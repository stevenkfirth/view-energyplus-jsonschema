```
{
    "Shading:Building:Detailed": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "transmittance_schedule_name": {
                        "type": "string",
                        "note": "Transmittance schedule for the shading device, defaults to zero (always opaque)",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "number_of_vertices": {
                        "note": "shown with 6 vertex coordinates -- extensible object Rules for vertices are given in GlobalGeometryRules coordinates -- For this object all surface coordinates are relative to the building origin (0,0,0) and will rotate with the BUILDING north axis.",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 3.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "vertices": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "vertex_x_coordinate": {
                                    "type": "number",
                                    "units": "m"
                                },
                                "vertex_y_coordinate": {
                                    "type": "number",
                                    "units": "m"
                                },
                                "vertex_z_coordinate": {
                                    "type": "number",
                                    "units": "m"
                                }
                            },
                            "type": "object",
                            "required": [
                                "vertex_x_coordinate",
                                "vertex_y_coordinate",
                                "vertex_z_coordinate"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Thermal Zones and Surfaces",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AllShadingAndHTSurfNames",
                "AllShadingSurfNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "transmittance_schedule_name": {
                    "field_name": "Transmittance Schedule Name",
                    "field_type": "a"
                },
                "number_of_vertices": {
                    "field_name": "Number of Vertices",
                    "field_type": "n"
                },
                "vertex_x_coordinate": {
                    "field_name": "Vertex X-coordinate",
                    "field_type": "n"
                },
                "vertex_y_coordinate": {
                    "field_name": "Vertex Y-coordinate",
                    "field_type": "n"
                },
                "vertex_z_coordinate": {
                    "field_name": "Vertex Z-coordinate",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "transmittance_schedule_name",
                "number_of_vertices"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "transmittance_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_vertices"
                ],
                "extensions": [
                    "vertex_x_coordinate",
                    "vertex_y_coordinate",
                    "vertex_z_coordinate"
                ]
            },
            "extensibles": [
                "vertex_x_coordinate",
                "vertex_y_coordinate",
                "vertex_z_coordinate"
            ],
            "extension": "vertices"
        },
        "type": "object",
        "memo": "used for shading elements such as trees, other buildings, parts of this building not being modeled these items are relative to the current building and would move with relative geometry",
        "min_fields": 12.0,
        "extensible_size": 3.0,
        "format": "vertices"
    }
}
```
