# Lee's Restaurant - User Flow Diagram

## System Overview

```
┌─────────────────────────────────────────────────────────────┐
│                    LEE'S RESTAURANT WEBSITE                 │
└─────────────────────────────────────────────────────────────┘
                              │
                    ┌─────────┼─────────┐
                    │         │         │
                    ▼         ▼         ▼
             Navbar Menu   Logo      Mobile Toggle
                    │         │         │
                    └─────────┼─────────┘
                              │
```

## Main User Flow

```
                          ┌─────────────┐
                          │  HOMEPAGE   │
                          └──────┬──────┘
                                 │
                   ┌───────��─────┼─────────────┐
                   │             │             │
                   ▼             ▼             ▼
              MENU PAGE    BOOKING PAGE    GALLERY PAGE
                   │             │             │
                   │             │             │
                   ▼             ▼             ▼
            ┌──────────┐  ┌────────────┐  ┌────────────┐
            │ Category │  │   FORM     │  │  SLIDER    │
            │ Filter   │  │ VALIDATION │  │   IMAGES   │
            └──────────┘  └────────────┘  └────────────┘
                │             │                  │
                │             │                  │
                ▼             ▼                  ▼
          Menu Items   Success Message    Next/Prev Controls
          with prices  & Confirmation     Thumbnail Navigation
```

## Detailed User Journeys

### Journey 1: Homepage Navigation

```
                    VISITOR LANDS
                         │
                         ▼
                  ┌────────────────┐
                  │  HERO SECTION  │
                  │  (Welcome CTA) │
                  └────────┬───────┘
                           │
                    ┌──────┴──────┐
                    │             │
                    ▼             ▼
            "BOOK TABLE"        Other Pages
              Button             Navigation
                │                 │
                │                 │
           (See Journey 3)   (Explore Website)
```

### Journey 2: Menu Exploration

```
          CLICK MENU (Navbar)
                 │
                 ▼
        ┌──────────────────┐
        │  MENU PAGE LOADS │
        └────────┬─────────┘
                 │
                 ▼
    ┌─────────────────────────┐
    │  Default: STARTERS      │
    │  Category Buttons       │
    │  • Starters (active)    │
    │  • Salads               │
    │  • Meat Mains           │
    │  • Pasta                │
    └────────┬────────────────┘
             │
      ┌──────┼──────┬──────┬──────┐
      │      │      │      │      │
      ▼      ▼      ▼      ▼      ▼
   Click  Click  Click  Click  Download
  Starters Salads Mains  Pasta  PDF
      │      │      │      │      │
      ▼      ▼      ▼      ▼      ▼
  ┌──────────────────────────────────────┐
  │  Display Menu Items                  │
  │  • Item Name                         │
  │  • Description                       │
  │  • Price                             │
  │  (Animated Transition)               │
  └──────────────────────────────────────┘
```

### Journey 3: Table Booking (COMPLETE FLOW)

```
        USER CLICKS "BOOK TABLE"
                 │
                 ▼
      ┌─────────────────────┐
      │ BOOKING PAGE LOADS  │
      └──────────┬──────────┘
                 │
                 ▼
      ┌──────────────────────────────────────┐
      │  BOOKING FORM                        │
      │  ┌────────────────────────────────┐  │
      │  │ Full Name Input                │  │
      │  │ [____________________]         │  │
      │  └────────────────────────────────┘  │
      └──────────┬───────────────────────────┘
                 │
                 ▼
      ┌──────────────────────────────────────┐
      │  EMAIL & PHONE ROW                   │
      │  ┌─────────────────┐ ┌──────────────┐│
      │  │ Email Address   │ │ Phone Number ││
      │  │ [___________]   │ │ [__________]││
      │  └─────────────────┘ └──────────────┘│
      └──────────┬───────────────────────────┘
                 │
                 ▼
      ┌──────────────────────────────────────┐
      │  DATE & TIME SELECTION ROW           │
      │  ┌─────────────┐    ┌────────────────┐│
      │  │  📅 Date    │    │  ⏰ Time       ││
      │  │[min: today+1]    │ [Dropdown List]││
      │  │[max: +60 days]   │ • 11:00 AM    ││
      │  │              │    │ • 11:30 AM    ││
      │  │              │    │ • 12:00 PM    ││
      │  │              │    │ • ... etc     ││
      │  └─────────────┘    └────────────────┘│
      └──────────┬───────────────────────────┘
                 │
                 ▼
      ┌──────────────────────────────────────┐
      │  NUMBER OF PERSONS                   │
      │  ┌────────────────────────────────┐  │
      │  │ Persons: [__] (1-10 range)     │  │
      │  │ Max 10 people                  │  │
      │  └────────────────────────────────┘  │
      └──────────┬───────────────────────────┘
                 │
                 ▼
      ┌──────────────────────────────────────┐
      │  USER CLICKS "CONFIRM BOOKING"      │
      └──────────┬───────────────────────────┘
                 │
          ┌──────┴──────┐
          │             │
         NO             YES
       ERROR        VALIDATION
          │             │
          ▼             ▼
    ┌──────────┐  ┌─────────────────┐
    │  Display │  │ SUCCESS MESSAGE │
    │  Error   │  │ ┌─────────────┐ │
    │  Message │  │ │ ✓ Confirmed │ │
    │ (Red Box)│  │ │ Name: [Name]│ │
    │          │  │ │ Date/Time   │ │
    │  (Retry) │  │ │ Persons: [N]│ │
    └──────────┘  │ │ Email Sent  │ │
          ▲       │ └─────────────┘ │
          │       └────────┬────────┘
          │                │
          └────────────────┴─── Form Resets
                           (Auto-Clear after 3s)
```

### Journey 4: Gallery Browsing

```
      CLICK GALLERY (Navbar)
             │
             ▼
    ┌────────────────────┐
    │  GALLERY PAGE      │
    └────────┬───────────┘
             │
             ▼
    ┌─────────────────────────────┐
    │  MAIN IMAGE DISPLAY         │
    │  ┌───────────────────────┐  │
    │  │  [Large Image]        │  │
    │  │  Title: [Dish Name]   │  │
    │  │  Desc: [Description]  │  │
    │  └───────────────────────┘  │
    └──────────┬────────────────────┘
               │
               ▼
    ┌─────────────────────────────┐
    │  CONTROLS LAYER             │
    │  ◀  Previous  │  Next  ▶    │
    │  (Circular Buttons)         │
    └──────────┬────────────────────┘
               │
               ▼
    ┌─────────────────────────────┐
    │  THUMBNAIL NAVIGATION       │
    │  [Img1] [Img2] [Img3]       │
    │  [Img4] [Img5] [Img6]       │
    │  (Click to Select)          │
    │  (Active = Red Border)      │
    └──────────┬────────────────────┘
               │
               ▼
    ┌─────────────────────────────┐
    │  SLIDE COUNTER              │
    │  1 / 6                      │
    └─────────────────────────────┘
```

### Journey 5: Contact Information Access

```
          USER ON ANY PAGE
                │
                ▼
      ┌──────────────────┐
      │  SCROLL DOWN     │
      │  TO BOTTOM       │
      └────────┬─────────┘
               │
               ▼
      ┌─────────────��────────────────┐
      │  FOOTER                      │
      │  ┌────────────────────────┐  │
      │  │ Restaurant Name & Info │  │
      │  │ 📍 Address             │  │
      │  │ 📞 Phone               │  │
      │  │ 📧 Email               │  │
      │  │ 🕐 Hours               │  │
      │  │ 🌐 Social Media        │  │
      │  └────────────────────────┘  │
      └──────────────────────────────┘
```

## State Management Flow

```
┌─────────────────────────────────────┐
│  APP.SVELTE (Main State)            │
│  currentPage: 'home'|'booking'|...  │
│  navigateTo(page) Function          │
└──────────────────┬──────────────────┘
                   │
        ┌──────────┼──────────┐
        │          │          │
        ▼          ▼          ▼
    Navbar    [Page]      Footer
        │      State       │
        └──────────────────┘
             │
        Page Dispatch
        Events
```

## Component Communication

```
App (Parent)
├── Navbar.svelte
│   └── emit: 'navigate' event
├── HomePage.svelte
│   ├── emit: 'navigate' event
│   └── MapComponent.svelte
│       └── Google Maps Script
├── BookingPage.svelte
│   └── Local State: formData
├── MenuPage.svelte
│   └── Local State: activeCategory
├── GalleryPage.svelte
│   └── GallerySlider.svelte
│       └── Local State: currentIndex
└── Footer.svelte
    └── Static Content
```

## Responsive Breakpoints

```
Desktop (>768px)
├── Full navbar with horizontal menu
├── Multi-column grids
└── Full-size images

Tablet/Mobile (<768px)
├── Hamburger menu toggle
├── Single column layouts
├── Stacked form rows
└── Optimized image sizes
```

## Data Flow: Booking Form

```
┌─────────────────────────────────┐
│  User Input Events              │
│  • name (text)                  │
│  • email (email)                │
│  • phone (tel)                  │
│  • date (date)                  │
│  • time (select)                │
│  • persons (number 1-10)        │
└──────────────┬──────────────────┘
               │
               ▼
    ┌────────────────────────┐
    │  Svelte Reactive      │
    │  bind:value={data}    │
    └────────────┬───────────┘
                 │
                 ▼
    ┌────────────────────────┐
    │  Form Submit Handler   │
    │  handleSubmit(e)       │
    └────────────┬───────────┘
                 │
          ┌──────┴──────┐
          │             │
          ▼             ▼
    ┌─────────┐   ┌──────────────┐
    │Validate │   │  Show Error  │
    │ Data    │   │  Messages    │
    └────┬────┘   └──────────────┘
         │
         ▼
   ┌─────────────┐
   │ Show Success│
   │ Message     │
   │ Auto-Reset  │
   │ After 3s    │
   └─────────────┘
```

---

**Navigation Summary**:
- **Home Page** → Landing + About + Hours + Contact + Map
- **Menu Page** → Category Tabs + Items Display + PDF Download
- **Gallery Page** → Slider + Navigation + Thumbnails
- **Booking Page** → Form Validation + Calendar + Time Selection + Confirmation
- **Footer** → Always Visible with Contact Info
