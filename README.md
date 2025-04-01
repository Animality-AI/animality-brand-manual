# Animality.AI Brand Manual

## Project Overview

The Animality.AI brand manual is a comprehensive implementation guide designed to provide a cohesive and flexible brand identity system with the following key features:

- Interactive web interface with navigation
- Dynamic SVG generation for logos, icons, and patterns
- Custom color system
- Typography system
- Light/dark mode toggle
- Asset generator for custom brand elements

## File Structure

```
animality-brand-manual/
│
├── index.html                # Main HTML structure
├── css/
│   ├── normalize.css         # CSS reset
│   ├── typography.css        # Typography system
│   ├── components.css        # UI components
│   └── main.css              # Main styles
│
├── js/
│   ├── brand-config.js       # Brand configuration
│   ├── brand-manager.js      # SVG generation
│   └── ui.js                 # UI interactions
│
└── README.md                 # Project documentation
```

## Brand Configuration

### Color Palette

#### Primary Colors
- **Teal**: 
  - Hex: `#08A4B4`
  - RGB: `8, 164, 180`
  - CMYK: `96, 9, 0, 29`

#### Secondary Colors
- **Gold**: 
  - Hex: `#F5B921`
  - RGB: `245, 185, 33`
  - CMYK: `0, 24, 87, 4`
- **Yellow-Orange**: 
  - Hex: `#FF9E1F`
  - RGB: `255, 158, 31`
  - CMYK: `0, 38, 88, 0`

#### Neutral Colors
- **Black**: 
  - Hex: `#151515`
  - RGB: `21, 21, 21`
  - CMYK: `0, 0, 0, 92`
- **White**: 
  - Hex: `#FFFFFF`
  - RGB: `255, 255, 255`
  - CMYK: `0, 0, 0, 0`

### Typography

#### Primary Font: Work Sans
- Weights: 300, 400, 500, 600, 700
- Fallback: sans-serif

#### Secondary Font: Poppins
- Weights: 400, 600, 700
- Fallback: sans-serif

### Brand Usage Guidelines

- Color Distribution:
  - Primary: 70%
  - Secondary: 30%

- Spacing:
  - Base unit: 8 pixels
  - Grid divisions: 4

## Key Design Elements

### Logo System
- Dynamic SVG generation
- Triangular elements representing animal and technology aspects
- Configurable colors and sizes
- Optional text inclusion

### Pattern Generation
- Geometric triangular elements
- Customizable color and density
- Randomized placement and opacity

## Deployment Instructions

### GitHub Pages Deployment
1. Create a new repository (e.g., `animality-brand-manual`)
2. Upload all files maintaining the folder structure
3. Enable GitHub Pages:
   - Go to Settings > Pages
   - Select "main" branch as source
   - Click Save

### Customization Options
- Edit `brand-config.js` to change:
  - Colors
  - Typography
  - Spacing parameters
- Modify CSS files for styling adjustments
- Update SVG generation functions in `brand-manager.js`

## Key Features
- Responsive design
- Interactive asset generator
- Flexible branding system
- Dynamic SVG elements
- Comprehensive color and typography management

## Recommended Workflow
1. Review brand configuration
2. Customize colors and typography
3. Generate logo and pattern variations
4. Test across different devices and contexts
5. Maintain consistency in brand application
