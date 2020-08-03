# Picture
Description.

## Schema

```js
{
  "type": "object",
  "properties": {
    "type": {
      "type": "string",
      "default": "picture",
    },
    "id": {
      "type": "string"
    },
    "alt": {
      "type": "string"
    },
    "src": {
      "type": "object",
      "properties": {
        "src": {
          "type": "string"
        },
        "src2x": {
          "type": "string"
        }
      },
      "required": [
        "src"
      ]
    }
  },
  "required": [
    "id",
    "alt",
    "src"
  ]
}
```

## Related DTOs.
- [TODO]

## Example

### basic

```json
{
    "id": "logo__small",
    "alt": "Logo MeLi",
    "src": "https://http2.mlstatic.com/frontend-assets/ui-navigation/5.8.0/mercadolibre/logo__small.png"
}
```

### as 2x

```json
{
    "id": "logo__small@2x",
    "alt": "Logo MeLi",
    "src": {
        "src": "https://http2.mlstatic.com/frontend-assets/ui-navigation/5.8.0/mercadolibre/logo__small.png",
        "src2x": "https://http2.mlstatic.com/frontend-assets/ui-navigation/5.8.0/mercadolibre/logo__small@2x.png"
    },
}
```
