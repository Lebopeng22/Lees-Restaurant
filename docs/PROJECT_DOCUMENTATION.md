# Lee's Restaurant - Project Documentation

## Project Overview
Lee's Restaurant is a modern Italian restaurant website built with Svelte, HTML5, CSS3, and JavaScript. The website showcases authentic Italian cuisine with features for online table booking, menu browsing, photo gallery, and Google Maps integration.

## Design Objectives

### Client Requirements
1. **Fresh Ingredients Communication** - Clearly communicate that all meals are made fresh to order
2. **Contact Information** - Display address, telephone, and email
3. **Location Map** - Integrate Google Maps for restaurant location
4. **Dish Gallery** - Showcase 6+ high-quality food images
5. **Downloadable Menu** - Provide menu with all categories and items
6. **Trading Hours** - Display operating hours for all days
7. **Online Booking** - Implement calendar-based table reservation system

## Technical Stack

### Frontend Framework
- **Svelte 4.0** - Reactive component framework
- **Vite** - Build tool and dev server
- **HTML5** - Semantic markup
- **CSS3** - Modern styling with gradients, animations, and flexbox/grid
- **JavaScript** - Interactivity and form handling

### APIs & Services
- **Google Maps API** - Restaurant location visualization
- **Unsplash API** - Free stock images for gallery

### Build & Deployment
- **Git/GitHub** - Version control and repository hosting
- **npm** - Package management

## Project Structure

```
Lees-Restaurant/
├── src/
│   ├── components/
│   │   ├── Navbar.svelte          # Navigation component
│   │   ├── Footer.svelte          # Footer with contact info
│   │   ├── GallerySlider.svelte   # Photo gallery with animations
│   │   └── MapComponent.svelte    # Google Maps integration
│   ├── pages/
│   │   ├── HomePage.svelte        # Landing page
│   │   ├── BookingPage.svelte     # Table booking form
│   │   ├── MenuPage.svelte        # Menu display
│   │   └── GalleryPage.svelte     # Gallery page
│   ├── styles/
│   │   └── global.css             # Global styles
│   ├── App.svelte                 # Main app component
│   └── main.js                    # Entry point
├── index.html                     # HTML template
├── package.json                   # Dependencies
├── vite.config.js                 # Build configuration
├── .gitignore                     # Git ignore rules
└── README.md                      # Project readme
```

## Key Features Implementation

### 1. Navigation (Navbar.svelte)
- Sticky navbar with restaurant branding
- Responsive mobile menu toggle
- Navigation buttons for all pages
- Highlight button for booking CTA
- Color scheme: Dark red (#8b0000) with gold accents (#ffd700)

### 2. Home Page (HomePage.svelte)
- **Hero Section**: Eye-catching banner with CTA
- **About Section**: Restaurant story and values
- **Trading Hours**: Grid display of operating hours
- **Contact Information**: Address, phone, email, website
- **Map Integration**: Google Maps showing location

### 3. Table Booking (BookingPage.svelte)
- **Form Fields**:
  - Full Name (text input)
  - Email Address (email input)
  - Phone Number (tel input)
  - Date Selection (HTML5 date picker)
  - Time Selection (dropdown with 19 time slots)
  - Number of Persons (1-10)

- **Features**:
  - Date range: Tomorrow to 60 days ahead
  - Time slots from 11:00 AM to 10:00 PM
  - Form validation with error messages
  - Success confirmation display
  - Auto-reset after 3 seconds

### 4. Menu Page (MenuPage.svelte)
- **Categories**:
  - Starters (3 items)
  - Salads (3 items)
  - Meat Mains (4 items)
  - Pasta (3 items)

- **Menu Items Structure**:
  ```
  - Name
  - Description
  - Price
  ```

- **Features**:
  - Category filtering with active state
  - Animated transitions between categories
  - PDF download button (extensible)
  - Responsive grid layout

### 5. Gallery (GallerySlider.svelte)
- **6 High-Quality Images**:
  1. Italian Pasta Bolognese
  2. Fresh Meatballs
  3. Grilled T-Bone Steak
  4. Greek Salad
  5. Fried Ravioli
  6. Pork Ribs

- **Features**:
  - Main image display with overlay info
  - Previous/Next navigation buttons
  - Thumbnail navigation
  - Image counter
  - Smooth transitions and hover effects
  - Responsive design

### 6. Google Maps Integration (MapComponent.svelte)
- Default location: New York coordinates (40.7128, -74.0060)
- Custom marker with restaurant info
- Info window on marker click
- Customized map styling
- Address and contact info display below map

## Design Decisions

### Color Scheme
- **Primary Red**: #8b0000 (Deep red for Italian authenticity)
- **Accent Gold**: #ffd700 (Premium feel)
- **Backgrounds**: #f5f5f5, #ffffff (Clean, modern)
- **Text**: #333333 (High contrast for readability)

### Typography
- **Font Family**: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif
- **Hierarchy**: Clear h1-h4 sizing
- **Readability**: Line-height 1.6+ for body text

### Responsive Design
- **Breakpoints**: 768px for mobile/tablet switch
- **Mobile First**: Stacked layouts for small screens
- **Touch Friendly**: Larger buttons and inputs on mobile
- **Flexible Grids**: CSS Grid with auto-fit for items

## Form Validation

### Booking Form Validation
```javascript
- Name: Required, text input
- Email: Required, valid email format
- Phone: Required, tel format
- Date: Required, 1 day ahead minimum, 60 days maximum
- Time: Required, dropdown selection
- Persons: Required, 1-10 range
```

## API Integration

### Google Maps API
- **API Key**: Set via environment variable `VITE_GOOGLE_MAPS_API_KEY`
- **Features Used**:
  - Map rendering
  - Marker placement
  - Info window
  - Custom styling

### Environment Variables
```bash
VITE_GOOGLE_MAPS_API_KEY=your_api_key_here
```

## Security Considerations

1. **API Keys**: Never commit API keys to repository
2. **Environment Variables**: Use .env files (add to .gitignore)
3. **Form Submission**: Client-side validation with server validation recommended
4. **CORS**: Google Maps API handles cross-origin requests

## Performance Optimizations

1. **Image Optimization**: Unsplash provides optimized images
2. **CSS Bundling**: Vite handles CSS minification
3. **Component Splitting**: Lazy-loading ready structure
4. **Responsive Images**: Width-based optimization via Unsplash
5. **Smooth Scrolling**: CSS scroll-behavior: smooth

## Browser Compatibility

- **Chrome**: Full support
- **Firefox**: Full support
- **Safari**: Full support
- **Edge**: Full support
- **IE11**: Not supported (Svelte/Vite target ES2020)

## Challenges & Solutions

### Challenge 1: Calendar Integration
**Problem**: Needed simple date selection without heavy library
**Solution**: Used HTML5 `<input type="date">` with custom range logic

### Challenge 2: Image Gallery
**Problem**: Needed animated gallery without heavy carousel library
**Solution**: Built custom slider with Svelte reactivity

### Challenge 3: Form State Management
**Problem**: Managing complex form state with validation
**Solution**: Svelte's reactive bindings with local state variables

### Challenge 4: Map Integration
**Problem**: Loading Google Maps asynchronously in Svelte
**Solution**: Used onMount lifecycle hook with script tag injection

## Future Enhancements

1. **Backend Integration**
   - Database for booking storage
   - Email confirmation system
   - Admin booking management

2. **Payment Integration**
   - Deposit system for bookings
   - Online payment processing
   - Invoice generation

3. **Advanced Features**
   - User accounts and booking history
   - Menu customization for dietary requirements
   - Table layout visualization
   - Real-time availability checking
   - Multi-language support
   - Review/rating system

4. **Analytics**
   - Google Analytics integration
   - Booking trends analysis
   - Popular menu items tracking

5. **Mobile App**
   - React Native or Flutter version
   - Push notifications
   - App-only deals

## Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- npm (v7 or higher)

### Steps
```bash
# Clone repository
git clone https://github.com/Lebopeng22/Lees-Restaurant.git
cd Lees-Restaurant

# Install dependencies
npm install

# Create .env file
echo "VITE_GOOGLE_MAPS_API_KEY=your_key_here" > .env

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Testing Recommendations

1. **Functional Testing**
   - Form submission and validation
   - Navigation between pages
   - Gallery slide transitions
   - Map loading and interaction

2. **User Testing**
   - Book table flow (end-to-end)
   - Menu browsing experience
   - Mobile responsiveness
   - Accessibility with screen readers

3. **Cross-browser Testing**
   - Chrome, Firefox, Safari, Edge
   - Mobile browsers (iOS Safari, Chrome Mobile)

## Git Workflow

### Branches
- `main` - Production-ready code
- `develop` - Development branch
- `feature/*` - Feature branches
- `bugfix/*` - Bug fix branches

### Commit Messages
```
format: [TYPE] Description
TYPES: feat, fix, docs, style, refactor, test, chore

Examples:
- feat: Add photo gallery slider
- fix: Resolve date picker validation
- docs: Update API integration guide
```

## Deployment

### Recommended Platforms
1. **Vercel** - Optimal for Vite/Svelte
2. **Netlify** - Excellent JAMstack support
3. **GitHub Pages** - Simple static hosting

### Pre-deployment
- Run `npm run build`
- Test production build locally with `npm run preview`
- Set environment variables on hosting platform
- Update Google Maps API key restrictions

## Support & Maintenance

- Regular dependency updates
- Security vulnerability scanning
- Performance monitoring
- User feedback incorporation
- Bug fixes and patches

## License
Project created for Lee's Restaurant. All rights reserved.

---

**Last Updated**: September 14, 2024
**Version**: 1.0.0
**Status**: Production Ready
