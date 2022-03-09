```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "temperature_data": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "optical_data_temperature": {
                                "type": "number",
                                "units": "C",
                                "ip-units": "F"
                            },
                            "window_material_glazing_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "GlazingMaterialName"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "optical_data_temperature",
                            "window_material_glazing_name"
                        ]
                    }
                }
            }
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "GlazingMaterialName",
            "MaterialName"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "optical_data_temperature": {
                "field_name": "Optical Data Temperature",
                "field_type": "n"
            },
            "window_material_glazing_name": {
                "field_name": "Window Material Glazing Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name"
        ],
        "alphas": {
            "fields": [
                "name"
            ],
            "extensions": [
                "window_material_glazing_name"
            ]
        },
        "numerics": {
            "fields": [],
            "extensions": [
                "optical_data_temperature"
            ]
        },
        "extensibles": [
            "optical_data_temperature",
            "window_material_glazing_name"
        ],
        "extension": "temperature_data"
    },
    "type": "object",
    "memo": "thermochromic glass at different temperatures",
    "min_fields": 3.0,
    "extensible_size": 2.0
}
```
