# Front-End Development: Key Definitions

This document provides clear explanations of common front-end development terms, especially those related to display, rendering, and screen concepts.

---

## 1. Viewport

- **Definition:** The visible area of a web page in the user's browser window. It excludes browser toolbars, menus, and scrollbars.
- **Example:** On a desktop, resizing the browser window changes the viewport size. On mobile, the viewport is usually the device's screen size minus the browser UI.

## 2. Widescreen

- **Definition:** A display aspect ratio that is wider than the traditional 4:3. Common widescreen ratios are 16:9 and 16:10.
- **Example:** Most modern monitors, TVs, and laptops use a 16:9 widescreen format, providing more horizontal space for content.

## 3. Display vs. Render

- **Display:**
  - Refers to the act of showing content on the screen. It is the final visual output that the user sees.
  - Example: A hidden element (with `display: none`) is not displayed on the page.
- **Render:**
  - The process by which the browser interprets HTML, CSS, and JavaScript to construct and paint the web page on the screen.
  - Rendering includes layout calculation, style application, and drawing pixels.
  - Example: The browser renders a button by processing its HTML, applying CSS styles, and then displaying it.

## 4. Responsive Design

- **Definition:** An approach to web design that ensures content looks good and functions well on all devices and screen sizes.
- **Techniques:** Media queries, flexible grids, and responsive images.

## 5. Pixel (CSS Pixel)

- **Definition:** The basic unit of measurement for digital screens in CSS. Not always equal to a device's physical pixel due to device pixel ratio.

## 6. Breakpoint

- **Definition:** Specific viewport widths at which a website's layout changes to provide an optimal user experience.
- **Example:** A site might switch from a single-column to a multi-column layout at a 768px breakpoint.

## 7. Reflow vs. Repaint

- **Reflow:**
  - The process of recalculating the layout of the page when elements are added, removed, or resized.
- **Repaint:**
  - The process of redrawing elements on the screen when their appearance changes but layout does not (e.g., color change).

---

For more details, see the [MDN Web Docs: Layout and Rendering](https://developer.mozilla.org/en-US/docs/Web/Performance/How_browsers_work#the_rendering_engine)
