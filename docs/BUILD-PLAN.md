# Review Feature Build Plan

## Overview
Add a customer review feature to `index.html` that allows visitors to leave a star rating (1–5) and a written review. Reviews are displayed in a card grid and persist across page reloads using localStorage.

---

## Steps

### Step 1 — Add Review Section HTML
Add a `<section id="reviews">` to `index.html`, placed between the Testimonials and Location & Hours sections. Includes a section title, subtitle, a review form, and a reviews display area.

### Step 2 — Add Star Rating Component
Inside the form, add five clickable `<span>` elements with `data-value` attributes and ARIA roles for accessibility. A hidden `<input>` stores the selected rating value. A message label displays the rating description.

### Step 3 — Style the Star Rating
In `styles.css`, style the stars gray by default and gold (`#f5a623`) when hovered or selected. Add a smooth scale transition on interaction and a small descriptive label beneath the stars.

### Step 4 — Style the Review Cards
Add CSS for a 3-column responsive grid (`.reviews-grid`) that collapses to a single column on screens 768px and below. Each `.review-card` uses the site's existing light background and border variables for visual consistency.

### Step 5 — Star Interactivity (JavaScript)
Attach `mouseenter`, `mouseleave`, and `click` event listeners to each star. Hovering previews a highlight up to that star and shows a label (Poor / Fair / Good / Very Good / Excellent). Clicking locks the selection. Keyboard (`Enter` / `Space`) support is included for accessibility.

### Step 6 — Form Submission and Validation
On submit, validate that the name, star rating, and review text are all present. If any field is missing, display a red error message. On success, build a review object with the name, rating, text, and formatted date.

### Step 7 — localStorage Persistence
Save the reviews array to `localStorage` under the key `synergyReviews` after each submission. On page load, retrieve and render any previously saved reviews so they survive browser refreshes.

---

## Files Modified
- `index.html` — review section HTML, star rating markup, JavaScript
- `css/styles.css` — star rating styles, review form styles, review card grid
- `docs/BUILD-PLAN.md` — this file
