```
{
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
                "height_above_window_or_door": {
                    "type": "number",
                    "units": "m"
                },
                "tilt_angle_from_window_door": {
                    "type": "number",
                    "units": "deg",
                    "default": 90.0,
                    "minimum": 0.0,
                    "maximum": 180.0
                },
                "left_extension_from_window_door_width": {
                    "type": "number",
                    "units": "m"
                },
                "right_extension_from_window_door_width": {
                    "type": "number",
                    "units": "m",
                    "note": "N3 + N4 + Window/Door Width is Overhang Length"
                },
                "depth_as_fraction_of_window_door_height": {
                    "type": "number",
                    "units": "dimensionless",
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
            "height_above_window_or_door": {
                "field_name": "Height above Window or Door",
                "field_type": "n"
            },
            "tilt_angle_from_window_door": {
                "field_name": "Tilt Angle from Window/Door",
                "field_type": "n"
            },
            "left_extension_from_window_door_width": {
                "field_name": "Left extension from Window/Door Width",
                "field_type": "n"
            },
            "right_extension_from_window_door_width": {
                "field_name": "Right extension from Window/Door Width",
                "field_type": "n"
            },
            "depth_as_fraction_of_window_door_height": {
                "field_name": "Depth as Fraction of Window/Door Height",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "window_or_door_name",
            "height_above_window_or_door",
            "tilt_angle_from_window_door",
            "left_extension_from_window_door_width",
            "right_extension_from_window_door_width",
            "depth_as_fraction_of_window_door_height"
        ],
        "alphas": {
            "fields": [
                "name",
                "window_or_door_name"
            ]
        },
        "numerics": {
            "fields": [
                "height_above_window_or_door",
                "tilt_angle_from_window_door",
                "left_extension_from_window_door_width",
                "right_extension_from_window_door_width",
                "depth_as_fraction_of_window_door_height"
            ]
        }
    },
    "type": "object",
    "memo": "Overhangs are typically flat shading surfaces that reference a window or door."
}
```
