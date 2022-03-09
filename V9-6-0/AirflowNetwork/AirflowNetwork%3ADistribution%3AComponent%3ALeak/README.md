```
{
    "AirflowNetwork:Distribution:Component:Leak": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "air_mass_flow_coefficient": {
                        "type": "number",
                        "units": "kg/s",
                        "exclusiveMinimum": 0.0,
                        "note": "Defined at 1 Pa pressure difference across this component. Enter the coefficient used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent"
                    },
                    "air_mass_flow_exponent": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.65,
                        "note": "Enter the exponent used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent"
                    }
                },
                "required": [
                    "air_mass_flow_coefficient"
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
                "air_mass_flow_coefficient": {
                    "field_name": "Air Mass Flow Coefficient",
                    "field_type": "n"
                },
                "air_mass_flow_exponent": {
                    "field_name": "Air Mass Flow Exponent",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "air_mass_flow_coefficient",
                "air_mass_flow_exponent"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "air_mass_flow_coefficient",
                    "air_mass_flow_exponent"
                ]
            }
        },
        "type": "object",
        "memo": "This object defines the characteristics of a supply or return air leak.",
        "min_fields": 3.0
    }
}
```
