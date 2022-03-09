```
{
    "Material": {
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
                    "thickness": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in"
                    },
                    "conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0
                    },
                    "density": {
                        "type": "number",
                        "units": "kg/m3",
                        "exclusiveMinimum": 0.0
                    },
                    "specific_heat": {
                        "type": "number",
                        "units": "J/kg-K",
                        "minimum": 100.0
                    },
                    "thermal_absorptance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.9,
                        "maximum": 0.99999
                    },
                    "solar_absorptance": {
                        "type": "number",
                        "default": 0.7,
                        "minimum": 0.0,
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
                    "thickness",
                    "conductivity",
                    "density",
                    "specific_heat"
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
                "thickness": {
                    "field_name": "Thickness",
                    "field_type": "n"
                },
                "conductivity": {
                    "field_name": "Conductivity",
                    "field_type": "n"
                },
                "density": {
                    "field_name": "Density",
                    "field_type": "n"
                },
                "specific_heat": {
                    "field_name": "Specific Heat",
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
                "thickness",
                "conductivity",
                "density",
                "specific_heat",
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
                    "thickness",
                    "conductivity",
                    "density",
                    "specific_heat",
                    "thermal_absorptance",
                    "solar_absorptance",
                    "visible_absorptance"
                ]
            }
        },
        "type": "object",
        "memo": "Regular materials described with full set of thermal properties",
        "min_fields": 6.0
    }
}
```
