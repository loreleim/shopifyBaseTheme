# shopifyBaseTheme

a shopify 2.0 base theme that passes `shopify theme check`

# Anatomy of the Theme

[Theme: Details]()

[Theme: Colors]()

[Development: CLI Commands](#cli-commands)

## Local Development

Login to your theme with 
```
shopify login --store=yourstorename.myshopify.com
```

Serve your theme to local with
```
shopify theme serve
```

## Theme Details

Everything below shows up in the Customize > Theme settings > Theme details page. Items will show up in accordion format in the admin. If you want an accordion to show up, you'll have to configure it in the settings_schema.json

<details>
  <summary>settings_schema.json</summary>
  
  ```json
  {
    "name": "theme_info",
    "theme_name": "Dawn",
    "theme_version": "2.5.0",
    "theme_author": "Shopify",
    "theme_documentation_url": "https://help.shopify.com/manual/online-store/themes/os20/themes-by-shopify/dawn",
    "theme_support_url": "https://support.shopify.com/"
  },
  ```
</details>

## Theme Colors

<details>
  <summary>settings_data.json</summary>
  
  ```json
  "Craft": {
  "colors_primaryColor": "#EFECEC",
  "colors_secondaryColor": "#2A332F",
  "colors_foregroundColor": "#476154",
  "colors_text": "#1C1A1A",
  "colors_outline_button_labels": "#7B8382",
  "colors_background_1": "#EFECEC",
  "colors_background_2": "#C1BCAE",
  "type_header_font": "americana_n4",
  "type_body_font": "quattrocento_sans_n4",
  "sections": {
     "footer": {
      "type": "footer",
      "settings": {
        "color_scheme": "accent-1"
       },
      "blocks": {
        "menu": {
        "type": "link_list"
         },
         "text": {
           "type": "text"
          }
       },
       "block_order": [
         "menu",
         "text"
       ]
   }
   }
  }
  ```
</details>

## Theme Variables

<details>
  <summary>theme.liquid</summary>
  
  ```liquid
  {% style %}
    :root {
      /* Colors */
      --primaryButton: red;
      --color-base-solid-button-labels: {{ settings.colors_primaryColor }};
    }
  {% endstyle %}
  ```
  
</details>

</hr>

## Fonts

--font-heading-family

## CLI Commands

`shopify login --store=yoursitename.myshopify.com`

`shopify logout`

`shopify theme check`

[Source](https://shopify.dev/changelog/online-store-2-0-detect-theme-errors-with-theme-check)

`shopify theme serve`

## Theme Comments

```liquid
{% comment %}theme-check-disable UndefinedObject{% endcomment %}
```
