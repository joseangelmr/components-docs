# Icon
Description.

## Schema

```js
{
  "type": "object",
  "properties": {
    "type": {
      "type": "string",
      "default": "icon",
    },
    "id": {
      "type": "string",
    },
    "alt": {
      "type": "string"
    },
    "position": {
      "type": "string",
      "enum": ["left", "right", "top", "bottom"]
    },
    "url": {
      "type": "string"
    }
  },
  "required": [
      "id",
      "alt",
  ]
}
```

## Related DTOs.
- [TODO]

## Example

### basic

```json
{
    "id": "codo_a_codo",
    "alt": "Logo MeLi",
}
```

### full url

```json
{
    "id": "logo__small@2x",
    "alt": "Logo MeLi",
    "url": "https://http2.mlstatic.com/frontend-assets/ui-navigation/5.8.0/mercadolibre/logo__small@2x.png",
}
```
