```
{
    "GroundHeatExchanger:Vertical:Single": {
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
                    "x_location": {
                        "type": "number",
                        "units": "m"
                    },
                    "y_location": {
                        "type": "number",
                        "units": "m"
                    }
                },
                "required": [
                    "ghe_vertical_properties_object_name",
                    "x_location",
                    "y_location"
                ]
            }
        },
        "group": "Condenser Equipment and Heat Exchangers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "GroundHeatExchangerVerticalSingleNames"
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
                "x_location": {
                    "field_name": "X-Location",
                    "field_type": "n"
                },
                "y_location": {
                    "field_name": "Y-Location",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "ghe_vertical_properties_object_name",
                "x_location",
                "y_location"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "ghe_vertical_properties_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "x_location",
                    "y_location"
                ]
            }
        },
        "type": "object"
    }
}
```
