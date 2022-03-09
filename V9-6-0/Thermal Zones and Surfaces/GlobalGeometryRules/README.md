```
{
    "GlobalGeometryRules": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "starting_vertex_position": {
                        "type": "string",
                        "note": "Specified as entry for a 4 sided surface/rectangle Surfaces are specified as viewed from outside the surface Shading surfaces as viewed from behind. (towards what they are shading)",
                        "enum": [
                            "LowerLeftCorner",
                            "LowerRightCorner",
                            "UpperLeftCorner",
                            "UpperRightCorner"
                        ]
                    },
                    "vertex_entry_direction": {
                        "type": "string",
                        "enum": [
                            "Clockwise",
                            "Counterclockwise"
                        ]
                    },
                    "coordinate_system": {
                        "type": "string",
                        "note": "Relative -- coordinates are entered relative to zone origin World -- all coordinates entered are \"absolute\" for this facility",
                        "enum": [
                            "Relative",
                            "World"
                        ]
                    },
                    "daylighting_reference_point_coordinate_system": {
                        "type": "string",
                        "enum": [
                            "",
                            "Relative",
                            "World"
                        ],
                        "default": "Relative",
                        "note": "Relative -- coordinates are entered relative to zone origin World -- all coordinates entered are \"absolute\" for this facility"
                    },
                    "rectangular_surface_coordinate_system": {
                        "type": "string",
                        "enum": [
                            "",
                            "Relative",
                            "World"
                        ],
                        "default": "Relative",
                        "note": "Relative -- Starting corner is entered relative to zone origin World -- Starting corner is entered in \"absolute\""
                    }
                },
                "required": [
                    "starting_vertex_position",
                    "vertex_entry_direction",
                    "coordinate_system"
                ]
            }
        },
        "group": "Thermal Zones and Surfaces",
        "legacy_idd": {
            "field_info": {
                "starting_vertex_position": {
                    "field_name": "Starting Vertex Position",
                    "field_type": "a"
                },
                "vertex_entry_direction": {
                    "field_name": "Vertex Entry Direction",
                    "field_type": "a"
                },
                "coordinate_system": {
                    "field_name": "Coordinate System",
                    "field_type": "a"
                },
                "daylighting_reference_point_coordinate_system": {
                    "field_name": "Daylighting Reference Point Coordinate System",
                    "field_type": "a"
                },
                "rectangular_surface_coordinate_system": {
                    "field_name": "Rectangular Surface Coordinate System",
                    "field_type": "a"
                }
            },
            "fields": [
                "starting_vertex_position",
                "vertex_entry_direction",
                "coordinate_system",
                "daylighting_reference_point_coordinate_system",
                "rectangular_surface_coordinate_system"
            ],
            "alphas": {
                "fields": [
                    "starting_vertex_position",
                    "vertex_entry_direction",
                    "coordinate_system",
                    "daylighting_reference_point_coordinate_system",
                    "rectangular_surface_coordinate_system"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "minProperties": 1,
        "maxProperties": 1,
        "memo": "Specifies the geometric rules used to describe the input of surface vertices and daylighting reference points."
    }
}
```
