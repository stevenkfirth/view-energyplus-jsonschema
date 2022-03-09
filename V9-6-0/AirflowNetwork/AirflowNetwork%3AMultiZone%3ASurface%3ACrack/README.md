```
{
    "AirflowNetwork:MultiZone:Surface:Crack": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "air_mass_flow_coefficient_at_reference_conditions": {
                        "type": "number",
                        "units": "kg/s",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the air mass flow coefficient at the conditions defined in the Reference Crack Conditions object. Defined at 1 Pa pressure difference across this crack."
                    },
                    "air_mass_flow_exponent": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.65,
                        "note": "Enter the air mass flow exponent for the surface crack."
                    },
                    "reference_crack_conditions": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ReferenceCrackConditions"
                        ],
                        "note": "Select a AirflowNetwork:MultiZone:ReferenceCrackConditions name associated with the air mass flow coefficient entered above."
                    }
                },
                "required": [
                    "air_mass_flow_coefficient_at_reference_conditions"
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
                "air_mass_flow_coefficient_at_reference_conditions": {
                    "field_name": "Air Mass Flow Coefficient at Reference Conditions",
                    "field_type": "n"
                },
                "air_mass_flow_exponent": {
                    "field_name": "Air Mass Flow Exponent",
                    "field_type": "n"
                },
                "reference_crack_conditions": {
                    "field_name": "Reference Crack Conditions",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "air_mass_flow_coefficient_at_reference_conditions",
                "air_mass_flow_exponent",
                "reference_crack_conditions"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "reference_crack_conditions"
                ]
            },
            "numerics": {
                "fields": [
                    "air_mass_flow_coefficient_at_reference_conditions",
                    "air_mass_flow_exponent"
                ]
            }
        },
        "type": "object",
        "memo": "This object specifies the properties of airflow through a crack.",
        "min_fields": 3.0
    }
}
```
