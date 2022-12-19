The **Navigation Pattern** is a responsive `nav` element that contains the main links for accessing different views and button elements for site features (such as language translation). It uses responsive styling to appear as a three-button menu for small viewports. Possible button options include a homepage link (using an SVG logo), a translation button, or a mobile menu toggle. The menu is fixed to the bottom of the screen by default to assist with thumb reach.

---

On larger devices (tablets), the Navigation sticks to the top of the screen with the same three-button menu set displayed as inline links.

On extra large devices (desktop), the Navigation is statically positioned at the top of the page with the complete list of navigation items on display. Navigation items are only visible on desktop viewports.

---

It is recommended to use three to four items: the logo (home link), the language, search, and the menu buttons. You should display additional navigation items by clicking the menu button using the [Menu Pattern](menu).

---

Use the `aria-label="Primary Navigation"` attribute to distinguish the `nav` element from others.

---

The Navigation below is positioned statically for demonstration purposes. You must add the `o-navigation-fixed` next to the `o-navigation` class when you use this pattern in production.
