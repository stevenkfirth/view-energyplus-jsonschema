```
{
    "Daylighting:DELight:ComplexFenestration": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "complex_fenestration_type": {
                        "type": "string",
                        "note": "Used to select the appropriate Complex Fenestration BTDF data"
                    },
                    "building_surface_name": {
                        "type": "string",
                        "note": "This is a reference to a valid surface object (such as BuildingSurface:Detailed) hosting this complex fenestration, analogous to the base surface Name field for subsurfaces such as Windows.",
                        "data_type": "object_list",
                        "object_list": [
                            "SurfaceNames"
                        ]
                    },
                    "window_name": {
                        "type": "string",
                        "note": "This is a reference to a valid FenestrationSurface:Detailed window object used to account for the geometry, and the solar and thermal gains/losses, of the Complex Fenestration",
                        "data_type": "object_list",
                        "object_list": [
                            "SubSurfNames"
                        ]
                    },
                    "fenestration_rotation": {
                        "type": "number",
                        "units": "deg",
                        "note": "In-plane counter-clockwise rotation angle of the Complex Fenestration optical reference direction and the base edge of the Complex Fenestration. The Rotation will typically be zero when the host and CFS surfaces are rectangular and height and width edges are aligned.",
                        "default": 0.0
                    }
                },
                "required": [
                    "complex_fenestration_type",
                    "building_surface_name",
                    "window_name"
                ]
            }
        },
        "group": "Daylighting",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "Only used for user reference"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "complex_fenestration_type": {
                    "field_name": "Complex Fenestration Type",
                    "field_type": "a"
                },
                "building_surface_name": {
                    "field_name": "Building Surface Name",
                    "field_type": "a"
                },
                "window_name": {
                    "field_name": "Window Name",
                    "field_type": "a"
                },
                "fenestration_rotation": {
                    "field_name": "Fenestration Rotation",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "complex_fenestration_type",
                "building_surface_name",
                "window_name",
                "fenestration_rotation"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "complex_fenestration_type",
                    "building_surface_name",
                    "window_name"
                ]
            },
            "numerics": {
                "fields": [
                    "fenestration_rotation"
                ]
            }
        },
        "type": "object",
        "memo": "Used for DElight Complex Fenestration of all types",
        "min_fields": 5.0
    }
}
```
