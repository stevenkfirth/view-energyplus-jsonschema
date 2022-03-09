```
{
    "GroundHeatExchanger:ResponseFactors": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "ghe_vertical_properties_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "GroundHeatExchangerVerticalPropertiesNames"
                        ]
                    },
                    "number_of_boreholes": {
                        "type": "number"
                    },
                    "g_function_reference_ratio": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "dimensionless",
                        "default": 0.0005
                    },
                    "g_functions": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "g_function_ln_t_ts_value": {
                                    "type": "number"
                                },
                                "g_function_g_value": {
                                    "type": "number"
                                }
                            },
                            "type": "object",
                            "required": [
                                "g_function_g_value",
                                "g_function_ln_t_ts_value"
                            ]
                        }
                    }
                },
                "required": [
                    "ghe_vertical_properties_object_name",
                    "number_of_boreholes"
                ]
            }
        },
        "group": "Condenser Equipment and Heat Exchangers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "GroundHeatExchangerVerticalResponseFactorNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "ghe_vertical_properties_object_name": {
                    "field_name": "GHE:Vertical:Properties Object Name",
                    "field_type": "a"
                },
                "number_of_boreholes": {
                    "field_name": "Number of Boreholes",
                    "field_type": "n"
                },
                "g_function_reference_ratio": {
                    "field_name": "G-Function Reference Ratio",
                    "field_type": "n"
                },
                "g_function_ln_t_ts_value": {
                    "field_name": "g-Function Ln(T/Ts) Value",
                    "field_type": "n"
                },
                "g_function_g_value": {
                    "field_name": "g-Function g Value",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "ghe_vertical_properties_object_name",
                "number_of_boreholes",
                "g_function_reference_ratio"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "ghe_vertical_properties_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_boreholes",
                    "g_function_reference_ratio"
                ],
                "extensions": [
                    "g_function_ln_t_ts_value",
                    "g_function_g_value"
                ]
            },
            "extensibles": [
                "g_function_ln_t_ts_value",
                "g_function_g_value"
            ],
            "extension": "g_functions"
        },
        "type": "object",
        "memo": "Response factor definitions from third-party tool, commonly referred to a \"g-functions\"",
        "min_fields": 5.0,
        "extensible_size": 2.0
    }
}
```
