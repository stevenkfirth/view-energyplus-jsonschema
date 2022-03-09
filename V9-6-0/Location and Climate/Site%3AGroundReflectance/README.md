```
{
    "Site:GroundReflectance": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "january_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "february_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "march_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "april_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "may_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "june_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "july_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "august_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "september_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "october_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "november_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    },
                    "december_ground_reflectance": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "units": "dimensionless"
                    }
                }
            }
        },
        "group": "Location and Climate",
        "legacy_idd": {
            "field_info": {
                "january_ground_reflectance": {
                    "field_name": "January Ground Reflectance",
                    "field_type": "n"
                },
                "february_ground_reflectance": {
                    "field_name": "February Ground Reflectance",
                    "field_type": "n"
                },
                "march_ground_reflectance": {
                    "field_name": "March Ground Reflectance",
                    "field_type": "n"
                },
                "april_ground_reflectance": {
                    "field_name": "April Ground Reflectance",
                    "field_type": "n"
                },
                "may_ground_reflectance": {
                    "field_name": "May Ground Reflectance",
                    "field_type": "n"
                },
                "june_ground_reflectance": {
                    "field_name": "June Ground Reflectance",
                    "field_type": "n"
                },
                "july_ground_reflectance": {
                    "field_name": "July Ground Reflectance",
                    "field_type": "n"
                },
                "august_ground_reflectance": {
                    "field_name": "August Ground Reflectance",
                    "field_type": "n"
                },
                "september_ground_reflectance": {
                    "field_name": "September Ground Reflectance",
                    "field_type": "n"
                },
                "october_ground_reflectance": {
                    "field_name": "October Ground Reflectance",
                    "field_type": "n"
                },
                "november_ground_reflectance": {
                    "field_name": "November Ground Reflectance",
                    "field_type": "n"
                },
                "december_ground_reflectance": {
                    "field_name": "December Ground Reflectance",
                    "field_type": "n"
                }
            },
            "fields": [
                "january_ground_reflectance",
                "february_ground_reflectance",
                "march_ground_reflectance",
                "april_ground_reflectance",
                "may_ground_reflectance",
                "june_ground_reflectance",
                "july_ground_reflectance",
                "august_ground_reflectance",
                "september_ground_reflectance",
                "october_ground_reflectance",
                "november_ground_reflectance",
                "december_ground_reflectance"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "january_ground_reflectance",
                    "february_ground_reflectance",
                    "march_ground_reflectance",
                    "april_ground_reflectance",
                    "may_ground_reflectance",
                    "june_ground_reflectance",
                    "july_ground_reflectance",
                    "august_ground_reflectance",
                    "september_ground_reflectance",
                    "october_ground_reflectance",
                    "november_ground_reflectance",
                    "december_ground_reflectance"
                ]
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Specifies the ground reflectance values used to calculate ground reflected solar. The ground reflectance can be further modified when snow is on the ground by Site:GroundReflectance:SnowModifier.",
        "min_fields": 12.0,
        "format": "singleLine"
    }
}
```
