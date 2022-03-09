```
{
    "ZoneHVAC:LowTemperatureRadiant:SurfaceGroup": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "surface_fractions": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "surface_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "RadiantSurfaceNames"
                                    ]
                                },
                                "flow_fraction_for_surface": {
                                    "type": "number",
                                    "minimum": 0.0
                                }
                            },
                            "type": "object",
                            "required": [
                                "flow_fraction_for_surface",
                                "surface_name"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Zone HVAC Radiative/Convective Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "RadiantGroupNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "surface_name": {
                    "field_name": "Surface Name",
                    "field_type": "a"
                },
                "flow_fraction_for_surface": {
                    "field_name": "Flow Fraction for Surface",
                    "field_type": "n"
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
                    "surface_name"
                ]
            },
            "numerics": {
                "fields": [],
                "extensions": [
                    "flow_fraction_for_surface"
                ]
            },
            "extensibles": [
                "surface_name",
                "flow_fraction_for_surface"
            ],
            "extension": "surface_fractions"
        },
        "type": "object",
        "memo": "This is used to allow the coordinate control of several radiant system surfaces. Note that the following flow fractions must sum up to 1.0 The number of surfaces can be expanded beyond 100, if necessary, by adding more groups to the end of the list",
        "extensible_size": 2.0
    }
}
```
