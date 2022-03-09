```
{
    "Output:IlluminanceMap": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "z_height": {
                        "type": "number",
                        "units": "m",
                        "default": 0.0
                    },
                    "x_minimum_coordinate": {
                        "type": "number",
                        "units": "m",
                        "default": 0.0
                    },
                    "x_maximum_coordinate": {
                        "type": "number",
                        "units": "m",
                        "default": 1.0
                    },
                    "number_of_x_grid_points": {
                        "type": "number",
                        "note": "Maximum number of total grid points must be <= 2500 (X*Y)",
                        "minimum": 1.0,
                        "default": 2.0
                    },
                    "y_minimum_coordinate": {
                        "type": "number",
                        "units": "m",
                        "default": 0.0
                    },
                    "y_maximum_coordinate": {
                        "type": "number",
                        "units": "m",
                        "default": 1.0
                    },
                    "number_of_y_grid_points": {
                        "type": "number",
                        "note": "Maximum number of total grid points must be <= 2500 (X*Y)",
                        "minimum": 1.0,
                        "default": 2.0
                    }
                },
                "required": [
                    "zone_name"
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
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "z_height": {
                    "field_name": "Z height",
                    "field_type": "n"
                },
                "x_minimum_coordinate": {
                    "field_name": "X Minimum Coordinate",
                    "field_type": "n"
                },
                "x_maximum_coordinate": {
                    "field_name": "X Maximum Coordinate",
                    "field_type": "n"
                },
                "number_of_x_grid_points": {
                    "field_name": "Number of X Grid Points",
                    "field_type": "n"
                },
                "y_minimum_coordinate": {
                    "field_name": "Y Minimum Coordinate",
                    "field_type": "n"
                },
                "y_maximum_coordinate": {
                    "field_name": "Y Maximum Coordinate",
                    "field_type": "n"
                },
                "number_of_y_grid_points": {
                    "field_name": "Number of Y Grid Points",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "z_height",
                "x_minimum_coordinate",
                "x_maximum_coordinate",
                "number_of_x_grid_points",
                "y_minimum_coordinate",
                "y_maximum_coordinate",
                "number_of_y_grid_points"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name"
                ]
            },
            "numerics": {
                "fields": [
                    "z_height",
                    "x_minimum_coordinate",
                    "x_maximum_coordinate",
                    "number_of_x_grid_points",
                    "y_minimum_coordinate",
                    "y_maximum_coordinate",
                    "number_of_y_grid_points"
                ]
            }
        },
        "type": "object",
        "memo": "reference points are given in coordinates specified in the GlobalGeometryRules object Daylighting Reference Point CoordinateSystem field",
        "min_fields": 9.0
    }
}
```
