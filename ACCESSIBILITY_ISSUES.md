# Accessibility Issues Documentation

This document lists all the intentional accessibility violations added to this application for testing and educational purposes.

## WCAG Violations by Category

### 1. Perceivable Issues

#### 1.1 Missing Alternative Text (WCAG 1.1.1 - Level A)
- **Location**: Throughout the site
- **Issue**: Images missing `alt` attributes or having empty alt text
- **Examples**:
  - Logo image in header
  - All decorative images
  - Pricing table icons
  - Client testimonial images
  - Footer logo

#### 1.2 Missing Language Attribute (WCAG 3.1.1 - Level A)
- **Location**: `<html>` tag
- **Issue**: The `lang` attribute has been removed from the HTML element
- **Impact**: Screen readers cannot determine the page language

#### 1.3 Low Color Contrast (WCAG 1.4.3 - Level AA)
- **Location**: 
  - Status Board section (red/yellow/green indicators)
  - System status text on colored backgrounds
- **Issue**: Text colors don't meet 4.5:1 contrast ratio
- **Examples**:
  - Red background with #ff4444 text
  - Yellow background with #ffff66 text
  - Green background with #66ff66 text

#### 1.4 Color-Only Information (WCAG 1.4.1 - Level A)
- **Location**: System Status Board
- **Issue**: Status information conveyed only through color (red=critical, yellow=warning, green=operational)
- **Impact**: Color-blind users cannot distinguish status

#### 1.5 Auto-Playing Media (WCAG 1.4.2 - Level A)
- **Location**: 
  - Hidden video in header
  - Background audio element
- **Issue**: Media auto-plays without user control
- **Impact**: Cannot be paused or stopped easily

### 2. Operable Issues

#### 2.1 Missing Focus Indicators (WCAG 2.4.7 - Level AA)
- **Location**: Site-wide via CSS
- **Issue**: All focus outlines removed with `outline: none !important`
- **Impact**: Keyboard users cannot see which element has focus

#### 2.2 Keyboard Navigation Problems (WCAG 2.1.1 - Level A)
- **Location**: Multiple sections
- **Issues**:
  - Carousel navigation (prev/next) only works with mouse clicks
  - Drag-and-drop file upload has no keyboard alternative
  - Hover-only dropdown menus
  - CAPTCHA verification grid requires mouse clicks

#### 2.3 No Skip Navigation Link (WCAG 2.4.1 - Level A)
- **Location**: Page header
- **Issue**: No "skip to main content" link for keyboard users
- **Impact**: Must tab through entire navigation on every page

#### 2.4 Small Touch Targets (WCAG 2.5.5 - Level AAA)
- **Location**: Rating buttons section
- **Issue**: Buttons are only 2px padding with 8px font size
- **Impact**: Difficult to tap on touch devices

#### 2.5 Insufficient Time Limits (WCAG 2.2.1 - Level A)
- **Location**: Timer section
- **Issue**: Countdown timer with no way to pause, extend, or turn off
- **Impact**: Users may not have enough time to complete actions

#### 2.6 Non-keyboard Interactive Elements (WCAG 2.1.1 - Level A)
- **Location**: 
  - Modal close buttons using onclick
  - Emoji buttons
  - Custom carousel controls
  - CAPTCHA grid squares

### 3. Understandable Issues

#### 3.1 Forms Without Labels (WCAG 3.3.2 - Level A)
- **Location**: 
  - Login form (email and password fields)
  - Register form
  - Contact form
  - Newsletter form (placeholder as label only)
- **Issue**: Form inputs rely only on placeholder text for labels
- **Impact**: Screen readers cannot identify form fields properly

#### 3.2 Missing Required Field Indicators (WCAG 3.3.2 - Level A)
- **Location**: Contact form
- **Issue**: Phone field marked required only in placeholder text
- **Impact**: No programmatic indication of required fields

#### 3.3 Missing Form Validation Feedback (WCAG 3.3.1 - Level A)
- **Location**: All forms
- **Issue**: No accessible error messages or validation feedback
- **Impact**: Users don't know when form submission fails

#### 3.4 Confusing Link Text (WCAG 2.4.4 - Level A)
- **Location**: Services section
- **Issue**: Links with generic text like "click here", "Read More"
- **Impact**: Links are not descriptive out of context

#### 3.5 Links That Don't Look Like Links (WCAG 1.4.1 - Level A)
- **Location**: Confusing links section
- **Issue**: Real links styled to look like plain text
- **Impact**: Users cannot identify clickable elements

#### 3.6 Non-links That Look Like Links (WCAG 1.4.1 - Level A)
- **Location**: Confusing links section
- **Issue**: Plain text styled with underline and blue color
- **Impact**: Users expect clickable elements that aren't functional

#### 3.7 Autocomplete Disabled (WCAG 1.3.5 - Level AA)
- **Location**: Register form
- **Issue**: `autocomplete="off"` prevents browser autofill
- **Impact**: Harder for users to fill forms quickly and accurately

### 4. Robust Issues

#### 4.1 Missing ARIA Labels (WCAG 4.1.2 - Level A)
- **Location**: Throughout site
- **Issues**:
  - Icon-only buttons without aria-label
  - Emoji buttons without text alternatives
  - Modal dialog without proper ARIA attributes
  - Carousel without ARIA live regions

#### 4.2 Missing ARIA Landmarks (WCAG 1.3.1 - Level A)
- **Location**: Site-wide
- **Issue**: Sections lack proper ARIA landmark roles
- **Impact**: Screen reader users cannot navigate by landmarks

#### 4.3 Invalid Form Structure (WCAG 1.3.1 - Level A)
- **Location**: All forms
- **Issue**: Input fields not associated with labels
- **Impact**: Poor screen reader experience

#### 4.4 Missing Table Headers (WCAG 1.3.1 - Level A)
- **Location**: Feature comparison table
- **Issue**: Table uses `<td>` for headers instead of `<th>`
- **Impact**: Screen readers cannot identify column/row relationships

#### 4.5 Missing Button Type (WCAG 4.1.2 - Level A)
- **Location**: Various buttons
- **Issue**: Buttons missing explicit `type` attribute
- **Impact**: May cause unexpected form submissions

### 5. Additional Accessibility Problems

#### 5.1 Horizontal Scrolling (WCAG 1.4.10 - Level AA)
- **Location**: Partners section
- **Issue**: Content requires horizontal scrolling to view
- **Impact**: Difficult for users with motor impairments

#### 5.2 Justified Text (WCAG 1.4.8 - Level AAA)
- **Location**: "Our Story" section
- **Issue**: Full justification creates uneven spacing
- **Impact**: Difficult to read for users with dyslexia

#### 5.3 Fixed Overlay Blocking Content (WCAG 2.4.3 - Level A)
- **Location**: Special offer popup (fixed bottom-right)
- **Issue**: Fixed element partially covers page content
- **Impact**: May hide important information from users

#### 5.4 Animations Without Prefers-Reduced-Motion (WCAG 2.3.3 - Level AAA)
- **Location**: Loading spinner section
- **Issue**: Constantly spinning animation with no pause option
- **Impact**: Can cause vestibular disorders or motion sickness

#### 5.5 Hover-Only Interactions (WCAG 1.4.13 - Level AA)
- **Location**: Product categories dropdown menu
- **Issue**: Dropdown appears only on hover, not on click or keyboard focus
- **Impact**: Mobile and keyboard users cannot access menu

#### 5.6 CAPTCHA Without Alternative (WCAG 1.1.1 - Level A)
- **Location**: Verification section
- **Issue**: Visual-only CAPTCHA with no audio alternative
- **Impact**: Blind users cannot complete verification

#### 5.7 Icon-Only Buttons (WCAG 1.1.1 - Level A)
- **Location**: Action toolbar
- **Issue**: Buttons use only emoji with no text or aria-label
- **Impact**: Screen readers announce only generic emoji descriptions

#### 5.8 Multiple Column Text (WCAG 1.4.8 - Level AAA)
- **Location**: "Our Story" section  
- **Issue**: Text split into columns that may require horizontal scanning
- **Impact**: Difficult for users with cognitive disabilities

#### 5.9 Thin Custom Scrollbars (WCAG 2.5.5 - Level AAA)
- **Location**: Site-wide (CSS)
- **Issue**: Scrollbars styled to only 2px width
- **Impact**: Very difficult to grab and use

#### 5.10 No Visual Distinction for Disabled Elements
- **Location**: Site-wide (CSS)
- **Issue**: Disabled inputs only 0.95 opacity with cursor still showing pointer
- **Impact**: Users may try to interact with disabled elements

## Testing Recommendations

### Tools to Test With:
1. **WAVE (Web Accessibility Evaluation Tool)** - Browser extension
2. **axe DevTools** - Browser extension
3. **Lighthouse** - Chrome DevTools audit
4. **NVDA** or **JAWS** - Screen readers
5. **Keyboard only navigation** - Unplug your mouse
6. **Color contrast analyzers**
7. **Mobile device testing**

### Manual Testing Steps:
1. Navigate entire site using only Tab, Enter, and Arrow keys
2. Test with screen reader (NVDA/JAWS/VoiceOver)
3. Test at 200% zoom level
4. Test with images disabled
5. Test with CSS disabled
6. Test with high contrast mode
7. Test on mobile devices in portrait and landscape
8. Test with browser's forced colors mode

## WCAG Success Criteria Violated

### Level A (Must Fix):
- 1.1.1 Non-text Content
- 1.3.1 Info and Relationships
- 1.4.1 Use of Color
- 1.4.2 Audio Control
- 2.1.1 Keyboard
- 2.2.1 Timing Adjustable
- 2.4.1 Bypass Blocks
- 2.4.3 Focus Order
- 2.4.4 Link Purpose (In Context)
- 3.1.1 Language of Page
- 3.3.1 Error Identification
- 3.3.2 Labels or Instructions
- 4.1.2 Name, Role, Value

### Level AA (Should Fix):
- 1.3.5 Identify Input Purpose
- 1.4.3 Contrast (Minimum)
- 1.4.10 Reflow
- 1.4.13 Content on Hover or Focus
- 2.4.7 Focus Visible

### Level AAA (Nice to Have):
- 1.4.8 Visual Presentation
- 2.3.3 Animation from Interactions
- 2.5.5 Target Size

## Educational Use

This code demonstrates what **NOT** to do when building accessible websites. Each issue represents a real-world accessibility barrier that affects millions of users with disabilities.

### Who is Affected:
- **Blind users** - Rely on screen readers (missing alt text, labels, ARIA)
- **Low vision users** - Need good contrast and zoom support
- **Keyboard users** - Cannot use mouse (focus indicators, keyboard traps)
- **Motor impaired users** - Need large touch targets and no time limits
- **Deaf users** - Need captions for audio/video content
- **Cognitive disabilities** - Need clear navigation and simple language
- **Color blind users** - Cannot rely on color alone for information

## Fixing the Issues

To make this site accessible, you would need to:

1. Add proper alt text to all images
2. Add lang attribute to HTML element
3. Ensure all interactive elements are keyboard accessible
4. Add proper form labels and ARIA attributes
5. Implement visible focus indicators
6. Provide text alternatives for icon-only buttons
7. Fix color contrast issues
8. Remove auto-playing media or add controls
9. Add skip navigation links
10. Implement proper error handling and validation feedback
11. Use semantic HTML and proper heading hierarchy
12. Add ARIA landmarks and live regions
13. Ensure all content is available without hover
14. Provide alternatives to time-limited content
15. Make tables accessible with proper th elements
16. Test thoroughly with assistive technologies

---

**Note**: These issues were intentionally added for testing and educational purposes. Do not use this code as a template for production websites.
