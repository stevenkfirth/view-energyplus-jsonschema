```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "azimuth_angle": {
                    "type": "number",
                    "note": "Facing direction of outside of shading device (S=180,N=0,E=90,W=270)",
                    "minimum": 0.0,
                    "maximum": 360.0,
                    "units": "deg"
                },
                "tilt_angle": {
                    "type": "number",
                    "default": 90.0,
                    "minimum": 0.0,
                    "maximum": 180.0,
                    "units": "deg"
                },
                "starting_x_coordinate": {
                    "type": "number",
                    "note": "Starting coordinate is the Lower Left Corner of the Shade",
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
                    "units": "m"
                },
                "height": {
                    "type": "number",
                    "units": "m"
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
            "height": {
                "field_name": "Height",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "azimuth_angle",
            "tilt_angle",
            "starting_x_coordinate",
            "starting_y_coordinate",
            "starting_z_coordinate",
            "length",
            "height"
        ],
        "alphas": {
            "fields": [
                "name"
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
                "height"
            ]
        }
    },
    "type": "object",
    "memo": "used for shading elements such as trees, other buildings, parts of this building not being modeled these items are relative to the current building and would move with relative geometry"
}
```
