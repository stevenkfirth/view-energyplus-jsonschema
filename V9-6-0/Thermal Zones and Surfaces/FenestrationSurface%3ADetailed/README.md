```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "surface_type": {
                    "type": "string",
                    "enum": [
                        "Door",
                        "GlassDoor",
                        "TubularDaylightDiffuser",
                        "TubularDaylightDome",
                        "Window"
                    ]
                },
                "construction_name": {
                    "type": "string",
                    "note": "To be matched with a construction in this input file",
                    "data_type": "object_list",
                    "object_list": [
                        "ComplexFenestrationStates",
                        "ConstructionNames"
                    ]
                },
                "building_surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfaceNames"
                    ]
                },
                "outside_boundary_condition_object": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "OutFaceEnvNames"
                    ],
                    "note": "Non-blank only if base surface field Outside Boundary Condition is Surface or OtherSideCoefficients If Base Surface's Surface, specify name of corresponding subsurface in adjacent zone or specify current subsurface name for internal partition separating like zones If OtherSideCoefficients, specify name of SurfaceProperty:OtherSideCoefficients or leave blank to inherit Base Surface's OtherSide Coefficients"
                },
                "view_factor_to_ground": {
                    "note": "From the exterior of the surface Unused if one uses the \"reflections\" options in Solar Distribution in Building input unless a DaylightingDevice:Shelf or DaylightingDevice:Tubular object has been specified. autocalculate will automatically calculate this value from the tilt of the surface",
                    "default": "Autocalculate",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0,
                            "maximum": 1.0
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
                "frame_and_divider_name": {
                    "type": "string",
                    "note": "Enter the name of a WindowProperty:FrameAndDivider object Used only for exterior windows (rectangular) and glass doors. Unused for triangular windows. If not specified (blank), window or glass door has no frame or divider and no beam solar reflection from reveal surfaces.",
                    "data_type": "object_list",
                    "object_list": [
                        "WindowFrameAndDividerNames"
                    ]
                },
                "multiplier": {
                    "type": "number",
                    "note": "Used only for Surface Type = WINDOW, GLASSDOOR or DOOR Non-integer values will be truncated to integer",
                    "default": 1.0,
                    "minimum": 1.0
                },
                "number_of_vertices": {
                    "default": "Autocalculate",
                    "note": "vertices are given in GlobalGeometryRules coordinates -- if relative, all surface coordinates are \"relative\" to the Zone Origin. If world, then building and zone origins are used for some internal calculations, but all coordinates are given in an \"absolute\" system.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 3.0,
                            "maximum": 4.0
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
                "vertex_1_x_coordinate": {
                    "type": "number",
                    "units": "m"
                },
                "vertex_1_y_coordinate": {
                    "type": "number",
                    "units": "m"
                },
                "vertex_1_z_coordinate": {
                    "type": "number",
                    "units": "m"
                },
                "vertex_2_x_coordinate": {
                    "type": "number",
                    "units": "m"
                },
                "vertex_2_y_coordinate": {
                    "type": "number",
                    "units": "m"
                },
                "vertex_2_z_coordinate": {
                    "type": "number",
                    "units": "m"
                },
                "vertex_3_x_coordinate": {
                    "type": "number",
                    "units": "m"
                },
                "vertex_3_y_coordinate": {
                    "type": "number",
                    "units": "m"
                },
                "vertex_3_z_coordinate": {
                    "type": "number",
                    "units": "m"
                },
                "vertex_4_x_coordinate": {
                    "type": "number",
                    "units": "m",
                    "note": "Not used for triangles"
                },
                "vertex_4_y_coordinate": {
                    "type": "number",
                    "units": "m",
                    "note": "Not used for triangles"
                },
                "vertex_4_z_coordinate": {
                    "type": "number",
                    "units": "m",
                    "note": "Not used for triangles"
                }
            },
            "required": [
                "surface_type",
                "construction_name",
                "building_surface_name",
                "vertex_1_x_coordinate",
                "vertex_1_y_coordinate",
                "vertex_1_z_coordinate",
                "vertex_2_x_coordinate",
                "vertex_2_y_coordinate",
                "vertex_2_z_coordinate",
                "vertex_3_x_coordinate",
                "vertex_3_y_coordinate",
                "vertex_3_z_coordinate"
            ]
        }
    },
    "group": "Thermal Zones and Surfaces",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AllHeatTranAngFacNames",
            "AllHeatTranSurfNames",
            "AllShadingAndHTSurfNames",
            "GlazedExtSubSurfNames",
            "OutFaceEnvNames",
            "RadiantSurfaceNames",
            "SubSurfNames",
            "SurfAndSubSurfNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "surface_type": {
                "field_name": "Surface Type",
                "field_type": "a"
            },
            "construction_name": {
                "field_name": "Construction Name",
                "field_type": "a"
            },
            "building_surface_name": {
                "field_name": "Building Surface Name",
                "field_type": "a"
            },
            "outside_boundary_condition_object": {
                "field_name": "Outside Boundary Condition Object",
                "field_type": "a"
            },
            "view_factor_to_ground": {
                "field_name": "View Factor to Ground",
                "field_type": "n"
            },
            "frame_and_divider_name": {
                "field_name": "Frame and Divider Name",
                "field_type": "a"
            },
            "multiplier": {
                "field_name": "Multiplier",
                "field_type": "n"
            },
            "number_of_vertices": {
                "field_name": "Number of Vertices",
                "field_type": "n"
            },
            "vertex_1_x_coordinate": {
                "field_name": "Vertex 1 X-coordinate",
                "field_type": "n"
            },
            "vertex_1_y_coordinate": {
                "field_name": "Vertex 1 Y-coordinate",
                "field_type": "n"
            },
            "vertex_1_z_coordinate": {
                "field_name": "Vertex 1 Z-coordinate",
                "field_type": "n"
            },
            "vertex_2_x_coordinate": {
                "field_name": "Vertex 2 X-coordinate",
                "field_type": "n"
            },
            "vertex_2_y_coordinate": {
                "field_name": "Vertex 2 Y-coordinate",
                "field_type": "n"
            },
            "vertex_2_z_coordinate": {
                "field_name": "Vertex 2 Z-coordinate",
                "field_type": "n"
            },
            "vertex_3_x_coordinate": {
                "field_name": "Vertex 3 X-coordinate",
                "field_type": "n"
            },
            "vertex_3_y_coordinate": {
                "field_name": "Vertex 3 Y-coordinate",
                "field_type": "n"
            },
            "vertex_3_z_coordinate": {
                "field_name": "Vertex 3 Z-coordinate",
                "field_type": "n"
            },
            "vertex_4_x_coordinate": {
                "field_name": "Vertex 4 X-coordinate",
                "field_type": "n"
            },
            "vertex_4_y_coordinate": {
                "field_name": "Vertex 4 Y-coordinate",
                "field_type": "n"
            },
            "vertex_4_z_coordinate": {
                "field_name": "Vertex 4 Z-coordinate",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "surface_type",
            "construction_name",
            "building_surface_name",
            "outside_boundary_condition_object",
            "view_factor_to_ground",
            "frame_and_divider_name",
            "multiplier",
            "number_of_vertices",
            "vertex_1_x_coordinate",
            "vertex_1_y_coordinate",
            "vertex_1_z_coordinate",
            "vertex_2_x_coordinate",
            "vertex_2_y_coordinate",
            "vertex_2_z_coordinate",
            "vertex_3_x_coordinate",
            "vertex_3_y_coordinate",
            "vertex_3_z_coordinate",
            "vertex_4_x_coordinate",
            "vertex_4_y_coordinate",
            "vertex_4_z_coordinate"
        ],
        "alphas": {
            "fields": [
                "name",
                "surface_type",
                "construction_name",
                "building_surface_name",
                "outside_boundary_condition_object",
                "frame_and_divider_name"
            ]
        },
        "numerics": {
            "fields": [
                "view_factor_to_ground",
                "multiplier",
                "number_of_vertices",
                "vertex_1_x_coordinate",
                "vertex_1_y_coordinate",
                "vertex_1_z_coordinate",
                "vertex_2_x_coordinate",
                "vertex_2_y_coordinate",
                "vertex_2_z_coordinate",
                "vertex_3_x_coordinate",
                "vertex_3_y_coordinate",
                "vertex_3_z_coordinate",
                "vertex_4_x_coordinate",
                "vertex_4_y_coordinate",
                "vertex_4_z_coordinate"
            ]
        }
    },
    "type": "object",
    "memo": "Allows for detailed entry of subsurfaces (windows, doors, glass doors, tubular daylighting devices).",
    "min_fields": 18.0,
    "format": "vertices"
}
```
