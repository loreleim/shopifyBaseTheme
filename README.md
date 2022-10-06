# shopifyBaseTheme

a shopify 2.0 base theme that passes `shopify theme check`

# Anatomy of the Theme

[Theme: Details](#theme-details)

[Theme: Colors](#theme-colors)

[Theme: Making a Block](#theme-blocks)

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

Admin Frontend: Customize > Theme settings > Theme details page

Items will show up in accordion format in the admin. If you want an accordion to show up, you'll have to
configure it in the settings_schema.json

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
Customize > Theme settings > Colors

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
  "type_headerFont": "americana_n4",
  "type_bodyFont": "quattrocento_sans_n4",
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

## Making a Block
`nameofblock` represents something you should change to match your block


en.default.schema.json > new sections.nameofblock
```
"nameofblock": {
  "name": "",
  settings: {
    "title": {
      "label": "Heading"
    }, 
    "collection": {
      "label": "Collection"
    }
  }

}
```

this gets called on with
```
t:sections.block-collection.name
t:sections.block-collection.settings.title.label
"t:sections.block-collection.settings.collection.label
```

sections > create a new file > block-nameofblock.liquid
```

```

## Theme Variables

<details>
  <summary>theme.liquid</summary>
  
  ```liquid
  {% style %}
    :root {
      /* Colors */
      --buttonColor: red;
      --buttonColor: {{ settings.colors_primaryColor }};
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
