```
{
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
                "number_of_boreholes_in_x_direction": {
                    "type": "number",
                    "minimum": 1.0
                },
                "number_of_boreholes_in_y_direction": {
                    "type": "number",
                    "minimum": 1.0
                },
                "borehole_spacing": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m"
                }
            },
            "required": [
                "ghe_vertical_properties_object_name",
                "number_of_boreholes_in_x_direction",
                "number_of_boreholes_in_y_direction",
                "borehole_spacing"
            ]
        }
    },
    "group": "Condenser Equipment and Heat Exchangers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "GroundHeatExchangerVerticalArrayNames"
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
            "number_of_boreholes_in_x_direction": {
                "field_name": "Number of Boreholes in X-Direction",
                "field_type": "n"
            },
            "number_of_boreholes_in_y_direction": {
                "field_name": "Number of Boreholes in Y-Direction",
                "field_type": "n"
            },
            "borehole_spacing": {
                "field_name": "Borehole Spacing",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "ghe_vertical_properties_object_name",
            "number_of_boreholes_in_x_direction",
            "number_of_boreholes_in_y_direction",
            "borehole_spacing"
        ],
        "alphas": {
            "fields": [
                "name",
                "ghe_vertical_properties_object_name"
            ]
        },
        "numerics": {
            "fields": [
                "number_of_boreholes_in_x_direction",
                "number_of_boreholes_in_y_direction",
                "borehole_spacing"
            ]
        }
    },
    "type": "object"
}
```
