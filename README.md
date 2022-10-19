# Navigation Pattern

Read more about [Navigation Pattern in the readme file](src/navigation.md).

It is recommended to use a maximum three items such as the logo, translate button, and menu button. Additional navigation items should be displayed in a different pattern, such as the [Menu Pattern](https://github.com/NYCOpportunity/pattern-menu).

## Usage

### Installation

```shell
$ npm install @nycopportunity/pattern-navigation
```

### Styles

The Navigation Pattern includes three stylesheets. One that sets default design tokens and display properties using [CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties), one that applies the tokens to the navigation CSS selectors, and one that adds some utilities for spacing (described below). The tokens can be used as is or overridden.

```scss
@forward '@nycopportunity/pattern-navigation/src/tokens.css';
@forward '@nycopportunity/pattern-navigation/src/navigation.css';
@forward '@nycopportunity/pattern-navigation/src/utilities.css';
```

### Markup

Below is the minimum required markup for the Navigation Pattern. It includes some possible navigation items and menu button options. This markup uses an [`aria-label` attribute](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute) to ensure the navigation is unique to screen readers as well as the [`role` attribute](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Navigation_Role) to signify this element includes a major set of links for the website or application.

```html
<!--{ @aria-label  Use "Primary Navigation" to identify the nav as a unique and major landmark }-->
<!--{ @class       Add "o-navigation-fixed" can be added to production layouts to fix the navigation to the bottom of the screen for the mobile viewport }-->
<!--{ @data-js     "navigation" is used as a JavaScript element selector. It is primarily used to set get the client height of the element to add padding to the bottom of the body. This prevents the mobile view of the element from covering the bottom of the page. }-->
<nav aria-label="Primary Navigation" class="o-navigation " data-js="navigation">
  <a class="o-navigation__home o-navigation__menu-item" href="#">
    <svg class="o-navigation__svg" fill="none" height="26" role="img" viewBox="0 0 456 152" width="78" xmlns="http://www.w3.org/2000/svg">
      <title>New York City Logo</title>
      <path d="M446.505 66.3803L456 57.0104V28.5052L427.495 0H332.505L304 28.5052V9.51562L294.505 0H256.505L247.01 9.51562V28.5052L228 47.5156L209.01 28.5052V9.51562L199.495 0H161.495L152 9.51562L142.505 0H104.505L95.0104 9.51562V47.5156L47.4948 0H9.49479L0 9.51562V142.505L9.49479 152H47.4948L57.0104 142.505V104.505L104.505 152H142.505L152 142.505V66.5052L199.495 114V142.505L209.01 152H247.01L256.505 142.505V114L304 66.5052V123.516L332.505 152H427.495L456 123.516V95.0104L446.505 85.4948H398.99V95.0104H361.01V57.0104H398.99V66.3803H446.505Z" fill="currentColor"></path>
      <path d="M449.233 6.41315C450.128 6.41315 450.899 6.32986 450.899 5.28876C450.899 4.41424 450.045 4.31013 449.337 4.31013H447.9V6.41315H449.233ZM447.921 10.4942H446.734V3.31068H449.462C451.19 3.31068 452.085 3.91452 452.085 5.37205C452.085 6.68383 451.294 7.20438 450.211 7.32931L452.231 10.4942H450.899L449.045 7.4126H447.942V10.4942H447.921ZM449.191 1.41589C446.38 1.41589 444.194 3.62301 444.194 6.78794C444.194 9.74466 446.11 12.16 449.191 12.16C451.981 12.16 454.168 9.9737 454.168 6.78794C454.168 3.62301 451.981 1.41589 449.191 1.41589ZM449.191 13.2844C445.464 13.2844 442.799 10.4942 442.799 6.78794C442.799 2.87342 445.756 0.291504 449.191 0.291504C452.585 0.291504 455.542 2.87342 455.542 6.78794C455.563 10.6816 452.606 13.2844 449.191 13.2844Z" fill="currentColor"></path>
    </svg>
  </a>
  <!--{ View navigation link item }-->
  <a class="o-navigation__item " href="#">Navigation</a>
  <!--{ Search site feature item }-->
  <button aria-controls="aria-c-search" aria-expanded="false" class="o-navigation__item" data-js="search">
    <svg class="o-navigation__menu-icon icon-ui">
      <use href="#feather-search"></use>
    </svg>
    <span class="o-navigation__menu-label">Search</span>
  </button>
  <!--{ Theme toggling site feature item }-->
  <button class="o-navigation__item" data-js="themes">
    <svg class="o-navigation__menu-icon icon-ui">
      <use data-js-themes="icon" href="#feather-moon"></use>
    </svg>
    <span class="sr-only">Toggle&nbsp;</span>
    <span class="o-navigation__menu-label" data-js-themes="label">Theme</span>
  </button>
  <!--{ Language translation site feature item }-->
  <label class="o-navigation__menu-item desktop:m-0" for="js-custom-language-selector">
    <svg class="o-navigation__menu-icon icon-ui">
      <use href="#icon-nyco-translate"></use>
    </svg>
    <div class="o-navigation__menu-label">
      <select id="js-custom-language-selector">
        <option disabled="true" selected="true" value="restore">Languages</option>
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

It is recommended to add padding to the bottom of the body to prevent the mobile view of the Navigation Pattern from covering the bottom of the page. Additionally, a bottom utility class for elements that use sticky or fixed positioning to the bottom of the view may also need help appearing above the menu.

The [utilites.css](src/utilities.css) file includes the following utilties.

```css
body, .o-navigation-spacing {
  padding-bottom: var(--o-navigation-height);
}

.o-navigation-spacing-bottom {
  bottom: var(--o-navigation-height);
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

The `--o-navigation-height` property value for both the padding and bottom position should be the height of the menu which can vary depending on the customization of the menu. By default it's set to 10 times the `--o-navigation-grid-base` (`8px`) which is `80px`. This property can be set via JavaScript and updated on the `load()` and `resize()` events.
