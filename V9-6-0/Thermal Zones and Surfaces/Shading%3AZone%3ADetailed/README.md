```
{
    "Shading:Zone:Detailed": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "base_surface_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SurfaceNames"
                        ]
                    },
                    "transmittance_schedule_name": {
                        "type": "string",
                        "note": "Transmittance schedule for the shading device, defaults to zero (always opaque)",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "number_of_vertices": {
                        "note": "shown with 6 vertex coordinates -- extensible object vertices are given in GlobalGeometryRules coordinates -- if relative, all surface coordinates are \"relative\" to the Zone Origin. if world, then building and zone origins are used for some internal calculations, but all coordinates are given in an \"absolute\" system.",
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
                },
                "required": [
                    "base_surface_name"
                ]
            }
        },
        "group": "Thermal Zones and Surfaces",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AllShadingAndHTSurfNames",
                "AllShadingSurfNames",
                "AttachedShadingSurfNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "base_surface_name": {
                    "field_name": "Base Surface Name",
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
                "base_surface_name",
                "transmittance_schedule_name",
                "number_of_vertices"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "base_surface_name",
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
        "memo": "used For fins, overhangs, elements that shade the building, are attached to the building but are not part of the heat transfer calculations",
        "min_fields": 13.0,
        "extensible_size": 3.0,
        "format": "vertices"
    }
}
```
