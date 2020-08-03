# Price
Description.

## Schema

```js
{
  "type": "object",
  "properties": {
    "type": {
      "type": "string",
      "default": "price",
    },
    "label": {
      "type": Label,
    },
    "original_value": {
      "type": "number",
    },
    "value": {
      "type": "string",
    },
    "currency_symbol": {
      "type": "string",
    }
  },
  "required": [
    "value",
  ]
}
```

## Related DTOs.

- [Label](https://github.com/joseangelmr/components-docs/blob/master/generics/label.md)

## Example

### as amount 

```json
{
  "type": "price",
  "label": {
    "text": "$ 4.900"
  },
  "original_value": 4900,
  "value": "4.900",
  "currency_symbol": "$"
}
```

### as percentage

```json
{
  "type": "price",
  "label": {
    "text": "18,50 %"
  },
  "original_value": 0.185,
  "value": "18,50",
  "currency_symbol": "%"
}
```
