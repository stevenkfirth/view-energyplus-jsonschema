```
{
    "Floor:Interzone": {
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
                        "note": "Zone for the inside face of the surface.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "space_name": {
                        "type": "string",
                        "note": "Space for the inside face of the surface (optional, see description of Space object for more details).",
                        "data_type": "object_list",
                        "object_list": [
                            "SpaceNames"
                        ]
                    },
                    "outside_boundary_condition_object": {
                        "type": "string",
                        "note": "Specify a surface name in an adjacent zone for known interior ceilings. Specify a zone name of an adjacent zone to automatically generate the interior ceiling in the adjacent zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "OutFaceEnvNames"
                        ]
                    },
                    "azimuth_angle": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 360.0,
                        "units": "deg"
                    },
                    "tilt_angle": {
                        "type": "number",
                        "note": "Floors are usually tilted 180 degrees",
                        "minimum": 0.0,
                        "maximum": 180.0,
                        "default": 180.0,
                        "units": "deg"
                    },
                    "starting_x_coordinate": {
                        "type": "number",
                        "note": "If not Flat, should be Lower Left Corner (from outside)",
                        "units": "m"
                    },
                    "starting_y_coordinate": {
                        "type": "number",
                        "units": "m"
                    },
                    "starting_z_coordinate": {
                        "type": "number",
                        "units": "m"
                    },
                    "length": {
                        "type": "number",
                        "note": "Along X Axis",
                        "units": "m"
                    },
                    "width": {
                        "type": "number",
                        "note": "Along Y Axis",
                        "units": "m"
                    }
                },
                "required": [
                    "construction_name",
                    "zone_name",
                    "outside_boundary_condition_object"
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
                "FloorSurfaceNames",
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
                "outside_boundary_condition_object": {
                    "field_name": "Outside Boundary Condition Object",
                    "field_type": "a"
                },
                "azimuth_angle": {
                    "field_name": "Azimuth Angle",
                    "field_type": "n"
                },
                "tilt_angle": {
                    "field_name": "Tilt Angle",
                    "field_type": "n"
                },
                "starting_x_coordinate": {
                    "field_name": "Starting X Coordinate",
                    "field_type": "n"
                },
                "starting_y_coordinate": {
                    "field_name": "Starting Y Coordinate",
                    "field_type": "n"
                },
                "starting_z_coordinate": {
                    "field_name": "Starting Z Coordinate",
                    "field_type": "n"
                },
                "length": {
                    "field_name": "Length",
                    "field_type": "n"
                },
                "width": {
                    "field_name": "Width",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "construction_name",
                "zone_name",
                "space_name",
                "outside_boundary_condition_object",
                "azimuth_angle",
                "tilt_angle",
                "starting_x_coordinate",
                "starting_y_coordinate",
                "starting_z_coordinate",
                "length",
                "width"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "construction_name",
                    "zone_name",
                    "space_name",
                    "outside_boundary_condition_object"
                ]
            },
            "numerics": {
                "fields": [
                    "azimuth_angle",
                    "tilt_angle",
                    "starting_x_coordinate",
                    "starting_y_coordinate",
                    "starting_z_coordinate",
                    "length",
                    "width"
                ]
            }
        },
        "type": "object",
        "memo": "Allows for simplified entry of floors using adjacent zone (interzone) heat transfer - adjacent surface should be a ceiling."
    }
}
```
