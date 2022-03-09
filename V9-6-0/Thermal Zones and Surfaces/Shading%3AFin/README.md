```
{
    "Shading:Fin": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "window_or_door_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SubSurfNames"
                        ]
                    },
                    "left_extension_from_window_door": {
                        "type": "number",
                        "units": "m"
                    },
                    "left_distance_above_top_of_window": {
                        "type": "number",
                        "units": "m"
                    },
                    "left_distance_below_bottom_of_window": {
                        "type": "number",
                        "units": "m",
                        "note": "N2 + N3 + height of Window/Door is height of Fin"
                    },
                    "left_tilt_angle_from_window_door": {
                        "type": "number",
                        "units": "deg",
                        "default": 90.0,
                        "minimum": 0.0,
                        "maximum": 180.0
                    },
                    "left_depth": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0
                    },
                    "right_extension_from_window_door": {
                        "type": "number",
                        "units": "m"
                    },
                    "right_distance_above_top_of_window": {
                        "type": "number",
                        "units": "m"
                    },
                    "right_distance_below_bottom_of_window": {
                        "type": "number",
                        "note": "N7 + N8 + height of Window/Door is height of Fin",
                        "units": "m"
                    },
                    "right_tilt_angle_from_window_door": {
                        "type": "number",
                        "units": "deg",
                        "default": 90.0,
                        "minimum": 0.0,
                        "maximum": 180.0
                    },
                    "right_depth": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0
                    }
                },
                "required": [
                    "window_or_door_name"
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
                "window_or_door_name": {
                    "field_name": "Window or Door Name",
                    "field_type": "a"
                },
                "left_extension_from_window_door": {
                    "field_name": "Left Extension from Window/Door",
                    "field_type": "n"
                },
                "left_distance_above_top_of_window": {
                    "field_name": "Left Distance Above Top of Window",
                    "field_type": "n"
                },
                "left_distance_below_bottom_of_window": {
                    "field_name": "Left Distance Below Bottom of Window",
                    "field_type": "n"
                },
                "left_tilt_angle_from_window_door": {
                    "field_name": "Left Tilt Angle from Window/Door",
                    "field_type": "n"
                },
                "left_depth": {
                    "field_name": "Left Depth",
                    "field_type": "n"
                },
                "right_extension_from_window_door": {
                    "field_name": "Right Extension from Window/Door",
                    "field_type": "n"
                },
                "right_distance_above_top_of_window": {
                    "field_name": "Right Distance Above Top of Window",
                    "field_type": "n"
                },
                "right_distance_below_bottom_of_window": {
                    "field_name": "Right Distance Below Bottom of Window",
                    "field_type": "n"
                },
                "right_tilt_angle_from_window_door": {
                    "field_name": "Right Tilt Angle from Window/Door",
                    "field_type": "n"
                },
                "right_depth": {
                    "field_name": "Right Depth",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "window_or_door_name",
                "left_extension_from_window_door",
                "left_distance_above_top_of_window",
                "left_distance_below_bottom_of_window",
                "left_tilt_angle_from_window_door",
                "left_depth",
                "right_extension_from_window_door",
                "right_distance_above_top_of_window",
                "right_distance_below_bottom_of_window",
                "right_tilt_angle_from_window_door",
                "right_depth"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "window_or_door_name"
                ]
            },
            "numerics": {
                "fields": [
                    "left_extension_from_window_door",
                    "left_distance_above_top_of_window",
                    "left_distance_below_bottom_of_window",
                    "left_tilt_angle_from_window_door",
                    "left_depth",
                    "right_extension_from_window_door",
                    "right_distance_above_top_of_window",
                    "right_distance_below_bottom_of_window",
                    "right_tilt_angle_from_window_door",
                    "right_depth"
                ]
            }
        },
        "type": "object",
        "memo": "Fins are usually shading surfaces that are perpendicular to a window or door."
    }
}
```
