```
{
    "SurfaceProperty:SurroundingSurfaces": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "sky_view_factor": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.5,
                        "note": "optional"
                    },
                    "sky_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values are real numbers, -100.0 to 100.0, units C optional"
                    },
                    "ground_view_factor": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.5,
                        "note": "optional"
                    },
                    "ground_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values are real numbers, -100.0 to 100.0, units C optional"
                    },
                    "surfaces": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "surrounding_surface_name": {
                                    "type": "string"
                                },
                                "surrounding_surface_view_factor": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 1.0,
                                    "default": 0.0
                                },
                                "surrounding_surface_temperature_schedule_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "ScheduleNames"
                                    ],
                                    "note": "Schedule values are real numbers, -100.0 to 100.0, units C"
                                }
                            },
                            "type": "object",
                            "required": [
                                "surrounding_surface_name",
                                "surrounding_surface_temperature_schedule_name",
                                "surrounding_surface_view_factor"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SurroundingSurfacesNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "sky_view_factor": {
                    "field_name": "Sky View Factor",
                    "field_type": "n"
                },
                "sky_temperature_schedule_name": {
                    "field_name": "Sky Temperature Schedule Name",
                    "field_type": "a"
                },
                "ground_view_factor": {
                    "field_name": "Ground View Factor",
                    "field_type": "n"
                },
                "ground_temperature_schedule_name": {
                    "field_name": "Ground Temperature Schedule Name",
                    "field_type": "a"
                },
                "surrounding_surface_name": {
                    "field_name": "Surrounding Surface Name",
                    "field_type": "a"
                },
                "surrounding_surface_view_factor": {
                    "field_name": "Surrounding Surface View Factor",
                    "field_type": "n"
                },
                "surrounding_surface_temperature_schedule_name": {
                    "field_name": "Surrounding Surface Temperature Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "sky_view_factor",
                "sky_temperature_schedule_name",
                "ground_view_factor",
                "ground_temperature_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "sky_temperature_schedule_name",
                    "ground_temperature_schedule_name"
                ],
                "extensions": [
                    "surrounding_surface_name",
                    "surrounding_surface_temperature_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "sky_view_factor",
                    "ground_view_factor"
                ],
                "extensions": [
                    "surrounding_surface_view_factor"
                ]
            },
            "extensibles": [
                "surrounding_surface_name",
                "surrounding_surface_view_factor",
                "surrounding_surface_temperature_schedule_name"
            ],
            "extension": "surfaces"
        },
        "type": "object",
        "memo": "This object defines a list of surrounding surfaces for an exterior surface.",
        "min_fields": 8.0,
        "extensible_size": 3.0
    }
}
```
