```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "tariff_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UtilityCostTariffs"
                    ],
                    "note": "The name of the UtilityCost:Tariff that is associated with this UtilityCost:Variable."
                },
                "variable_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Currency",
                        "Demand",
                        "Dimensionless",
                        "Energy"
                    ],
                    "default": "Dimensionless"
                },
                "january_value": {
                    "type": "number"
                },
                "february_value": {
                    "type": "number"
                },
                "march_value": {
                    "type": "number"
                },
                "april_value": {
                    "type": "number"
                },
                "may_value": {
                    "type": "number"
                },
                "june_value": {
                    "type": "number"
                },
                "july_value": {
                    "type": "number"
                },
                "august_value": {
                    "type": "number"
                },
                "september_value": {
                    "type": "number"
                },
                "october_value": {
                    "type": "number"
                },
                "november_value": {
                    "type": "number"
                },
                "december_value": {
                    "type": "number"
                }
            },
            "required": [
                "tariff_name"
            ]
        }
    },
    "group": "Economics",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "tariff_name": {
                "field_name": "Tariff Name",
                "field_type": "a"
            },
            "variable_type": {
                "field_name": "Variable Type",
                "field_type": "a"
            },
            "january_value": {
                "field_name": "January Value",
                "field_type": "n"
            },
            "february_value": {
                "field_name": "February Value",
                "field_type": "n"
            },
            "march_value": {
                "field_name": "March Value",
                "field_type": "n"
            },
            "april_value": {
                "field_name": "April Value",
                "field_type": "n"
            },
            "may_value": {
                "field_name": "May Value",
                "field_type": "n"
            },
            "june_value": {
                "field_name": "June Value",
                "field_type": "n"
            },
            "july_value": {
                "field_name": "July Value",
                "field_type": "n"
            },
            "august_value": {
                "field_name": "August Value",
                "field_type": "n"
            },
            "september_value": {
                "field_name": "September Value",
                "field_type": "n"
            },
            "october_value": {
                "field_name": "October Value",
                "field_type": "n"
            },
            "november_value": {
                "field_name": "November Value",
                "field_type": "n"
            },
            "december_value": {
                "field_name": "December Value",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "tariff_name",
            "variable_type",
            "january_value",
            "february_value",
            "march_value",
            "april_value",
            "may_value",
            "june_value",
            "july_value",
            "august_value",
            "september_value",
            "october_value",
            "november_value",
            "december_value"
        ],
        "alphas": {
            "fields": [
                "name",
                "tariff_name",
                "variable_type"
            ]
        },
        "numerics": {
            "fields": [
                "january_value",
                "february_value",
                "march_value",
                "april_value",
                "may_value",
                "june_value",
                "july_value",
                "august_value",
                "september_value",
                "october_value",
                "november_value",
                "december_value"
            ]
        }
    },
    "type": "object",
    "memo": "Allows for the direct entry of monthly values into a utility tariff variable.",
    "min_fields": 3.0
}
```
