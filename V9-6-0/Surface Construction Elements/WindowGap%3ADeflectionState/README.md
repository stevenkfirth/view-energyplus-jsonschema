```
{
    "WindowGap:DeflectionState": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "deflected_thickness": {
                        "type": "number",
                        "note": "If left blank will be considered that gap has no deflection.",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "initial_temperature": {
                        "type": "number",
                        "units": "C",
                        "minimum": 0.0,
                        "default": 25.0
                    },
                    "initial_pressure": {
                        "type": "number",
                        "units": "Pa",
                        "minimum": 0.0,
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
                "WindowGapDeflectionStates"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "deflected_thickness": {
                    "field_name": "Deflected Thickness",
                    "field_type": "n"
                },
                "initial_temperature": {
                    "field_name": "Initial Temperature",
                    "field_type": "n"
                },
                "initial_pressure": {
                    "field_name": "Initial Pressure",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "deflected_thickness",
                "initial_temperature",
                "initial_pressure"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "deflected_thickness",
                    "initial_temperature",
                    "initial_pressure"
                ]
            }
        },
        "type": "object",
        "memo": "Used to enter data describing deflection state of the gap. It is referenced from WindowMaterial:Gap object only and it is used only when deflection model is set to MeasuredDeflection, otherwise it is ignored."
    }
}
```
