```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "january_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "february_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "march_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "april_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "may_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "june_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "july_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "august_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "september_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "october_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "november_ground_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 13.0
                },
                "december_ground_temperature": {
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
            "january_ground_temperature": {
                "field_name": "January Ground Temperature",
                "field_type": "n"
            },
            "february_ground_temperature": {
                "field_name": "February Ground Temperature",
                "field_type": "n"
            },
            "march_ground_temperature": {
                "field_name": "March Ground Temperature",
                "field_type": "n"
            },
            "april_ground_temperature": {
                "field_name": "April Ground Temperature",
                "field_type": "n"
            },
            "may_ground_temperature": {
                "field_name": "May Ground Temperature",
                "field_type": "n"
            },
            "june_ground_temperature": {
                "field_name": "June Ground Temperature",
                "field_type": "n"
            },
            "july_ground_temperature": {
                "field_name": "July Ground Temperature",
                "field_type": "n"
            },
            "august_ground_temperature": {
                "field_name": "August Ground Temperature",
                "field_type": "n"
            },
            "september_ground_temperature": {
                "field_name": "September Ground Temperature",
                "field_type": "n"
            },
            "october_ground_temperature": {
                "field_name": "October Ground Temperature",
                "field_type": "n"
            },
            "november_ground_temperature": {
                "field_name": "November Ground Temperature",
                "field_type": "n"
            },
            "december_ground_temperature": {
                "field_name": "December Ground Temperature",
                "field_type": "n"
            }
        },
        "fields": [
            "january_ground_temperature",
            "february_ground_temperature",
            "march_ground_temperature",
            "april_ground_temperature",
            "may_ground_temperature",
            "june_ground_temperature",
            "july_ground_temperature",
            "august_ground_temperature",
            "september_ground_temperature",
            "october_ground_temperature",
            "november_ground_temperature",
            "december_ground_temperature"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "january_ground_temperature",
                "february_ground_temperature",
                "march_ground_temperature",
                "april_ground_temperature",
                "may_ground_temperature",
                "june_ground_temperature",
                "july_ground_temperature",
                "august_ground_temperature",
                "september_ground_temperature",
                "october_ground_temperature",
                "november_ground_temperature",
                "december_ground_temperature"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "These temperatures are specifically for underground walls and ground floors defined with the C-factor and F-factor methods, and should be close to the monthly average outdoor air temperature delayed by 3 months for the location.",
    "min_fields": 12.0,
    "format": "singleLine"
}
```
