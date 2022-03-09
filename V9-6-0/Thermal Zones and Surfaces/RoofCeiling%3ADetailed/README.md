```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "construction_name": {
                    "type": "string",
                    "note": "To be matched with a construction in this input file",
                    "data_type": "object_list",
                    "object_list": [
                        "ConstructionNames"
                    ]
                },
                "zone_name": {
                    "type": "string",
                    "note": "Zone the surface is a part of.",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "space_name": {
                    "type": "string",
                    "note": "Space the surface is a part of (optional, see description of Space object for more details).",
                    "data_type": "object_list",
                    "object_list": [
                        "SpaceNames"
                    ]
                },
                "outside_boundary_condition": {
                    "type": "string",
                    "enum": [
                        "Adiabatic",
                        "Ground",
                        "GroundBasementPreprocessorAverageFloor",
                        "GroundBasementPreprocessorAverageWall",
                        "GroundBasementPreprocessorLowerWall",
                        "GroundBasementPreprocessorUpperWall",
                        "GroundSlabPreprocessorAverage",
                        "GroundSlabPreprocessorCore",
                        "GroundSlabPreprocessorPerimeter",
                        "OtherSideCoefficients",
                        "OtherSideConditionsModel",
                        "Outdoors",
                        "Surface",
                        "Zone"
                    ]
                },
                "outside_boundary_condition_object": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "OutFaceEnvNames"
                    ],
                    "note": "Non-blank only if the field Outside Boundary Condition is Surface, Zone, OtherSideCoefficients or OtherSideConditionsModel If Surface, specify name of corresponding surface in adjacent zone or specify current surface name for internal partition separating like zones If Zone, specify the name of the corresponding zone and the program will generate the corresponding interzone surface If OtherSideCoefficients, specify name of SurfaceProperty:OtherSideCoefficients If OtherSideConditionsModel, specify name of SurfaceProperty:OtherSideConditionsModel"
                },
                "sun_exposure": {
                    "type": "string",
                    "enum": [
                        "",
                        "NoSun",
                        "SunExposed"
                    ],
                    "default": "SunExposed"
                },
                "wind_exposure": {
                    "type": "string",
                    "enum": [
                        "",
                        "NoWind",
                        "WindExposed"
                    ],
                    "default": "WindExposed"
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
                "number_of_vertices": {
                    "note": "shown with 10 vertex coordinates -- extensible object \"extensible\" -- duplicate last set of x,y,z coordinates, renumbering please (and changing z terminator to a comma \",\" for all but last one which needs a semi-colon \";\") vertices are given in GlobalGeometryRules coordinates -- if relative, all surface coordinates are \"relative\" to the Zone Origin. If world, then building and zone origins are used for some internal calculations, but all coordinates are given in an \"absolute\" system.",
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
                "construction_name",
                "zone_name",
                "outside_boundary_condition"
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
            "OutFaceEnvNames",
            "RadiantSurfaceNames",
            "SurfAndSubSurfNames",
            "SurfaceNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "construction_name": {
                "field_name": "Construction Name",
                "field_type": "a"
            },
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "space_name": {
                "field_name": "Space Name",
                "field_type": "a"
            },
            "outside_boundary_condition": {
                "field_name": "Outside Boundary Condition",
                "field_type": "a"
            },
            "outside_boundary_condition_object": {
                "field_name": "Outside Boundary Condition Object",
                "field_type": "a"
            },
            "sun_exposure": {
                "field_name": "Sun Exposure",
                "field_type": "a"
            },
            "wind_exposure": {
                "field_name": "Wind Exposure",
                "field_type": "a"
            },
            "view_factor_to_ground": {
                "field_name": "View Factor to Ground",
                "field_type": "n"
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
            "construction_name",
            "zone_name",
            "space_name",
            "outside_boundary_condition",
            "outside_boundary_condition_object",
            "sun_exposure",
            "wind_exposure",
            "view_factor_to_ground",
            "number_of_vertices"
        ],
        "alphas": {
            "fields": [
                "name",
                "construction_name",
                "zone_name",
                "space_name",
                "outside_boundary_condition",
                "outside_boundary_condition_object",
                "sun_exposure",
                "wind_exposure"
            ]
        },
        "numerics": {
            "fields": [
                "view_factor_to_ground",
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
    "memo": "Allows for detailed entry of roof/ceiling heat transfer surfaces.",
    "min_fields": 19.0,
    "extensible_size": 3.0,
    "format": "vertices"
}
```
