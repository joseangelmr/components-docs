# Label
Description.

## Schema

```js
{
  "type": "object",
  "properties": {
    "id": {
      "type": "string"
    },
    "type": {
      "type": "string"
    },
    "text": {
      "type": "string"
    },
    "color": {
      "type": "string"
    },
    "bgColor": {
      "type": "string"
    },
    "disabled": {
      "type": "boolean",
    },
    "editable": {
      "type": "boolean"
    }
  },
  "required": [
    "type",
    "text",
  ]
}
```

## Related DTOs.

- [TODO]

## Example

```json
{
  "id": "username",
  "type": "label",
  "text": "Hello world",
  "color": "#3483fa",
  "bgColor": "#000",
}
```

