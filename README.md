# Navigation Pattern

The Navigation Pattern is a responsive nav that contains the main links for navigating different views and button elements for site features (such as translation). It uses responsive styling to appear as a three button menu for small view ports. Possible button options may include a homepage link (as an SVG logo), translation button, or mobile menu toggle. The menu is fixed to the bottom of the screen by default to assist with thumb reach.

On larger devices (tablets) the menu sticks to the top of the screen with the same three button menu set displayed as inline links.

On extra large devices (desktop) the menu is statically positioned at the top of the page with the full list of navigation items on display. Navigation items are only visible on desktop view ports.

It is recommended to use a maximum three items such as the logo, translate button, and menu button. Additional navigation items should be displayed in a different pattern, such as the [Menu Pattern](https://github.com/NYCOpportunity/pattern-menu).

## Usage

### Installation

```shell
$ npm install @nycopportunity/pattern-navigation
```

### Styles

The Navigation Pattern includes two stylesheets. One that sets default design tokens and display properties using [CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) and one that applies the tokens to the navigation CSS selectors. The tokens can be used as is or overridden.

```scss
@import '@nycopportunity/pattern-navigation/src/tokens';
@import '@nycopportunity/pattern-navigation/src/navigation';
```

### Markup

Below is the minimum required markup for the Navigation Pattern. It includes some possible navigation items and menu button options. This markup uses an [`aria-label` attribute](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute) to ensure the navigation is unique to screen readers as well as the [`role` attribute](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Navigation_Role) to signify this element includes a major set of links for the website or application.

```html
<!-- The o-navigation-fixed class controls the fixed positioning and display of the menu. -->
<nav aria-label="Primary Navigation" class="o-navigation o-navigation-fixed" role="navigation">
  <a class="o-navigation__logo o-navigation__menu-item" href="/">
    <svg aria-hidden="true" fill="none" height="60" viewBox="0 0 60 128" width="128" xmlns="http://www.w3.org/2000/svg" role="img">
      <title>Website Title</title>

      {{ Your custom SVG logo content }}
    </svg>
  </a>

  <!-- Possible Navigation Items. These will be hidden on mobile devices. Any number of these can be used -->
  <a class="o-navigation__item" href="/programs">Programs</a>

  <a class="o-navigation__item" href="/about">About</a>

  <!-- Possible Menu Item. A custom language selector. -->
  <label class="o-navigation__menu-item" for="js-custom-language-selector">
    <svg class="o-navigation__menu-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
      <path d="M3 16C4.5 15.1667 8 12.5 10 9.5C12 6.5 11.5 4 11.5 4M14.5 4H8.5M2.5 4H8.5M8.5 4V2.5M4.5 7C5.5 10 7.5 12.5 10 14.5M12 21L13.35 18M21 21L19.65 18M13.35 18L16.5 10.5C17.7302 13.2337 18.4198 15.2663 19.65 18M13.35 18H19.65"></path>
    </svg>

    <div class="o-navigation__menu-label">
      <select class="underline" name="js-custom-language-selector">
        <option disabled="true" selected="true" value="restore">Translate</option>
        <option value="es">Español</option>
        <option value="ru">Русский</option>
        <option value="ko">한국어</option>
        <option value="ar">العربية</option>
        <option value="ht">Kreyol</option>
        <option value="zh-CN">繁體中文</option>
        <option value="fr">Français</option>
        <option value="pl">polski</option>
        <option value="ur">اردو</option>
        <option value="bn">বাংলা</option>
      </select>
    </div>
  </label>

  <!-- Possible Menu Item. A sliding menu toggle. This will only be visible on mobile devices. -->
  <button class="o-navigation__menu-item o-navigation__menu-toggle">
    <svg class="o-navigation__menu-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
      <line x1="3" y1="12" x2="21" y2="12"/>
      <line x1="3" y1="6" x2="21" y2="6"/>
      <line x1="3" y1="18" x2="21" y2="18"/>
    </svg>

    <span class="o-navigation__menu-label">Menu</span>
  </button>
</nav>
```

### Possible Menu Items

The navigation menu items to not have functionality embedded. Functionality can be added depending on the use case. The examples in the markup include the [Menu Pattern](https://github.com/NYCOpportunity/pattern-menu) and the [Google Translate Element](https://github.com/CityOfNewYork/patterns-scripts/tree/main/src/google-translate-element) from the Patterns Scripts library.

## Breakpoints

The table below describes the primary breakpoint values used in the token and main stylesheets.

Intended Device Type | Pixel Width
---------------------|-
Tablet               | `768px`
Desktop              | `1112px`

## Spacers

It is recommended to add padding to the bottom of the body to prevent the mobile view of the Navigation Pattern from covering the bottom of the page. A utility class can be created to also use the spacing in other parts of the interface if required. Additionally, a bottom utility class for elements that use sticky or fixed positioning to the bottom of the view may also need help appearing above the menu.

The value for both the padding and bottom position should be the height of the menu which can vary depending on the customization of the menu. These utility classes can be reset for tablet view ports when the menu is no longer fixed to the bottom of the view. Below is an example of such utilities.

```css
body, .o-navigation-spacing {
  padding-bottom: 86px;
}

.o-navigation-spacing-bottom {
  bottom: 86px;
}

@media screen and (min-width: 768px) {
  body, .o-navigation-spacing {
    padding-bottom: 0;
  }

  .o-navigation-spacing-bottom {
    bottom: 0;
  }
}
```
