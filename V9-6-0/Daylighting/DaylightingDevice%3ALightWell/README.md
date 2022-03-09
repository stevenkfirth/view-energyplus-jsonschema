```
{
    "DaylightingDevice:LightWell": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "exterior_window_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SubSurfNames"
                        ]
                    },
                    "height_of_well": {
                        "type": "number",
                        "note": "Distance from Bottom of Window to Bottom of Well",
                        "units": "m",
                        "minimum": 0.0
                    },
                    "perimeter_of_bottom_of_well": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "area_of_bottom_of_well": {
                        "type": "number",
                        "units": "m2",
                        "exclusiveMinimum": 0.0
                    },
                    "visible_reflectance_of_well_walls": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    }
                },
                "required": [
                    "exterior_window_name",
                    "height_of_well",
                    "perimeter_of_bottom_of_well",
                    "area_of_bottom_of_well",
                    "visible_reflectance_of_well_walls"
                ]
            }
        },
        "group": "Daylighting",
        "legacy_idd": {
            "field_info": {
                "exterior_window_name": {
                    "field_name": "Exterior Window Name",
                    "field_type": "a"
                },
                "height_of_well": {
                    "field_name": "Height of Well",
                    "field_type": "n"
                },
                "perimeter_of_bottom_of_well": {
                    "field_name": "Perimeter of Bottom of Well",
                    "field_type": "n"
                },
                "area_of_bottom_of_well": {
                    "field_name": "Area of Bottom of Well",
                    "field_type": "n"
                },
                "visible_reflectance_of_well_walls": {
                    "field_name": "Visible Reflectance of Well Walls",
                    "field_type": "n"
                }
            },
            "fields": [
                "exterior_window_name",
                "height_of_well",
                "perimeter_of_bottom_of_well",
                "area_of_bottom_of_well",
                "visible_reflectance_of_well_walls"
            ],
            "alphas": {
                "fields": [
                    "exterior_window_name"
                ]
            },
            "numerics": {
                "fields": [
                    "height_of_well",
                    "perimeter_of_bottom_of_well",
                    "area_of_bottom_of_well",
                    "visible_reflectance_of_well_walls"
                ]
            }
        },
        "type": "object",
        "memo": "Applies only to exterior windows in daylighting-controlled zones or in zones that share an interior window with a daylighting-controlled  zone. Generally used with skylights.",
        "min_fields": 5.0
    }
}
```
