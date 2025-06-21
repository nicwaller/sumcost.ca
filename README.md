# SumCost.ca

A Canadian tax calculator that determines the true cost of purchases by factoring in income tax, CPP, EI contributions, and provincial sales taxes.

## Features

- **Comprehensive tax calculation**: Includes federal and provincial income tax brackets for 2024
- **All Canadian jurisdictions**: Supports all provinces and territories with accurate GST/PST/HST rates  
- **Real-time calculations**: Updates results as you type with animated feedback
- **URL state management**: Share calculations via URL hash parameters
- **Mobile optimized**: Responsive design with appropriate input modes for iOS/Android
- **Zero dependencies**: Pure vanilla JavaScript with no external libraries

## Technical Architecture

### Single File Application
The entire application is contained in `index.html` with embedded CSS and JavaScript. This approach provides:
- Zero build process complexity
- Fast loading with no external requests
- Easy deployment to any static hosting
- Simple maintenance and updates

### Tax Calculation Engine
- **Federal tax brackets**: 5-tier progressive tax system (15% - 33%)
- **Provincial tax rates**: Complete coverage including AB, BC, ON, QC with accurate brackets
- **CPP contributions**: 2024 rates with $68,500 maximum pensionable earnings
- **EI contributions**: 2.29% rate with $66,600 maximum insurable earnings
- **Sales tax calculation**: Province-specific GST/PST/HST handling

### Data Structures
```javascript
// Provincial tax rates with detailed breakdown
const taxRates = {
    'ON': { gst: 0, pst: 0, hst: 13 },
    'QC': { gst: 5, pst: 9.975, hst: 0 }
    // ... all provinces
};

// Progressive tax brackets
const incomeTaxBrackets = {
    federal: [
        { min: 0, max: 55867, rate: 0.15 },
        // ... additional brackets
    ],
    provincial: {
        // Province-specific brackets
    }
};
```

## Development

### Local Development
```bash
# Option 1: Direct file access
open index.html

# Option 2: Local server (recommended)
python -m http.server 8000
# or
npx serve .
```

### Testing
Manual testing required. Key test scenarios:
- Various income levels across tax brackets
- All provincial tax calculations
- Edge cases (high income, low income, $0 purchases)
- Mobile device input handling

### Deployment
Static files can be deployed to:
- GitHub Pages (current setup)
- Netlify
- Vercel
- Any web server

## File Structure
```
.
├── index.html              # Complete application
├── CNAME                   # GitHub Pages custom domain
├── ogpreview.jpg          # Open Graph social preview
├── twitter-card-image.jpg # Twitter card image
└── README.md              # This file
```

## Social Media Integration
- **Open Graph**: Optimized for Facebook sharing with 1200x630 preview image
- **Twitter Cards**: Summary large image format with dedicated image
- **SEO**: Comprehensive meta tags for search engine optimization

## Browser Support
- Modern browsers (ES6+ features used)
- Mobile Safari and Chrome (iOS input modes)
- No IE support (uses modern JavaScript features)

## Contributing
When updating tax rates or brackets:
1. Verify rates against current CRA publications
2. Test calculations manually against known scenarios
3. Update both federal and provincial rates as needed
4. Consider CPP/EI maximum thresholds for annual updates