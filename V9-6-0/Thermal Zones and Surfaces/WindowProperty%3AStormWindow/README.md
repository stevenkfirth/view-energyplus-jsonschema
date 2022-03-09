```
{
    "WindowProperty:StormWindow": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "window_name": {
                        "type": "string",
                        "note": "Must be the name of a FenestrationSurface:Detailed object with Surface Type = WINDOW. The WindowProperty:StormWindow object can only be used with exterior windows.",
                        "data_type": "object_list",
                        "object_list": [
                            "SubSurfNames"
                        ]
                    },
                    "storm_glass_layer_name": {
                        "type": "string",
                        "note": "Must be a WindowMaterial:Glazing or WindowMaterial:Glazing:RefractionExtinctionMethod Gap between storm glass layer and adjacent glass layer is assumed to be filled with Air",
                        "data_type": "object_list",
                        "object_list": [
                            "GlazingMaterialName"
                        ]
                    },
                    "distance_between_storm_glass_layer_and_adjacent_glass": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "maximum": 0.5,
                        "default": 0.05
                    },
                    "month_that_storm_glass_layer_is_put_on": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 12.0
                    },
                    "day_of_month_that_storm_glass_layer_is_put_on": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 31.0
                    },
                    "month_that_storm_glass_layer_is_taken_off": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 12.0
                    },
                    "day_of_month_that_storm_glass_layer_is_taken_off": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 31.0
                    }
                },
                "required": [
                    "window_name",
                    "storm_glass_layer_name",
                    "month_that_storm_glass_layer_is_put_on",
                    "day_of_month_that_storm_glass_layer_is_put_on",
                    "month_that_storm_glass_layer_is_taken_off",
                    "day_of_month_that_storm_glass_layer_is_taken_off"
                ]
            }
        },
        "group": "Thermal Zones and Surfaces",
        "legacy_idd": {
            "field_info": {
                "window_name": {
                    "field_name": "Window Name",
                    "field_type": "a"
                },
                "storm_glass_layer_name": {
                    "field_name": "Storm Glass Layer Name",
                    "field_type": "a"
                },
                "distance_between_storm_glass_layer_and_adjacent_glass": {
                    "field_name": "Distance Between Storm Glass Layer and Adjacent Glass",
                    "field_type": "n"
                },
                "month_that_storm_glass_layer_is_put_on": {
                    "field_name": "Month that Storm Glass Layer is Put On",
                    "field_type": "n"
                },
                "day_of_month_that_storm_glass_layer_is_put_on": {
                    "field_name": "Day of Month that Storm Glass Layer is Put On",
                    "field_type": "n"
                },
                "month_that_storm_glass_layer_is_taken_off": {
                    "field_name": "Month that Storm Glass Layer is Taken Off",
                    "field_type": "n"
                },
                "day_of_month_that_storm_glass_layer_is_taken_off": {
                    "field_name": "Day of Month that Storm Glass Layer is Taken Off",
                    "field_type": "n"
                }
            },
            "fields": [
                "window_name",
                "storm_glass_layer_name",
                "distance_between_storm_glass_layer_and_adjacent_glass",
                "month_that_storm_glass_layer_is_put_on",
                "day_of_month_that_storm_glass_layer_is_put_on",
                "month_that_storm_glass_layer_is_taken_off",
                "day_of_month_that_storm_glass_layer_is_taken_off"
            ],
            "alphas": {
                "fields": [
                    "window_name",
                    "storm_glass_layer_name"
                ]
            },
            "numerics": {
                "fields": [
                    "distance_between_storm_glass_layer_and_adjacent_glass",
                    "month_that_storm_glass_layer_is_put_on",
                    "day_of_month_that_storm_glass_layer_is_put_on",
                    "month_that_storm_glass_layer_is_taken_off",
                    "day_of_month_that_storm_glass_layer_is_taken_off"
                ]
            }
        },
        "type": "object",
        "memo": "This is a movable exterior glass layer that is usually applied in the winter and removed in the summer.",
        "min_fields": 7.0
    }
}
```
