```
{
    "AirflowNetwork:Distribution:Component:LeakageRatio": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "effective_leakage_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "note": "Defined as a ratio of leak flow rate to the maximum flow rate."
                    },
                    "maximum_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the maximum air flow rate in this air loop."
                    },
                    "reference_pressure_difference": {
                        "type": "number",
                        "units": "Pa",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the pressure corresponding to the Effective leakage ratio entered above."
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
                    "maximum_flow_rate",
                    "reference_pressure_difference"
                ]
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AirflowNetworkComponentNames"
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
                "effective_leakage_ratio": {
                    "field_name": "Effective Leakage Ratio",
                    "field_type": "n"
                },
                "maximum_flow_rate": {
                    "field_name": "Maximum Flow Rate",
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
                "effective_leakage_ratio",
                "maximum_flow_rate",
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
                    "effective_leakage_ratio",
                    "maximum_flow_rate",
                    "reference_pressure_difference",
                    "air_mass_flow_exponent"
                ]
            }
        },
        "type": "object",
        "memo": "This object is used to define supply and return air leaks with respect to the fan's maximum air flow rate.",
        "min_fields": 5.0
    }
}
```
