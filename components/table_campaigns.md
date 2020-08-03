# Table Campaigns
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
      "type": "string",
      "default": "table_campaigns_tab_campaign"
    },
    "header": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "string"
          },
          "type": {
            "type": "string"
          },
          "title": {
            "type": "Label"
          },
          "align": {
            "type": "string",
            "enum": [
              "left",
              "right",
              "center"
            ],
            "default": "left"
          },
          "sort": {
            "type": "boolean"
          },
          "end_no_sortable": {
            "type": "boolean"
          }
        },
        "required": [
          "id",
          "title"
        ]
      }
    },
    "rows": {
      "type": "array",
      "items": {
        "type": "object",
        "items": [
          {
            "type": "object",
            "properties": {
              "id": {
                "type": "integer"
              },
              "title": {
                "type": Label,
              },
              "status": {
                "type": Switch,
              },
              "budget": {
                "type": Price,
              },
              "impressions": {
                "type": Label,
              },
              "clicks": {
                "type": Label
              },
              "income": {
                "type": Price,
              },
              "investment": {
                "type": Price,
              },
              "tr": {
                "type": Price,
              },
              "orders": {
                "type": Label,
              },
            },
          }
        ]
      }
    },
    "paging": {
      "type": "object",
      "properties": {
        "total": {
          "type": "number",
        },
        "offset": {
          "type": "number",
        },
        "limit": {
          "type": "number",
        }
      },
      "required": [
        "total",
        "offset",
        "limit"
      ]
    },
    "metadata": {
      "type": "object",
      "properties": {
        "in_basket_label": Label,
        "catalog_listing_label": Label,
        "empty_state_search": {
          "type": "object",
          "properties": {
            "text": "string"
          },
          "required": [
            "text"
          ],
        },
        "next_label": Label,
        "prev_label": Label,
      }
    },
    "tracks": Tracks,
  },
  "required": [
    "type",
    "header",
    "rows",
    "paging",
    "metadata",
    "tracks",
  ]
}
```

## Related DTOs.

- [Label](https://github.com/joseangelmr/components-docs/blob/master/generics/label.md)

- [Price](https://github.com/joseangelmr/components-docs/blob/master/generics/price.md)

- [Switch]()

## Example

### empty rows

```json
{
  "id": "table_campaigns_tab_campaign",
  "type": "table_campaigns",
  "header": [
    {
      "id": "title",
      "type": "row_hub_campaign",
      "title": {
        "text": "Nombre de campaña"
      },
      "align": "left",
      "sort": false
    },
    {
      "id": "status",
      "type": "toggle",
      "title": {
        "text": "Estado"
      },
      "align": "center",
      "sort": false
    },
    {
      "id": "budget",
      "type": "price",
      "title": {
        "text": "Presupuesto"
      },
      "align": "right",
      "sort": false,
      "end_no_sortable": true
    },
    {
      "id": "orders",
      "type": "row_hub_orders",
      "title": {
        "text": "Ventas por publicidad"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "impressions",
      "title": {
        "text": "Impresiones"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "clicks",
      "title": {
        "text": "Clics"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "income",
      "type": "price",
      "title": {
        "text": "Ingresos"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "investment",
      "type": "price",
      "title": {
        "text": "Inversión"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "tr",
      "title": {
        "text": "Inversión<br>/ Ingresos"
      },
      "align": "right",
      "sort": false
    }
  ],
  "rows": [],
  "paging": {
    "total": 0,
    "offset": 0,
    "limit": 50
  },
  "metadata": {
    "in_basket_label": {
      "text": "Agregado"
    },
    "catalog_listing_label": {
      "text": "CATÁLOGO"
    },
    "empty_state_search": {
      "title": {
        "text": "No encontramos campañas que coincidan con tu búsqueda"
      }
    },
    "next_label": {
      "text": "Siguiente"
    },
    "prev_label": {
      "text": "Anterior"
    }
  }
}
```

### one Row

```json
{
  "id": "table_campaigns_tab_campaign",
  "type": "table_campaigns",
  "header": [
    {
      "id": "title",
      "type": "row_hub_campaign",
      "title": {
        "text": "Nombre de campaña"
      },
      "align": "left",
      "sort": false
    },
    {
      "id": "status",
      "type": "toggle",
      "title": {
        "text": "Estado"
      },
      "align": "center",
      "sort": false
    },
    {
      "id": "budget",
      "type": "price",
      "title": {
        "text": "Presupuesto"
      },
      "align": "right",
      "sort": false,
      "end_no_sortable": true
    },
    {
      "id": "orders",
      "type": "row_hub_orders",
      "title": {
        "text": "Ventas por publicidad"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "impressions",
      "title": {
        "text": "Impresiones"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "clicks",
      "title": {
        "text": "Clics"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "income",
      "type": "price",
      "title": {
        "text": "Ingresos"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "investment",
      "type": "price",
      "title": {
        "text": "Inversión"
      },
      "align": "right",
      "sort": false
    },
    {
      "id": "tr",
      "title": {
        "text": "Inversión<br>/ Ingresos"
      },
      "align": "right",
      "sort": false
    }
  ],
  "rows": [
    {
      "id": 292913103,
      "title": {
        "permalink": "/publicidad/product-ads/admin/dashboard?campaign_id=292913103",
        "primary_label": {
          "text": "Prueba2",
          "font_weight": "font-weight-semibold",
          "color": "blue-400",
          "editable": true
        },
        "secondary_label": {
          "text": "2 anuncios",
          "color": "gray-450"
        }
      },
      "status": {
        "type": "switch",
        "checked": true,
        "disabled": false
      },
      "budget": {
        "label": {
          "text": "$ 3.900",
          "disabled": false,
          "editable": true
        },
        "value": 3900,
        "currency_symbol": "$"
      },
      "impressions": {
        "text": "0",
        "disabled": false
      },
      "clicks": {
        "text": "0",
        "disabled": false
      },
      "income": {
        "label": {
          "text": "$ 0",
          "disabled": false
        },
        "value": 0,
        "currency_symbol": "$"
      },
      "investment": {
        "label": {
          "text": "$ 0",
          "disabled": false
        },
        "value": 0,
        "currency_symbol": "$",
        "editable": true
      },
      "tr": {
        "text": "-",
        "disabled": false
      },
      "orders": {
        "primary_label": {
          "text": "0",
          "disabled": false
        }
      },
      "tracks": {
        "update_campaign_name_close_event": {
          "melidata_event": {
            "path": "/advertising/pads2/hub/campaign/update/name/go",
            "event_data": {
              "campaign_name": "Prueba2",
              "name_new": "",
              "campaign_id": 292913103
            }
          }
        },
        "update_name_event": {
          "melidata_event": {
            "path": "/advertising/pads2/hub/campaign/update/name/pencil",
            "event_data": {
              "campaign_name": "Prueba2",
              "campaign_id": 292913103,
              "status": "active"
            }
          }
        },
        "update_campaign_event": {
          "melidata_event": {
            "path": "/advertising/pads2/hub/campaign/update/name/go",
            "event_data": {
              "campaign_name": "Prueba2",
              "name_new": "",
              "campaign_id": 292913103
            }
          }
        },
        "update_budget_go_event": {
          "melidata_event": {
            "path": "/advertising/pads2/hub/campaign/update/budget/go",
            "event_data": {
              "budget_new": "0",
              "campaign_id": 292913103,
              "budget": 3900,
              "status": "active"
            }
          }
        },
        "update_budget_close_event": {
          "melidata_event": {
            "path": "/advertising/pads2/hub/campaign/update/budget/close",
            "event_data": {
              "budget_new": "0",
              "campaign_id": 292913103,
              "budget": 3900,
              "status": "active"
            }
          }
        },
        "update_budget_event": {
          "melidata_event": {
            "path": "/advertising/pads2/hub/campaign/update/budget/pencil",
            "event_data": {
              "campaign_id": 292913103,
              "budget": 3900,
              "status": "active"
            }
          }
        }
      }
    }
  ],
  "paging": {
    "total": 1,
    "offset": 0,
    "limit": 50
  },
  "metadata": {
    "in_basket_label": {
      "text": "Agregado"
    },
    "catalog_listing_label": {
      "text": "CATÁLOGO"
    },
    "empty_state_search": {
      "title": {
        "text": "No encontramos campañas que coincidan con tu búsqueda"
      }
    },
    "next_label": {
      "text": "Siguiente"
    },
    "prev_label": {
      "text": "Anterior"
    }
  }
}
```
