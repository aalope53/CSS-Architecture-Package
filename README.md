# CSS-Architecture-Package

Refactoring Evidence

Before: The CSS would have repeated values for colors, spacing, border radiuses, font sizes, and focus styles throughout different selectors.

After: I created custom properties in :root, such as --color-primary, --space-md, --radius-medium, and --focus-color. These values can now be reused throughout the stylesheet instead of writing the same values multiple times.

Before: Repeated elements such as buttons, project cards, featured cards, and navigation links could require separate styling each time they appeared.

After: I planned reusable component classes such as .button, .featured-card, .project-card, .social-card, and .nav-list. This allows the same styles to be reused anywhere those components appear.

Before: Small styling changes could require creating more specific selectors or repeating declarations.

After: Utility classes such as .text-center, .margin-top-lg, and .max-width-text are planned for simple, reusable changes without increasing selector specificity.

Before: CSS rules could become difficult to organize as more styles were added.

After: The stylesheet is divided into cascade layers so each type of CSS has a clear location and purpose. This should make future changes easier to find and maintain.


Architecture Notes 

The CSS uses the layer order reset, base, layout, components, utilities, and overrides. The reset layer removes browser default styling. Base contains the site's global styles and design tokens. Layout controls the positioning and structure of major areas such as the header, hero, and card grids. Components contain reusable interface elements such as buttons, navigation, and cards. Utilities provide small reusable adjustments, while overrides contain styles that should have higher priority, such as focus and current-page states.

The design tokens in :root define repeated decisions for color, typography, spacing, shape, and focus. For example, --color-primary establishes the main red color, the --space-* properties create a consistent spacing system, and the --radius-* properties provide consistent rounded corners. Using tokens means these design decisions can be changed in one location instead of searching through the entire stylesheet.

The naming approach uses descriptive class names based on an element's purpose, such as .site-header, .featured-card, .project-card, .social-card, and .card-grid. Utility names such as .text-center and .margin-top-lg describe the specific change they make. This helps make the CSS easier to understand without relying on highly specific selectors.

As the CSS is implemented, I will check the site at narrow, medium, and wide browser widths to make sure the layouts respond correctly. I will also check hover, active, keyboard focus, and current-page states and test the print styles using the browser's print preview. These checks will help identify layout, accessibility, and browser-related problems before the site is finished.

AI Disclosure: No AI was used to make the initial CSS Planning Package, however AI was used briefly for the refactoring evidence and notes to word it a little better, specifically the wording of the before and after portions.