# Hub Page
Description.

## Schema

```js
{
  "type": "object",
  "properties": {
    "title": {
      "type": "string",
    },
    "header": Header,
    "onboarding": {
      "type": "array",
      "items": {
        "anyOf": [
          "type": OnboardingModal,
        ]
      }
    },
    "messages": {
      "type": "object",
      "properties": {
        "hub_campaign_active_success": Message,
        "hub_campaign_active_error": Message,
        "hub_campaign_move_pads_success": Message,
        "hub_campaign_single_move_pads_success": Message,
        "hub_campaign_add_pads_success": Message,
        "hub_campaign_move_pads_congrats_success": Message,
        "hub_campaign_paused_success": Message,
        "hub_sads_active_success": Message,
        "hub_campaign_paused_error": Message,
        "hub_pad_active_success": Message,
        "hub_pad_pause_success": Message,
        "hub_pad_active_pause_error": Message,
        "hub_campaign_move_pads_error": Message,
        "hub_pad_single_active_success": Message,
        "hub_pad_single_pause_success": Message,
      }
    },
    "components": {
      "type": "array",
      "items": [
        {
          "type": "object",
          "properties": {
            "type": {
               "type": "string",
              "default": "tab_view",
            },
            "selected_tab": {
               "type": "string",
              "default": "tab_campaigns",
            },
            "tabs": {
              "type": "array",
              "items": [
                TabCampaigns,
                TabPads
              ]
            }
          }
        },
        {
          "type": "object",
          "properties": {
            "type": {
              "type": "string",
              "default": "update_budget_modal",
            },
            "title": Label,
            "description": Label,
            "field": Field,
            "confirm_action": Action,
            "cancel_action": Action,
          }
        }
        {
          "type": "object",
          "properties": {
            "type": {
              "type": "string",
              "default": "update_name_modal",
            },
            "title": Label,
            "description": Label,
            "field": Field,
            "confirm_action": Action,
            "cancel_action": Action,
          }
        }
      ]
    },
    "picture_config": {
      "type": "object",
      "properties": {
        "template_icon": {
          "type": "string",
          "default": "https://http2.mlstatic.com/resources/frontend/statics/admin-pa-frontend/images/{id}.svg",
        },
        "template_pad": {
          "type": "string",
          "default": "https://http2.mlstatic.com/resources/frontend/statics/admin-pa-frontend/images/{id}.svg",
        }
      },
      "required": [
        "template_icon",
        "template_pad",
      ]
    },
  },
  "required": [
    "title",
    "header",
    "onboarding",
    "messages",
    "components",
    "picture_config",
  ]
}
```

## Related DTOs.

- [Header]()
- [OnboardingModal]()
- [Message]()
- [TabCampaigns]()
- [TabPads]()
- [Label]()
- [Field]()
- [Action]()


## Example

### basic

```json
{
  "title": "Publicidad",
  "header": {
    "title": {
      "text": "Publicidad"
    },
    "help_action": {
      "label": {
        "text": "Necesito ayuda",
        "color": "blue"
      },
      "icon": {
        "id": "helper_outline",
        "alt": "Necesito ayuda"
      },
      "context": {
        "title": "Ayuda con campañas",
        "title_campaigns": "Ayuda con campañas",
        "title_pads": "Ayuda con anuncios",
        "version": "v1.5.0",
        "source_id": 16212,
        "user_id": "614384876",
        "entities": [
          {
            "entity": {
              "name": "Advertising",
              "department": "publicidad"
            },
            "problem": {
              "site_id": "MLC",
              "context": {
                "status": "start"
              }
            }
          }
        ]
      }
    }
  },
  "onboarding": [
    {
      "id": "onboarding_welcome",
      "type": "onboarding_modal",
      "onboarding": true,
      "icon": {
        "id": "onboarding_welcome",
        "alt": "Bienvenido/a",
        "url": "https://http2.mlstatic.com/resources/frontend/statics/admin-pa-frontend/images/onboarding-bienvenida.svg"
      },
      "title": {
        "text": "¡Ahora puedes tener más de una campaña!"
      },
      "description_blocks": [
        {
          "label": {
            "text": "Agrupa tus anuncios como prefieras y asígnale diferentes presupuestos a cada una."
          }
        },
        {
          "label": {
            "text": "Dejaremos de activar automáticamente publicidad en tus nuevas publicaciones. Podrás promocionarlas y agregarlas a otras campañas cuando tú decidas."
          }
        }
      ],
      "confirmation_action": {
        "label": {
          "text": "Entendido",
          "color": "white",
          "bg_color": "blue",
          "background": "blue"
        }
      }
    }
  ],
  "messages": {
    "hub_campaign_active_success": {
      "type": "success",
      "text": "Activaste tu campaña."
    },
    "hub_campaign_active_error": {
      "type": "error",
      "text": "No es posible activar tu campaña. Por favor, inténtalo más tarde."
    },
    "hub_campaign_move_pads_success": {
      "type": "success",
      "text": "¡Moviste {0} anuncios a {1} exitosamente!"
    },
    "hub_campaign_single_move_pads_success": {
      "type": "success",
      "text": "¡Listo! Moviste 1 anuncio a la campaña {0}."
    },
    "hub_campaign_add_pads_success": {
      "type": "success",
      "text": "¡Listo! Agregaste {0} anuncios a tu campaña."
    },
    "hub_campaign_move_pads_congrats_success": {
      "type": "success",
      "text": "¡Listo! Moviste {0} anuncios a la campaña {1}."
    },
    "hub_campaign_paused_success": {
      "type": "success",
      "text": "Pausaste tu campaña."
    },
    "hub_sads_active_success": {
      "type": "success",
      "text": "¡Activaste {0} anuncios!"
    },
    "hub_campaign_paused_error": {
      "type": "error",
      "text": "No es posible pausar tu campaña. Por favor, inténtalo más tarde."
    },
    "hub_pad_active_success": {
      "type": "success",
      "text": "¡Listo! Activaste {0} anuncios."
    },
    "hub_pad_pause_success": {
      "type": "default",
      "text": "¡Listo! Pausaste {0} anuncios."
    },
    "hub_pad_active_pause_error": {
      "type": "error",
      "text": "Algunas de tus acciones no se completaron. Inténtalo nuevamente."
    },
    "hub_campaign_move_pads_error": {
      "type": "error",
      "text": "No pudimos guardar los cambios, inténtalo nuevamente."
    },
    "hub_pad_single_active_success": {
      "type": "success",
      "text": "¡Activaste 1 anuncio!"
    },
    "hub_pad_single_pause_success": {
      "type": "success",
      "text": "¡Pausaste 1 anuncio!"
    }
  },
  "components": [
    {
      "type": "tab_view",
      "selected_tab": "tab_campaigns",
      "tabs": [
        {
          "type": "tab_campaigns",
          "title": {
            "text": "Campañas"
          },
          "components": [
            {
              "id": "date_range_tab_campaign",
              "type": "date_range",
              "title": {
                "text": "Métricas"
              },
              "selector": {
                "disabled": false,
                "month_calendar_list": [
                  "Enero",
                  "Febrero",
                  "Marzo",
                  "Abril",
                  "Mayo",
                  "Junio",
                  "Julio",
                  "Agosto",
                  "Septiembre",
                  "Octubre",
                  "Noviembre",
                  "Diciembre"
                ],
                "days_of_week": [
                  "D",
                  "L",
                  "M",
                  "M",
                  "J",
                  "V",
                  "S"
                ],
                "default_label": {
                  "label": {
                    "text": "Últimos 30 días"
                  },
                  "value": "30_days",
                  "date": {
                    "to": "2020-07-30",
                    "from": "2020-07-01"
                  }
                },
                "options": [
                  {
                    "date": {
                      "to": "2020-07-30",
                      "from": "2020-05-02"
                    },
                    "label": {
                      "text": "Últimos 90 días",
                      "disabled": false
                    },
                    "value": "90_days",
                    "disabled": false
                  },
                  {
                    "date": {
                      "to": "2020-07-30",
                      "from": "2020-06-01"
                    },
                    "label": {
                      "text": "Últimos 60 días",
                      "disabled": false
                    },
                    "value": "60_days",
                    "disabled": false
                  },
                  {
                    "date": {
                      "to": "2020-07-30",
                      "from": "2020-07-01"
                    },
                    "label": {
                      "text": "Últimos 30 días",
                      "disabled": false
                    },
                    "value": "30_days",
                    "disabled": false
                  },
                  {
                    "date": {
                      "to": "2020-07-30",
                      "from": "2020-07-24"
                    },
                    "label": {
                      "text": "Últimos 7 días",
                      "disabled": false
                    },
                    "value": "7_days",
                    "disabled": false
                  },
                  {
                    "date": {},
                    "label": {
                      "text": "Personalizado",
                      "disabled": false
                    },
                    "value": "custom_days",
                    "disabled": false
                  }
                ]
              }
            },
            {
              "id": "lift_chart_tab_campaign",
              "type": "lift_chart",
              "title": {
                "text": "Metricas totales",
                "color": "black"
              },
              "top_section": {
                "sell_with_ad": {
                  "number_label": {
                    "text": "0",
                    "color": "black"
                  },
                  "label": {
                    "text": "Ventas por publicidad",
                    "color": "black",
                    "position": "bottom"
                  },
                  "icon_action": {
                    "id": "sell_with_ad",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda",
                      "url": "https://http2.mlstatic.com/resources/frontend/statics/admin-pa-frontend/images/question.svg"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Ventas por publicidad"
                    },
                    "description": {
                      "text": "Directos  0 | Asistidos 0"
                    },
                    "description_blocks": [
                      {
                        "text": "Tienes una venta directa cuando un usuario hace clic en tu anuncio y compra ese producto."
                      },
                      {
                        "text": "En cambio, tienes una venta indirecta cuando un usuario hace clic en tu anuncio y compra otro de tus productos."
                      }
                    ]
                  }
                },
                "sell_without_ad": {
                  "number_label": {
                    "text": "0",
                    "color": "black"
                  },
                  "label": {
                    "text": "Ventas sin publicidad",
                    "color": "black",
                    "position": "bottom"
                  },
                  "icon_action": {
                    "id": "sell_without_ad",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Ventas sin publicidad"
                    },
                    "description_blocks": [
                      {
                        "text": "Son las ventas que obtuviste sin publicidad de las publicaciones anunciadas."
                      }
                    ]
                  }
                },
                "switch_field": {
                  "type": "textfield",
                  "value": "sell_without_ad"
                },
                "badge": {
                  "label": {
                    "text": "Publicidad generó el <b>0%</b> de las ventas totales de tus publicaciones anunciadas.",
                    "color": "black",
                    "bg_color": "blue",
                    "position": "left"
                  },
                  "icon_action": {
                    "id": "badge",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Aporte por publicidad"
                    },
                    "description_blocks": [
                      {
                        "text": "Es el porcentaje de ventas que tuviste gracias a Product Ads sobre el total de las ventas de tus anuncios activos."
                      }
                    ]
                  }
                },
                "show_action": {
                  "id": "bar_chart"
                }
              },
              "chart_section": {
                "bar_chart": {
                  "tooltip": {
                    "sell_with_ad": {
                      "text": "Por publicidad"
                    },
                    "sell_without_ad": {
                      "text": "Sin publicidad"
                    },
                    "paused": {
                      "text": "Campaña pausada"
                    }
                  },
                  "data": [
                    {
                      "date": "1 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "1 jul."
                    },
                    {
                      "date": "2 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "2 jul."
                    },
                    {
                      "date": "3 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "3 jul."
                    },
                    {
                      "date": "4 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "4 jul."
                    },
                    {
                      "date": "5 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "5 jul."
                    },
                    {
                      "date": "6 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "6 jul."
                    },
                    {
                      "date": "7 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "7 jul."
                    },
                    {
                      "date": "8 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "8 jul."
                    },
                    {
                      "date": "9 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "9 jul."
                    },
                    {
                      "date": "10 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "10 jul."
                    },
                    {
                      "date": "11 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "11 jul."
                    },
                    {
                      "date": "12 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "12 jul."
                    },
                    {
                      "date": "13 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "13 jul."
                    },
                    {
                      "date": "14 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "14 jul."
                    },
                    {
                      "date": "15 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "15 jul."
                    },
                    {
                      "date": "16 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "16 jul."
                    },
                    {
                      "date": "17 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "17 jul."
                    },
                    {
                      "date": "18 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "18 jul."
                    },
                    {
                      "date": "19 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "19 jul."
                    },
                    {
                      "date": "20 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "20 jul."
                    },
                    {
                      "date": "21 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "21 jul."
                    },
                    {
                      "date": "22 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "22 jul."
                    },
                    {
                      "date": "23 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "23 jul."
                    },
                    {
                      "date": "24 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "24 jul."
                    },
                    {
                      "date": "25 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "25 jul."
                    },
                    {
                      "date": "26 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "26 jul."
                    },
                    {
                      "date": "27 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "27 jul."
                    },
                    {
                      "date": "28 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "28 jul."
                    },
                    {
                      "date": "29 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "29 jul."
                    },
                    {
                      "date": "30 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "30 jul."
                    }
                  ]
                }
              },
              "bottom_section": {
                "impressions": {
                  "number_label": {
                    "text": "0",
                    "color": "black"
                  },
                  "label": {
                    "text": "Impresiones",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "impressions",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Impresiones"
                    },
                    "description_blocks": [
                      {
                        "text": "Cantidad de veces que se muestran tus Product Ads en las páginas de Mercado Libre."
                      }
                    ]
                  }
                },
                "clicks": {
                  "number_label": {
                    "text": "0",
                    "color": "black"
                  },
                  "label": {
                    "text": "Clics",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "clicks",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Clics"
                    },
                    "description_blocks": [
                      {
                        "text": "Cantidad de veces que los usuarios de Mercado Libre hacen clic en tus Product Ads."
                      }
                    ]
                  }
                },
                "income": {
                  "price": {
                    "original_value": "0",
                    "currency_symbol": "$"
                  },
                  "label": {
                    "text": "Ingresos",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "income",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Ingresos"
                    },
                    "description": {
                      "text": "Directos $ 0 | Asistidos $ 0"
                    },
                    "description_blocks": [
                      {
                        "text": "Los ingresos directos son los que obtienes por ventas directas de tus Product Ads."
                      },
                      {
                        "text": "Los ingresos indirectos son los que obtienes por ventas indirectas a través de tus Product Ads."
                      }
                    ]
                  }
                },
                "investment": {
                  "price": {
                    "original_value": "0",
                    "currency_symbol": "$"
                  },
                  "label": {
                    "text": "Inversión",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "income",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Inversión"
                    },
                    "description_blocks": [
                      {
                        "text": "Suma del costo de los clics que recibieron tus Product Ads."
                      }
                    ]
                  }
                },
                "investment_income": {
                  "number_label": {
                    "text": "-",
                    "color": "black"
                  },
                  "label": {
                    "text": "Inversión / Ingresos",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "investment_income",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Inversión / Ingresos"
                    },
                    "description_blocks": [
                      {
                        "text": "Porcentaje de inversión en publicidad sobre los ingresos obtenidos."
                      }
                    ]
                  }
                }
              },
              "lazyload": true
            },
            {
              "type": "filter_campaigns",
              "search_results": {
                "label": {
                  "text": "3 campañas",
                  "disabled": false
                }
              },
              "primary_action": {
                "label": {
                  "text": "Crear campaña"
                },
                "target": "/publicidad/product-ads/admin/campaigns"
              }
            },
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
                },
                {
                  "id": 292463007,
                  "title": {
                    "permalink": "/publicidad/product-ads/admin/dashboard?campaign_id=292463007",
                    "primary_label": {
                      "text": "TEST Changed (Sin Nombre)",
                      "font_weight": "font-weight-semibold",
                      "color": "blue-400",
                      "editable": true
                    },
                    "secondary_label": {
                      "text": "0 anuncios",
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
                          "campaign_name": "TEST Changed (Sin Nombre)",
                          "name_new": "",
                          "campaign_id": 292463007
                        }
                      }
                    },
                    "update_name_event": {
                      "melidata_event": {
                        "path": "/advertising/pads2/hub/campaign/update/name/pencil",
                        "event_data": {
                          "campaign_name": "TEST Changed (Sin Nombre)",
                          "campaign_id": 292463007,
                          "status": "active"
                        }
                      }
                    },
                    "update_campaign_event": {
                      "melidata_event": {
                        "path": "/advertising/pads2/hub/campaign/update/name/go",
                        "event_data": {
                          "campaign_name": "TEST Changed (Sin Nombre)",
                          "name_new": "",
                          "campaign_id": 292463007
                        }
                      }
                    },
                    "update_budget_go_event": {
                      "melidata_event": {
                        "path": "/advertising/pads2/hub/campaign/update/budget/go",
                        "event_data": {
                          "budget_new": "0",
                          "campaign_id": 292463007,
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
                          "campaign_id": 292463007,
                          "budget": 3900,
                          "status": "active"
                        }
                      }
                    },
                    "update_budget_event": {
                      "melidata_event": {
                        "path": "/advertising/pads2/hub/campaign/update/budget/pencil",
                        "event_data": {
                          "campaign_id": 292463007,
                          "budget": 3900,
                          "status": "active"
                        }
                      }
                    }
                  }
                },
                {
                  "id": 292463008,
                  "title": {
                    "permalink": "/publicidad/product-ads/admin/dashboard?campaign_id=292463008",
                    "primary_label": {
                      "text": "TESTMLC (Sin Nombre)",
                      "font_weight": "font-weight-semibold",
                      "color": "blue-400",
                      "editable": true
                    },
                    "secondary_label": {
                      "text": "0 anuncios",
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
                          "campaign_name": "TESTMLC (Sin Nombre)",
                          "name_new": "",
                          "campaign_id": 292463008
                        }
                      }
                    },
                    "update_name_event": {
                      "melidata_event": {
                        "path": "/advertising/pads2/hub/campaign/update/name/pencil",
                        "event_data": {
                          "campaign_name": "TESTMLC (Sin Nombre)",
                          "campaign_id": 292463008,
                          "status": "active"
                        }
                      }
                    },
                    "update_campaign_event": {
                      "melidata_event": {
                        "path": "/advertising/pads2/hub/campaign/update/name/go",
                        "event_data": {
                          "campaign_name": "TESTMLC (Sin Nombre)",
                          "name_new": "",
                          "campaign_id": 292463008
                        }
                      }
                    },
                    "update_budget_go_event": {
                      "melidata_event": {
                        "path": "/advertising/pads2/hub/campaign/update/budget/go",
                        "event_data": {
                          "budget_new": "0",
                          "campaign_id": 292463008,
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
                          "campaign_id": 292463008,
                          "budget": 3900,
                          "status": "active"
                        }
                      }
                    },
                    "update_budget_event": {
                      "melidata_event": {
                        "path": "/advertising/pads2/hub/campaign/update/budget/pencil",
                        "event_data": {
                          "campaign_id": 292463008,
                          "budget": 3900,
                          "status": "active"
                        }
                      }
                    }
                  }
                }
              ],
              "paging": {
                "total": 3,
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
          ],
          "tracks": {
            "select_tab": {
              "melidata_event": {
                "path": "/advertising/pads2/hub",
                "event_data": {
                  "tab": "campaigns",
                  "campaigns": [
                    {
                      "campaign_id": 292913103,
                      "budget": 3900,
                      "status": "active"
                    },
                    {
                      "campaign_id": 292463007,
                      "budget": 3900,
                      "status": "active"
                    },
                    {
                      "campaign_id": 292463008,
                      "budget": 3900,
                      "status": "active"
                    }
                  ]
                }
              }
            }
          }
        },
        {
          "type": "tab_pads",
          "title": {
            "text": "Anuncios"
          },
          "components": [
            {
              "id": "date_range_tab_pads",
              "type": "date_range",
              "title": {
                "text": "Métricas"
              },
              "selector": {
                "disabled": false,
                "month_calendar_list": [
                  "Enero",
                  "Febrero",
                  "Marzo",
                  "Abril",
                  "Mayo",
                  "Junio",
                  "Julio",
                  "Agosto",
                  "Septiembre",
                  "Octubre",
                  "Noviembre",
                  "Diciembre"
                ],
                "days_of_week": [
                  "D",
                  "L",
                  "M",
                  "M",
                  "J",
                  "V",
                  "S"
                ],
                "default_label": {
                  "label": {
                    "text": "Últimos 30 días"
                  },
                  "value": "30_days",
                  "date": {
                    "to": "2020-07-30",
                    "from": "2020-07-01"
                  }
                },
                "options": [
                  {
                    "date": {
                      "to": "2020-07-30",
                      "from": "2020-05-02"
                    },
                    "label": {
                      "text": "Últimos 90 días",
                      "disabled": false
                    },
                    "value": "90_days",
                    "disabled": false
                  },
                  {
                    "date": {
                      "to": "2020-07-30",
                      "from": "2020-06-01"
                    },
                    "label": {
                      "text": "Últimos 60 días",
                      "disabled": false
                    },
                    "value": "60_days",
                    "disabled": false
                  },
                  {
                    "date": {
                      "to": "2020-07-30",
                      "from": "2020-07-01"
                    },
                    "label": {
                      "text": "Últimos 30 días",
                      "disabled": false
                    },
                    "value": "30_days",
                    "disabled": false
                  },
                  {
                    "date": {
                      "to": "2020-07-30",
                      "from": "2020-07-24"
                    },
                    "label": {
                      "text": "Últimos 7 días",
                      "disabled": false
                    },
                    "value": "7_days",
                    "disabled": false
                  },
                  {
                    "date": {},
                    "label": {
                      "text": "Personalizado",
                      "disabled": false
                    },
                    "value": "custom_days",
                    "disabled": false
                  }
                ]
              }
            },
            {
              "id": "lift_chart_tab_pads",
              "type": "lift_chart",
              "title": {
                "text": "Metricas totales",
                "color": "black"
              },
              "top_section": {
                "sell_with_ad": {
                  "number_label": {
                    "text": "0",
                    "color": "black"
                  },
                  "label": {
                    "text": "Ventas por publicidad",
                    "color": "black",
                    "position": "bottom"
                  },
                  "icon_action": {
                    "id": "sell_with_ad",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda",
                      "url": "https://http2.mlstatic.com/resources/frontend/statics/admin-pa-frontend/images/question.svg"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Ventas por publicidad"
                    },
                    "description": {
                      "text": "Directos  0 | Asistidos 0"
                    },
                    "description_blocks": [
                      {
                        "text": "Tienes una venta directa cuando un usuario hace clic en tu anuncio y compra ese producto."
                      },
                      {
                        "text": "En cambio, tienes una venta indirecta cuando un usuario hace clic en tu anuncio y compra otro de tus productos."
                      }
                    ]
                  }
                },
                "sell_without_ad": {
                  "number_label": {
                    "text": "0",
                    "color": "black"
                  },
                  "label": {
                    "text": "Ventas sin publicidad",
                    "color": "black",
                    "position": "bottom"
                  },
                  "icon_action": {
                    "id": "sell_without_ad",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Ventas sin publicidad"
                    },
                    "description_blocks": [
                      {
                        "text": "Son las ventas que obtuviste sin publicidad de las publicaciones anunciadas."
                      }
                    ]
                  }
                },
                "switch_field": {
                  "type": "textfield",
                  "value": "sell_without_ad"
                },
                "badge": {
                  "label": {
                    "text": "Publicidad generó el <b>0%</b> de las ventas totales de tus publicaciones anunciadas.",
                    "color": "black",
                    "bg_color": "blue",
                    "position": "left"
                  },
                  "icon_action": {
                    "id": "badge",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Aporte por publicidad"
                    },
                    "description_blocks": [
                      {
                        "text": "Es el porcentaje de ventas que tuviste gracias a Product Ads sobre el total de las ventas de tus anuncios activos."
                      }
                    ]
                  }
                },
                "show_action": {
                  "id": "bar_chart"
                }
              },
              "chart_section": {
                "bar_chart": {
                  "tooltip": {
                    "sell_with_ad": {
                      "text": "Por publicidad"
                    },
                    "sell_without_ad": {
                      "text": "Sin publicidad"
                    },
                    "paused": {
                      "text": "Campaña pausada"
                    }
                  },
                  "data": [
                    {
                      "date": "1 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "1 jul."
                    },
                    {
                      "date": "2 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "2 jul."
                    },
                    {
                      "date": "3 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "3 jul."
                    },
                    {
                      "date": "4 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "4 jul."
                    },
                    {
                      "date": "5 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "5 jul."
                    },
                    {
                      "date": "6 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "6 jul."
                    },
                    {
                      "date": "7 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "7 jul."
                    },
                    {
                      "date": "8 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "8 jul."
                    },
                    {
                      "date": "9 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "9 jul."
                    },
                    {
                      "date": "10 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "10 jul."
                    },
                    {
                      "date": "11 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "11 jul."
                    },
                    {
                      "date": "12 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "12 jul."
                    },
                    {
                      "date": "13 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "13 jul."
                    },
                    {
                      "date": "14 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "14 jul."
                    },
                    {
                      "date": "15 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "15 jul."
                    },
                    {
                      "date": "16 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "16 jul."
                    },
                    {
                      "date": "17 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "17 jul."
                    },
                    {
                      "date": "18 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "18 jul."
                    },
                    {
                      "date": "19 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "19 jul."
                    },
                    {
                      "date": "20 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "20 jul."
                    },
                    {
                      "date": "21 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "21 jul."
                    },
                    {
                      "date": "22 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "22 jul."
                    },
                    {
                      "date": "23 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "23 jul."
                    },
                    {
                      "date": "24 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "24 jul."
                    },
                    {
                      "date": "25 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "25 jul."
                    },
                    {
                      "date": "26 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "26 jul."
                    },
                    {
                      "date": "27 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "27 jul."
                    },
                    {
                      "date": "28 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "28 jul."
                    },
                    {
                      "date": "29 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "29 jul."
                    },
                    {
                      "date": "30 jul 2020",
                      "sell_with_ad": "0",
                      "sell_without_ad": "0",
                      "impressions": "0",
                      "label": "30 jul."
                    }
                  ]
                }
              },
              "bottom_section": {
                "impressions": {
                  "number_label": {
                    "text": "0",
                    "color": "black"
                  },
                  "label": {
                    "text": "Impresiones",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "impressions",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Impresiones"
                    },
                    "description_blocks": [
                      {
                        "text": "Cantidad de veces que se muestran tus Product Ads en las páginas de Mercado Libre."
                      }
                    ]
                  }
                },
                "clicks": {
                  "number_label": {
                    "text": "0",
                    "color": "black"
                  },
                  "label": {
                    "text": "Clics",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "clicks",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Clics"
                    },
                    "description_blocks": [
                      {
                        "text": "Cantidad de veces que los usuarios de Mercado Libre hacen clic en tus Product Ads."
                      }
                    ]
                  }
                },
                "income": {
                  "price": {
                    "original_value": "0",
                    "currency_symbol": "$"
                  },
                  "label": {
                    "text": "Ingresos",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "income",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Ingresos"
                    },
                    "description": {
                      "text": "Directos $ 0 | Asistidos $ 0"
                    },
                    "description_blocks": [
                      {
                        "text": "Los ingresos directos son los que obtienes por ventas directas de tus Product Ads."
                      },
                      {
                        "text": "Los ingresos indirectos son los que obtienes por ventas indirectas a través de tus Product Ads."
                      }
                    ]
                  }
                },
                "investment": {
                  "price": {
                    "original_value": "0",
                    "currency_symbol": "$"
                  },
                  "label": {
                    "text": "Inversión",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "income",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Inversión"
                    },
                    "description_blocks": [
                      {
                        "text": "Suma del costo de los clics que recibieron tus Product Ads."
                      }
                    ]
                  }
                },
                "investment_income": {
                  "number_label": {
                    "text": "-",
                    "color": "black"
                  },
                  "label": {
                    "text": "Inversión / Ingresos",
                    "color": "black",
                    "position": "top"
                  },
                  "icon_action": {
                    "id": "investment_income",
                    "icon": {
                      "id": "question",
                      "alt": "Necesito ayuda"
                    }
                  },
                  "tooltip": {
                    "visible": false,
                    "title": {
                      "text": "Inversión / Ingresos"
                    },
                    "description_blocks": [
                      {
                        "text": "Porcentaje de inversión en publicidad sobre los ingresos obtenidos."
                      }
                    ]
                  }
                }
              },
              "lazyload": true
            },
            {
              "type": "filter_pads",
              "filter_action": {
                "id": "modal_id",
                "label": {
                  "text": "Filtrar"
                },
                "icon": {
                  "id": "filter_icon",
                  "url": "https://http2.mlstatic.com/resources/frontend/statics/admin-pa-frontend/images/filtro.svg"
                }
              },
              "search_field": {
                "id": "query",
                "type": "search",
                "placeholder": "Buscar por título del anuncio",
                "value": ""
              }
            },
            {
              "type": "massive_selector_pads",
              "select_field": {
                "id": "many",
                "value": "selected_pads",
                "checked": false,
                "disabled": false
              },
              "selected_pads": {
                "initial": {
                  "text": "Selecciona anuncios para accionar masivamente"
                },
                "none": {
                  "text": "Sin anuncios"
                },
                "one": {
                  "text": "1 anuncio seleccionado"
                },
                "many": {
                  "text": "{0} anuncios seleccionados"
                }
              },
              "all_action": {
                "text": "Seleccionar los {0} anuncios"
              },
              "primary_action": {
                "id": "active",
                "label": {
                  "text": "Activar anuncios"
                }
              },
              "selector": {
                "initial": {
                  "label": {
                    "text": "Más acciones"
                  }
                },
                "options": [
                  {
                    "label": {
                      "text": "Pausar"
                    },
                    "value": "pause",
                    "disabled": false
                  },
                  {
                    "label": {
                      "text": "Mover a una campaña"
                    },
                    "value": "move",
                    "disabled": false
                  },
                  {
                    "label": {
                      "text": "Crear campaña"
                    },
                    "value": "create",
                    "disabled": false
                  }
                ]
              },
              "confirmation_modal": {
                "title": {
                  "text": "¡Atención!"
                },
                "description": {
                  "text": "Por el momento, sólo podemos accionar en tus primeros 10.000 anuncios seleccionados."
                },
                "confirmation_action": {
                  "label": {
                    "text": "Continuar"
                  }
                },
                "cancel_action": {
                  "label": {
                    "text": "Cancelar"
                  }
                }
              },
              "loading": {
                "text": "Procesando, aguarda un momento"
              },
              "tracks": {
                "tab_pads_massive_actions": {
                  "melidata_event": {
                    "path": "/advertising/pads2/hub/massive_actions",
                    "event_data": {
                      "action": "",
                      "total_items": "0"
                    }
                  }
                }
              }
            },
            {
              "type": "table_ads",
              "header": [],
              "rows": [],
              "paging": {
                "total": 0,
                "offset": 0,
                "limit": 50
              }
            },
            {
              "type": "campaign_single_list",
              "title": {
                "text": "Elige la campaña de destino",
                "color": "black"
              },
              "subtitle": {
                "one": {
                  "text": "Moverás <b>1 anuncio</b> hacia otra campaña",
                  "color": "black"
                },
                "many": {
                  "text": "Moverás <b>{0} anuncios</b> hacia otra campaña",
                  "color": "black"
                }
              },
              "loading": {
                "text": "Cargando tus campañas"
              },
              "input_search": {
                "label": {
                  "text": "Buscar por título de campaña"
                }
              },
              "selected": {},
              "campaigns": [],
              "check_to_activate": {
                "label": "Activar anuncios al moverlos de campaña",
                "checked": true
              },
              "confirmation_action": {
                "label": {
                  "text": "Mover anuncios",
                  "color": "white",
                  "bg_color": "blue"
                }
              },
              "cancel_action": {
                "label": {
                  "text": "Cancelar",
                  "color": "white"
                }
              },
              "campaigns_not_found": {
                "img": {
                  "src": "https://http2.mlstatic.com/resources/frontend/statics/admin-pa-frontend/images/busqueda-fail.svg"
                },
                "message": {
                  "text": "No encontramos campañas que coincidan con tu búsqueda."
                }
              },
              "paging": {
                "total": 3,
                "offset": 0,
                "limit": 50
              },
              "metadata": {
                "loading_massive_move_pads": {
                  "text": "Moviendo tus anuncios"
                }
              }
            }
          ]
        }
      ]
    },
    {
      "type": "update_budget_modal",
      "title": {
        "text": "Presupuesto de tu campaña",
        "color": "black"
      },
      "description": {
        "text": "Elige cuánto quieres invertir por día. Podrás cambiar tu presupuesto cuando quieras.",
        "color": "black"
      },
      "field": {
        "type": "number",
        "placeholder": "Introduce un monto",
        "currency_symbol": "$",
        "validations": {
          "pattern": "^[0-9]+$",
          "required": true,
          "messages": [
            {
              "id": "required_error",
              "text": "Ingresa un monto",
              "color": "red"
            },
            {
              "id": "min_error",
              "text": "Ingresa el valor $ 3.900",
              "color": "red"
            },
            {
              "id": "max_error",
              "text": "Ingresa el valor $ 3.900",
              "color": "red"
            }
          ],
          "min": 3900,
          "max": 3900
        }
      },
      "confirm_action": {
        "id": "confirm",
        "label": {
          "text": "Confirmar",
          "color": "white"
        }
      },
      "cancel_action": {
        "id": "cancel",
        "label": {
          "text": "Cancelar",
          "color": "blue"
        }
      }
    },
    {
      "type": "update_name_modal",
      "title": {
        "text": "Nombre de tu campaña",
        "color": "black"
      },
      "description": {
        "text": "El nombre de tu campaña te permitirá identificar más rápido los anuncios que agrupaste.",
        "color": "black"
      },
      "field": {
        "type": "text",
        "placeholder": "Introduce un nombre",
        "validations": {
          "pattern": "^[a-zA-Z\\u00C0-\\u00FF\\-\\s(0-9)]*$",
          "required": true,
          "messages": [
            {
              "id": "required_error",
              "text": "Ingresa un valor",
              "color": "red"
            }
          ],
          "min": 0,
          "max": 30
        }
      },
      "confirm_action": {
        "id": "confirm",
        "label": {
          "text": "Confirmar",
          "color": "white"
        }
      },
      "cancel_action": {
        "id": "cancel",
        "label": {
          "text": "Cancelar",
          "color": "blue"
        }
      }
    }
  ],
  "picture_config": {
    "template_icon": "https://http2.mlstatic.com/resources/frontend/statics/admin-pa-frontend/images/{id}.svg",
    "template_pad": "https://http2.mlstatic.com/S_Q_NP_{id}-N.jpg"
  }
}
```
