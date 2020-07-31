# Label
Breve descripción.

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

## Ejemplo

```json
{
  "id": "username",
  "type": "label",
  "text": "Hello world",
  "color": "#3483fa",
  "bgColor": "#000",
}
```

## Caso de uso relacionados

- [Label](https://github.com/mercadolibre/fury_advertising-components/tree/master/packages/common/src/components/label)
- [Componente 1](https://github.com/mercadolibre/fury_advertising-components/tree/master/packages/lift-section)
- [View 1](https://github.com)
