```
{
    "Material:NoMass": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "roughness": {
                        "type": "string",
                        "enum": [
                            "MediumRough",
                            "MediumSmooth",
                            "Rough",
                            "Smooth",
                            "VeryRough",
                            "VerySmooth"
                        ]
                    },
                    "thermal_resistance": {
                        "type": "number",
                        "units": "m2-K/W",
                        "minimum": 0.001
                    },
                    "thermal_absorptance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.9,
                        "maximum": 0.99999
                    },
                    "solar_absorptance": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.7,
                        "maximum": 1.0
                    },
                    "visible_absorptance": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.7,
                        "maximum": 1.0
                    }
                },
                "required": [
                    "roughness",
                    "thermal_resistance"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "MaterialName"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "roughness": {
                    "field_name": "Roughness",
                    "field_type": "a"
                },
                "thermal_resistance": {
                    "field_name": "Thermal Resistance",
                    "field_type": "n"
                },
                "thermal_absorptance": {
                    "field_name": "Thermal Absorptance",
                    "field_type": "n"
                },
                "solar_absorptance": {
                    "field_name": "Solar Absorptance",
                    "field_type": "n"
                },
                "visible_absorptance": {
                    "field_name": "Visible Absorptance",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "roughness",
                "thermal_resistance",
                "thermal_absorptance",
                "solar_absorptance",
                "visible_absorptance"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "roughness"
                ]
            },
            "numerics": {
                "fields": [
                    "thermal_resistance",
                    "thermal_absorptance",
                    "solar_absorptance",
                    "visible_absorptance"
                ]
            }
        },
        "type": "object",
        "memo": "Regular materials properties described whose principal description is R (Thermal Resistance)",
        "min_fields": 3.0
    }
}
```
