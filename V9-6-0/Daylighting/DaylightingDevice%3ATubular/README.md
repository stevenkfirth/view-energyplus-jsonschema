```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "dome_name": {
                    "type": "string",
                    "note": "This must refer to a subsurface object of type TubularDaylightDome",
                    "data_type": "object_list",
                    "object_list": [
                        "SubSurfNames"
                    ]
                },
                "diffuser_name": {
                    "type": "string",
                    "note": "This must refer to a subsurface object of type TubularDaylightDiffuser Delivery zone is specified in the diffuser object",
                    "data_type": "object_list",
                    "object_list": [
                        "SubSurfNames"
                    ]
                },
                "construction_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ConstructionNames"
                    ]
                },
                "diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "total_length": {
                    "type": "number",
                    "note": "The exterior exposed length is the difference between total and sum of zone lengths",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "effective_thermal_resistance": {
                    "type": "number",
                    "note": "R value between TubularDaylightDome and TubularDaylightDiffuser",
                    "units": "m2-K/W",
                    "exclusiveMinimum": 0.0,
                    "default": 0.28
                },
                "transition_lengths": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "transition_zone_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "ZoneNames"
                                ]
                            },
                            "transition_zone_length": {
                                "type": "number",
                                "units": "m",
                                "minimum": 0.0
                            }
                        },
                        "type": "object"
                    }
                }
            },
            "required": [
                "dome_name",
                "diffuser_name",
                "construction_name",
                "diameter",
                "total_length"
            ]
        }
    },
    "group": "Daylighting",
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
            "dome_name": {
                "field_name": "Dome Name",
                "field_type": "a"
            },
            "diffuser_name": {
                "field_name": "Diffuser Name",
                "field_type": "a"
            },
            "construction_name": {
                "field_name": "Construction Name",
                "field_type": "a"
            },
            "diameter": {
                "field_name": "Diameter",
                "field_type": "n"
            },
            "total_length": {
                "field_name": "Total Length",
                "field_type": "n"
            },
            "effective_thermal_resistance": {
                "field_name": "Effective Thermal Resistance",
                "field_type": "n"
            },
            "transition_zone_name": {
                "field_name": "Transition Zone Name",
                "field_type": "a"
            },
            "transition_zone_length": {
                "field_name": "Transition Zone Length",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "dome_name",
            "diffuser_name",
            "construction_name",
            "diameter",
            "total_length",
            "effective_thermal_resistance"
        ],
        "alphas": {
            "fields": [
                "name",
                "dome_name",
                "diffuser_name",
                "construction_name"
            ],
            "extensions": [
                "transition_zone_name"
            ]
        },
        "numerics": {
            "fields": [
                "diameter",
                "total_length",
                "effective_thermal_resistance"
            ],
            "extensions": [
                "transition_zone_length"
            ]
        },
        "extensibles": [
            "transition_zone_name",
            "transition_zone_length"
        ],
        "extension": "transition_lengths"
    },
    "type": "object",
    "memo": "Defines a tubular daylighting device (TDD) consisting of three components: a dome, a pipe, and a diffuser. The dome and diffuser are defined separately using the FenestrationSurface:Detailed object.",
    "min_fields": 7.0,
    "extensible_size": 2.0
}
```
