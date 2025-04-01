Animality.AI Brand Manual - Implementation Guide
Project Overview
This guide contains the core implementation files for the Animality.AI brand manual. The brand manual is designed with the following features:

Interactive web interface with navigation
Dynamic SVG generation for logos, icons, and patterns
Custom color system with teal blue primary, gold/yellow-orange secondary colors
Typography system using Work Sans and Poppins
Light/dark mode toggle
Asset generator for custom brand elements

File Structure
Copyanimality-brand-manual/
├── index.html              # Main HTML structure
├── css/
│   ├── normalize.css       # CSS reset
│   ├── typography.css      # Typography system
│   ├── components.css      # UI components
│   └── main.css            # Main styles
├── js/
│   ├── brand-config.js     # Brand configuration
│   ├── brand-manager.js    # SVG generation
│   └── ui.js               # UI interactions
└── README.md               # Project documentation
Core Brand Configuration
javascriptCopy// brand-config.js - Core brand parameters
const BRAND_CONFIG = {
  name: "Animality.AI",
  version: "1.0.0",
  colors: {
    primary: {
      teal: {
        hex: "#08A4B4",
        rgb: "8, 164, 180",
        cmyk: "96, 9, 0, 29"
      }
    },
    secondary: {
      gold: {
        hex: "#F5B921",
        rgb: "245, 185, 33",
        cmyk: "0, 24, 87, 4"
      },
      yellowOrange: {
        hex: "#FF9E1F",
        rgb: "255, 158, 31", 
        cmyk: "0, 38, 88, 0"
      }
    },
    neutral: {
      black: {
        hex: "#151515",
        rgb: "21, 21, 21",
        cmyk: "0, 0, 0, 92"
      },
      white: {
        hex: "#FFFFFF",
        rgb: "255, 255, 255",
        cmyk: "0, 0, 0, 0"
      }
    }
  },
  typography: {
    primary: {
      family: "Work Sans",
      weights: [300, 400, 500, 600, 700],
      fallback: "sans-serif"
    },
    secondary: {
      family: "Poppins",
      weights: [400, 600, 700],
      fallback: "sans-serif"
    }
  },
  spacing: {
    unit: 8, // Base spacing unit in pixels
    grid: 4  // Grid divisions
  },
  usage: {
    colorDistribution: {
      primary: 70,
      secondary: 30
    }
  }
};
SVG Asset Generation Examples
javascriptCopy// Logo generation function from brand-manager.js
generateLogo(options = {}) {
  const defaults = {
    color: this.config.colors.primary.teal.hex,
    secondaryColor: this.config.colors.secondary.gold.hex,
    width: 200,
    height: 60,
    includeText: true
  };

  const settings = { ...defaults, ...options };
  
  let svg = `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 ${settings.width} ${settings.height}" width="${settings.width}" height="${settings.height}">
    <defs>
      <style>
        .logo-primary { fill: ${settings.color}; }
        .logo-secondary { fill: ${settings.secondaryColor}; }
        .logo-text { font-family: "Work Sans", sans-serif; font-weight: 600; }
        .logo-ai { font-family: "Poppins", sans-serif; font-weight: 700; }
      </style>
    </defs>
    <g class="logo-mark">
      <!-- Triangular element representing the animal aspect -->
      <polygon class="logo-primary" points="20,10 50,50 10,50" />
      <!-- Sharp angular element representing the technology aspect -->
      <path class="logo-secondary" d="M60,10 L90,10 L75,40 Z" />
    </g>`;
  
  if (settings.includeText) {
    svg += `
    <g class="logo-type" transform="translate(100, 35)">
      <text class="logo-text" fill="#151515">Animality</text>
      <text class="logo-ai" x="90" y="0" fill="${settings.color}">.AI</text>
    </g>`;
  }
  
  svg += `</svg>`;
  
  return svg;
}
CSS Color Variables
cssCopy/* CSS color variables from main.css */
:root {
  /* Color Variables */
  --color-primary: #08A4B4;
  --color-primary-light: #3BBECB;
  --color-primary-dark: #067A87;
  --color-secondary-gold: #F5B921;
  --color-secondary-orange: #FF9E1F;
  
  /* Neutral Colors */
  --color-black: #151515;
  --color-gray-900: #212121;
  --color-gray-800: #424242;
  --color-gray-700: #616161;
  --color-gray-600: #757575;
  --color-gray-500: #9E9E9E;
  --color-gray-400: #BDBDBD;
  --color-gray-300: #E0E0E0;
  --color-gray-200: #EEEEEE;
  --color-gray-100: #F5F5F5;
  --color-white: #FFFFFF;
}
Typography System
cssCopy/* Typography Variables from typography.css */
:root {
  /* Font Families */
  --font-primary: 'Work Sans', sans-serif;
  --font-secondary: 'Poppins', sans-serif;
  
  /* Font Weights */
  --font-weight-light: 300;
  --font-weight-regular: 400;
  --font-weight-medium: 500;
  --font-weight-semibold: 600;
  --font-weight-bold: 700;
  
  /* Font Sizes */
  --font-size-xs: 0.75rem;    /* 12px */
  --font-size-sm: 0.875rem;   /* 14px */
  --font-size-base: 1rem;     /* 16px */
  --font-size-lg: 1.125rem;   /* 18px */
  --font-size-xl: 1.25rem;    /* 20px */
  --font-size-2xl: 1.5rem;    /* 24px */
  --font-size-3xl: 1.75rem;   /* 28px */
  --font-size-4xl: 2rem;      /* 32px */
  --font-size-5xl: 2.5rem;    /* 40px */
  --font-size-6xl: 3rem;      /* 48px */
}
Pattern Generation Example
javascriptCopy// Pattern generation from brand-manager.js
generatePattern(options = {}) {
  const defaults = {
    color: this.config.colors.primary.teal.hex,
    secondaryColor: this.config.colors.secondary.gold.hex,
    width: 100,
    height: 100,
    density: 'medium' // low, medium, high
  };

  const settings = { ...defaults, ...options };
  
  // Generate a repeating pattern with triangular elements
  let patternSVG = `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 ${settings.width} ${settings.height}" width="${settings.width}" height="${settings.height}">
    <defs>
      <pattern id="trianglePattern" patternUnits="userSpaceOnUse" width="${settings.width}" height="${settings.height}">`;
  
  // Pattern density determines number of elements
  const elements = settings.density === 'low' ? 3 : 
                   settings.density === 'high' ? 12 : 6;
  
  for (let i = 0; i < elements; i++) {
    const x = Math.random() * settings.width;
    const y = Math.random() * settings.height;
    const size = Math.random() * 15 + 5;
    const color = Math.random() > 0.7 ? settings.secondaryColor : settings.color;
    
    patternSVG += `<polygon fill="${color}" points="${x},${y} ${x+size},${y+size} ${x-size},${y+size}" opacity="${Math.random() * 0.5 + 0.5}" />`;
  }
  
  patternSVG += `
      </pattern>
    </defs>
    <rect fill="url(#trianglePattern)" width="100%" height="100%" />
  </svg>`;
  
  return patternSVG;
}
Deployment Instructions
GitHub Pages Deployment

Create a new repository on GitHub (e.g., animality-brand-manual)
Upload all files maintaining the folder structure
Enable GitHub Pages in repository settings:

Go to Settings > Pages
Select "main" branch as source
Click Save



Your brand manual will be available at: https://[username].github.io/animality-brand-manual/
Customization
To customize the brand manual:

Edit brand-config.js to change colors, typography, and other brand parameters
Modify CSS files to adjust styling
Update SVG generation functions in brand-manager.js to change logo and pattern designs

Key Features

Logo System: Dynamic SVG generation with triangular elements
Color System: Primary teal with secondary gold/orange accents
Typography: Work Sans for body text, Poppins for headers
Patterns & Textures: Triangular geometric elements
Asset Generator: Interactive tool for creating custom brand assets
Responsive Design: Works on all device sizes

License
