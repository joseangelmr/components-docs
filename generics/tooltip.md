# Tooltip
Description.

## Schema

```js
{
  "type": "tooltip",
  "properties": {
    "visible": {
      "type": "boolean",
      "default": true
    },
    "title": {
      "type": Label
    },
    "description": {
      "type": "node",
      "oneOf": [
        {
          "type": Label
        },
        {
          "type": LabelComposed
        }
      ]
    },
    "description_blocks": {
      "type": "array",
      "anyOf": [
        {
          "type": Label
        },
        {
          "type": LabelComposed
        }
      ]
    },
    "side": {
      "type": "string",
      "enum": [
        "top",
        "bottom",
        "leftTop",
        "rightTop",
        "bottomRight",
        "bottomLeft",
        "topLeft",
        "topRight",
        "left",
        "right"
      ],
      "default": "top"
    },
    "trigger": {
      "type": "string",
      "enum": [
        "click",
        "hover",
        "no-trigger"
      ],
      "default": "hover"
    },
    "hierarchy": {
      "type": "string",
      "enum": [
        "light",
        "dark",
        "highlight"
      ],
      "default": "light"
    },
    "offsetX": {
      "type": "number"
    },
    "offsetY": {
      "type": "number"
    }
  },
  "oneOf": [
    {
      "required": [
        "title",
      ],
    },
    {
      "required": [
        "description",
      ],
    },
        {
      "required": [
        "description_blocks",
      ],
    }
  ]
}
```

## Related DTOs.

- [Label](https://github.com/joseangelmr/components-docs/blob/master/generics/label.md)
- [Label Composed](https://github.com/joseangelmr/components-docs/blob/master/generics/label_composed.md)
- [Price](https://github.com/joseangelmr/components-docs/blob/master/generics/price.md)

## Example

### basic 

```json
{
  "type": "tooltip",
  "title": {
    "text": "Ingresos"
  },
}
```

### with description Label Composed

```json
{
  "type": "tooltip",
  "description": {
    "text": "Directos {direct} | Asistidos {no_direct}",
    "values": {
      "direct_price": {
        "original_value": 1000,
        "value": "1.000",
        "currency_symbol": "$",
      },
      "no_direct_price": {
        "original_value": 2000,
        "value": "2.000",
        "currency_symbol": "$",
      }
    }
  }
}
```

### with description_blocks Label

```json
{
  "type": "tooltip",
  "description_blocks": [
    {
      "text": "Los ingresos directos son los que obtienes por ventas directas de tus Product Ads."
    },
    {
      "text": "Los ingresos indirectos son los que obtienes por ventas indirectas a través de tus Product Ads.",
    }
  ]
}
```
