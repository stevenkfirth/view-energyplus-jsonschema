```
{
    "Site:GroundTemperature:Shallow": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "january_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "february_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "march_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "april_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "may_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "june_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "july_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "august_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "september_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "october_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "november_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    },
                    "december_surface_ground_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 13.0
                    }
                }
            }
        },
        "group": "Location and Climate",
        "legacy_idd": {
            "field_info": {
                "january_surface_ground_temperature": {
                    "field_name": "January Surface Ground Temperature",
                    "field_type": "n"
                },
                "february_surface_ground_temperature": {
                    "field_name": "February Surface Ground Temperature",
                    "field_type": "n"
                },
                "march_surface_ground_temperature": {
                    "field_name": "March Surface Ground Temperature",
                    "field_type": "n"
                },
                "april_surface_ground_temperature": {
                    "field_name": "April Surface Ground Temperature",
                    "field_type": "n"
                },
                "may_surface_ground_temperature": {
                    "field_name": "May Surface Ground Temperature",
                    "field_type": "n"
                },
                "june_surface_ground_temperature": {
                    "field_name": "June Surface Ground Temperature",
                    "field_type": "n"
                },
                "july_surface_ground_temperature": {
                    "field_name": "July Surface Ground Temperature",
                    "field_type": "n"
                },
                "august_surface_ground_temperature": {
                    "field_name": "August Surface Ground Temperature",
                    "field_type": "n"
                },
                "september_surface_ground_temperature": {
                    "field_name": "September Surface Ground Temperature",
                    "field_type": "n"
                },
                "october_surface_ground_temperature": {
                    "field_name": "October Surface Ground Temperature",
                    "field_type": "n"
                },
                "november_surface_ground_temperature": {
                    "field_name": "November Surface Ground Temperature",
                    "field_type": "n"
                },
                "december_surface_ground_temperature": {
                    "field_name": "December Surface Ground Temperature",
                    "field_type": "n"
                }
            },
            "fields": [
                "january_surface_ground_temperature",
                "february_surface_ground_temperature",
                "march_surface_ground_temperature",
                "april_surface_ground_temperature",
                "may_surface_ground_temperature",
                "june_surface_ground_temperature",
                "july_surface_ground_temperature",
                "august_surface_ground_temperature",
                "september_surface_ground_temperature",
                "october_surface_ground_temperature",
                "november_surface_ground_temperature",
                "december_surface_ground_temperature"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "january_surface_ground_temperature",
                    "february_surface_ground_temperature",
                    "march_surface_ground_temperature",
                    "april_surface_ground_temperature",
                    "may_surface_ground_temperature",
                    "june_surface_ground_temperature",
                    "july_surface_ground_temperature",
                    "august_surface_ground_temperature",
                    "september_surface_ground_temperature",
                    "october_surface_ground_temperature",
                    "november_surface_ground_temperature",
                    "december_surface_ground_temperature"
                ]
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "These temperatures are specifically for the Surface Ground Heat Exchanger and should probably be close to the average outdoor air temperature for the location. They are not used in other models.",
        "min_fields": 12.0,
        "format": "singleLine"
    }
}
```
