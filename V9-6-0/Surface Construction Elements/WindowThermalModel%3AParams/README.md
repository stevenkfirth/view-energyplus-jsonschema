```
{
    "WindowThermalModel:Params": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "standard": {
                        "type": "string",
                        "enum": [
                            "",
                            "EN673Declared",
                            "EN673Design",
                            "ISO15099"
                        ],
                        "default": "ISO15099"
                    },
                    "thermal_model": {
                        "type": "string",
                        "enum": [
                            "",
                            "ConvectiveScalarModel_NoSDThickness",
                            "ConvectiveScalarModel_withSDThickness",
                            "ISO15099",
                            "ScaledCavityWidth"
                        ],
                        "default": "ISO15099"
                    },
                    "sdscalar": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "deflection_model": {
                        "type": "string",
                        "enum": [
                            "",
                            "MeasuredDeflection",
                            "NoDeflection",
                            "TemperatureAndPressureInput"
                        ],
                        "default": "NoDeflection"
                    },
                    "vacuum_pressure_limit": {
                        "type": "number",
                        "units": "Pa",
                        "exclusiveMinimum": 0.0,
                        "default": 13.238
                    },
                    "initial_temperature": {
                        "type": "number",
                        "note": "This is temperature in time of window fabrication",
                        "units": "C",
                        "exclusiveMinimum": 0.0,
                        "default": 25.0
                    },
                    "initial_pressure": {
                        "type": "number",
                        "note": "This is pressure in time of window fabrication",
                        "units": "Pa",
                        "exclusiveMinimum": 0.0,
                        "default": 101325.0
                    }
                }
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "WindowThermalModelParameters"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "standard": {
                    "field_name": "standard",
                    "field_type": "a"
                },
                "thermal_model": {
                    "field_name": "Thermal Model",
                    "field_type": "a"
                },
                "sdscalar": {
                    "field_name": "SDScalar",
                    "field_type": "n"
                },
                "deflection_model": {
                    "field_name": "Deflection Model",
                    "field_type": "a"
                },
                "vacuum_pressure_limit": {
                    "field_name": "Vacuum Pressure Limit",
                    "field_type": "n"
                },
                "initial_temperature": {
                    "field_name": "Initial temperature",
                    "field_type": "n"
                },
                "initial_pressure": {
                    "field_name": "Initial pressure",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "standard",
                "thermal_model",
                "sdscalar",
                "deflection_model",
                "vacuum_pressure_limit",
                "initial_temperature",
                "initial_pressure"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "standard",
                    "thermal_model",
                    "deflection_model"
                ]
            },
            "numerics": {
                "fields": [
                    "sdscalar",
                    "vacuum_pressure_limit",
                    "initial_temperature",
                    "initial_pressure"
                ]
            }
        },
        "type": "object",
        "memo": "object is used to select which thermal model should be used in tarcog simulations"
    }
}
```
