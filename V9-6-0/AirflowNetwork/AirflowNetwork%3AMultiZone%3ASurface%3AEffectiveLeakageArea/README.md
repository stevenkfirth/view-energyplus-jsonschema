```
{
    "AirflowNetwork:MultiZone:Surface:EffectiveLeakageArea": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "effective_leakage_area": {
                        "type": "number",
                        "units": "m2",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the effective leakage area."
                    },
                    "discharge_coefficient": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0,
                        "note": "Enter the coefficient used in the air mass flow equation."
                    },
                    "reference_pressure_difference": {
                        "type": "number",
                        "units": "Pa",
                        "exclusiveMinimum": 0.0,
                        "default": 4.0,
                        "note": "Enter the pressure difference used to define the air mass flow coefficient and exponent."
                    },
                    "air_mass_flow_exponent": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 0.65,
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "note": "Enter the exponent used in the air mass flow equation."
                    }
                },
                "required": [
                    "effective_leakage_area"
                ]
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SurfaceAirflowLeakageNames"
            ],
            "note": "Enter a unique name for this object."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "effective_leakage_area": {
                    "field_name": "Effective Leakage Area",
                    "field_type": "n"
                },
                "discharge_coefficient": {
                    "field_name": "Discharge Coefficient",
                    "field_type": "n"
                },
                "reference_pressure_difference": {
                    "field_name": "Reference Pressure Difference",
                    "field_type": "n"
                },
                "air_mass_flow_exponent": {
                    "field_name": "Air Mass Flow Exponent",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "effective_leakage_area",
                "discharge_coefficient",
                "reference_pressure_difference",
                "air_mass_flow_exponent"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "effective_leakage_area",
                    "discharge_coefficient",
                    "reference_pressure_difference",
                    "air_mass_flow_exponent"
                ]
            }
        },
        "type": "object",
        "memo": "This object is used to define surface air leakage.",
        "min_fields": 5.0
    }
}
```
