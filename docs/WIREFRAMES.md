# Lee's Restaurant - Wireframes

## Wireframe 1: Homepage Layout

```
╔════════════════════════════════════════════════════════════════╗
║  🍝 Lee's Restaurant  [Home] [Menu] [Gallery] [Book Table]     ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║                   HERO SECTION                                 ║
║              Welcome to Lee's Restaurant                       ║
║         Experience Authentic Italian Cuisine                   ║
║              Made Fresh to Order                               ║
║                                                                ║
║              [📅 BOOK A TABLE] (CTA Button)                   ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║  OUR STORY                                                     ║
║  ───────────                                                   ║
║  At Lee's Restaurant, we believe in serving only the finest   ║
║  Italian cuisine prepared with the freshest ingredients...     ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║  TRADING HOURS                                                 ║
║  ┌─────────────────┐  ┌──────────────────┐  ┌──────────────┐ ║
║  │ Mon - Thu       │  │ Fri - Sat        │  │ Sunday       │ ║
║  │ 11 AM - 10 PM   │  │ 11 AM - 11 PM    │  │ 12 PM - 9 PM │ ║
║  └─────────────────┘  └──────────────────┘  └──────────────┘ ║
║                                                                ║
║  ┌──────────────────┐                                         ║
║  │ Holidays         │                                         ║
║  │ Closed Christmas │                                         ║
║  └──────────────────┘                                         ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║  GET IN TOUCH                                                  ║
║  ┌──────────────────┐  ┌──────────────┐  ┌───────────────┐   ║
║  │ 📍 Address       │  │ 📞 Phone     │  │ 📧 Email      │   ║
║  │ 123 Italian St   │  │ (555)123-456 │  │ info@lees.com │   ║
║  └──────────────────┘  └──────────────┘  └───────────────┘   ║
║                                                                ║
║  ┌───────────────┐                                            ║
║  │ 🌐 Website    │                                            ║
║  │ www.lees.com  │                                            ║
║  └───────────────┘                                            ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║  FIND US ON THE MAP                                            ║
║  ┌────────────────────────────────────────────────────────┐   ║
║  │  Google Maps Integration                               │   ║
║  │  [Map showing restaurant location with marker]         │   ║
║  │                                                         │   ║
║  └────────────────────────────────────────────────────────┘   ║
║  📍 123 Italian Street, Flavor City, FC 12345                  ║
║  📞 (555) 123-4567 | 📧 info@leesrestaurant.com               ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║  Footer: © 2024 Lee's Restaurant | Facebook | Instagram       ║
╚═══���════════════════════════════════════════════════════════════╝
```

---

## Wireframe 2: Booking Table Form

```
╔════════════════════════════════════════════════════════════════╗
║  🍝 Lee's Restaurant  [Home] [Menu] [Gallery] [Book Table] ✓   ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║                   BOOK A TABLE                                 ║
║          Reserve your table at Lee's Restaurant               ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║  Full Name *                                                   ║
║  ┌──────────────────────────────────────────────────────────┐ ║
║  │ Your full name                                           │ ║
║  └──────────────────────────────────────────────────────────┘ ║
║                                                                ║
║  Email Address *                      Phone Number *           ║
║  ┌─────────────────────────────┐  ┌──────────────────────┐   ║
║  │ your@email.com              │  │ (555) 123-4567       │   ║
║  └─────────────────────────────┘  └──────────────────────┘   ║
║                                                                ║
║  Date *                               Time *                   ║
║  ┌─────────────────────────────┐  ┌──────────────────────┐   ║
║  │ 📅 [Date Picker]            │  │ ⏰ [Dropdown ▼]      │   ║
║  │ Range: Tomorrow to +60 Days │  │ 11:00 AM             │   ║
║  └─────────────────────────────┘  │ 12:00 PM             │   ║
║                                     │ 1:00 PM              │   ║
║                                     │ ...                  │   ║
║                                     │ 10:00 PM             │   ║
║                                     └──────────────────────┘   ║
║                                                                ║
║  Number of Persons *                                           ║
║  ┌──────────────────────────────────────────────────────────┐ ║
║  │ [  1  ] (Range: 1-10 Maximum 10 people)               │ ║
║  └──────────────────────────────────────────────────────────┘ ║
║                                                                ║
║              ��────────────────────────────┐                    ║
║              │ ✓ CONFIRM BOOKING          │                    ║
║              └────────────────────────────┘                    ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║  SUCCESS STATE (After Submit)                                  ║
║  ┌──────────────────────────────────────────────────────────┐ ║
║  │ ✓ Booking Confirmed!                                    │ ║
║  │                                                          │ ║
║  │ Thank you, [Name]!                                      │ ║
║  │ Your table for 4 people is booked for                  │ ║
║  │ September 20, 2024 at 7:00 PM                           │ ║
║  │                                                          │ ║
║  │ A confirmation email has been sent to                   │ ║
║  │ your@email.com                                           │ ║
║  └──────────────────────────────────────────────────────────┘ ║
║  (Auto-clears after 3 seconds)                                 ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║  Footer: © 2024 Lee's Restaurant | Facebook | Instagram       ║
╚════════════════════════════════════════════════════════════════╝
```

---

## Wireframe 3: Menu Page

```
╔════════════════════════════════════════════════════════════════╗
║  🍝 Lee's Restaurant  [Home] [Menu] ✓ [Gallery] [Book Table]   ║
╠════════════════════════════════════════��═══════════════════════╣
║                                                                ║
║                      OUR MENU                                  ║
║     Freshly prepared Italian cuisine, made to order           ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║  Category Selection:                        📥 Download Menu   ║
║  ┌──────────┬──────────┬────────────┬──────────┐              ║
║  │Starters  │ Salads   │Meat Mains  │ Pasta    │              ║
║  │ (Active) │          │            │          │              ║
║  └──────────┴──────────┴────────────┴──────────┘              ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║  STARTERS                                                      ║
║  ┌──────────────────────────┐  ┌──────────────────────────┐   ║
║  │ Italian Mini Meatballs   │  │ Fried Ravioli            │   ║
║  │                          │  │                          │   ║
║  │ Tender homemade          │  │ Crispy fried ravioli     │   ║
║  │ meatballs in marinara    │  │ with ricotta filling,    │   ║
║  │ sauce                    │  │ served with marinara     │   ║
║  │                          │  │                          │   ║
║  │ $9.99                    │  │ $8.99                    │   ║
║  └──────────────────────────┘  └──────────────────────────┘   ║
║                                                                ║
║  ┌──────────────────────────┐                                  ║
║  │ Chicken Livers           │                                  ║
║  │                          │                                  ║
║  │ Sautéed chicken livers   │                                  ║
║  │ with garlic and white    │                                  ║
║  │ wine                     │                                  ║
║  │                          │                                  ║
║  │ $10.99                   │                                  ║
║  └──────────────────────────┘                                  ║
║                                                                ║
║  (Other categories display similarly when tabs are clicked)   ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║  Footer: © 2024 Lee's Restaurant | Facebook | Instagram       ║
╚═════════════════════════════════════════════════════════════���══╝
```

---

## Wireframe 4: Photo Gallery

```
╔════════════════════════════════════════════════════════════════╗
║  🍝 Lee's Restaurant  [Home] [Menu] [Gallery] ✓ [Book Table]   ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║                    PHOTO GALLERY                               ║
║           Explore our delicious Italian dishes               ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║                                                                ║
║  MAIN IMAGE DISPLAY                                            ║
║  ┌────────────────────────────────────────────────────────┐   ║
║  │                                                         │   ║
║  │  [LARGE HIGH-QUALITY FOOD IMAGE]                      │   ║
║  │                                                         │   ║
║  │  Italian Pasta Bolognese                              │   ║
║  │  Authentic spaghetti with rich meat sauce             │   ║
║  │                                                         │   ║
║  └────────────────────────────────────────────────────────┘   ║
║                                                                ║
║  NAVIGATION CONTROLS                                           ║
║  ◀ [Previous]                               [Next] ▶          ║
║  (Circular buttons on left and right)                          ║
║                                                                ║
║  THUMBNAIL NAVIGATION                                          ║
║  ┌────┐  ┌────┐  ┌────┐  ┌────┐  ┌────┐  ┌────┐              ║
║  │ 1  │  │ 2  │  │ 3  │  │ 4  │  │ 5  │  │ 6  │              ║
║  │[🖼 ]│  │[🖼 ]│  │[🖼 ]│  │[🖼 ]│  │[🖼 ]│  │[🖼 ]│              ║
║  └────┘  └────┘  └────┘  └────┘  └────┘  └────┘              ║
║  (Meatballs) (Steak) (Salad) (Ravioli) (Ribs) (active)       ║
║                                                                ║
║  SLIDE COUNTER                                                 ║
║  1 / 6                                                         ║
║                                                                ║
║  IMAGE DESCRIPTIONS:                                           ║
║  1. Italian Pasta Bolognese - Authentic spaghetti             ║
║  2. Fresh Meatballs - Homemade Italian meatballs             ║
║  3. Grilled Steak - Premium T-bone steak with fries          ║
║  4. Fresh Salad - Crisp Greek salad with feta cheese         ║
║  5. Fried Ravioli - Golden crispy fried ravioli              ║
║  6. Pork Ribs - Slow-cooked tender pork ribs                ║
║                                                                ║
╠════════════════════════════════════════════════════════════════╣
║  Footer: © 2024 Lee's Restaurant | Facebook | Instagram       ║
╚════════════════════════════��═══════════════════════════════════╝
```

---

## Wireframe 5: Mobile Homepage (Responsive)

```
╔════════════════════════════╗
║ 🍝 Lee's Restaurant   ☰    ║
╠════════════════════════════╣
║                            ║
║     HERO SECTION           ║
║  Welcome to Lee's          ║
║  Restaurant                ║
║                            ║
║  Experience Authentic      ║
║  Italian Cuisine           ║
║  Made Fresh to Order       ║
║                            ║
║  [📅 BOOK A TABLE]         ║
║                            ║
╠════════════════════════════╣
║                            ║
║  OUR STORY                 ║
║                            ║
║  At Lee's Restaurant, we   ║
║  believe in serving only   ║
║  the finest Italian        ║
║  cuisine prepared with     ║
║  the freshest              ║
║  ingredients...            ║
║                            ║
╠════════════════════════════╣
║                            ║
║  TRADING HOURS             ║
║                            ║
║  Mon - Thu                 ║
║  11 AM - 10 PM             ║
║                            ║
║  Fri - Sat                 ║
║  11 AM - 11 PM             ║
║                            ║
║  Sunday                    ║
║  12 PM - 9 PM              ║
║                            ║
╠════════════════════════════╣
║                            ║
║  GET IN TOUCH              ║
║                            ║
║  📍 123 Italian Street     ║
║  📞 (555) 123-4567         ║
║  📧 info@lees.com          ║
║                            ║
╠════════════════════════════╣
║                            ║
║  FIND US ON THE MAP        ║
║  ┌──────────────────────┐  ║
║  │ Google Maps          │  ║
║  │ [Mobile Map View]    │  ║
║  └──────────────────────┘  ║
║                            ║
╠════════════════════════════╣
║ © 2024 Lee's Restaurant    ║
║ Facebook | Instagram       ║
╚════════════════════════════╝
```

---

## Responsive Design Notes

### Desktop (>768px)
- Sidebar or horizontal navigation
- Multi-column grid layouts (2-3 columns)
- Full-width images
- Expanded form layouts

### Tablet (768px)
- Hamburger menu option
- 2-column layouts
- Scaled images
- Form rows break into 2 columns

### Mobile (<768px)
- Full hamburger menu
- Single column layout
- Stacked form fields
- Optimized image sizing
- Touch-friendly buttons (min 44px)

---

## Color Scheme in Wireframes

- **Primary Red**: #8b0000 (Headlines, Buttons, Accents)
- **Gold Accent**: #ffd700 (CTA Buttons, Highlights)
- **Backgrounds**: #f5f5f5, #ffffff
- **Text**: #333333
- **Borders**: #ddd

---

## Interactive Elements

1. **Buttons**: 12px padding, rounded corners, hover effects
2. **Form Inputs**: 8px padding, 2px border, focus states
3. **Links**: Underline on hover, color change
4. **Cards**: Box shadow, hover lift effect
5. **Gallery**: Smooth transitions, overlay effects

---

**Last Updated**: September 14, 2024
