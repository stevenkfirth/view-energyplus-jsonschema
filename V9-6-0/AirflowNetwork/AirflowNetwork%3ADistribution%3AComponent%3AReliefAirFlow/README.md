```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "outdoor_air_mixer_name": {
                    "type": "string",
                    "object_list": [
                        "OutdoorAirMixers"
                    ]
                },
                "air_mass_flow_coefficient_when_no_outdoor_air_flow_at_reference_conditions": {
                    "type": "number",
                    "units": "kg/s",
                    "exclusiveMinimum": 0.0,
                    "note": "Enter the air mass flow coefficient at the conditions defined in the Reference Crack Conditions object. Defined at 1 Pa pressure difference. Enter the coefficient used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent. Used only when no outdoor air flow rate."
                },
                "air_mass_flow_exponent_when_no_outdoor_air_flow": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.5,
                    "maximum": 1.0,
                    "default": 0.65,
                    "note": "Enter the exponent used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent. Used only when no outdoor air flow rate."
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
                "outdoor_air_mixer_name",
                "air_mass_flow_coefficient_when_no_outdoor_air_flow_at_reference_conditions"
            ]
        }
    },
    "group": "AirflowNetwork",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AFNReliefAirFlowNames",
            "AirflowNetworkComponentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "outdoor_air_mixer_name": {
                "field_name": "Outdoor Air Mixer Name",
                "field_type": "a"
            },
            "air_mass_flow_coefficient_when_no_outdoor_air_flow_at_reference_conditions": {
                "field_name": "Air Mass Flow Coefficient When No Outdoor Air Flow at Reference Conditions",
                "field_type": "n"
            },
            "air_mass_flow_exponent_when_no_outdoor_air_flow": {
                "field_name": "Air Mass Flow Exponent When No Outdoor Air Flow",
                "field_type": "n"
            },
            "reference_crack_conditions": {
                "field_name": "Reference Crack Conditions",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "outdoor_air_mixer_name",
            "air_mass_flow_coefficient_when_no_outdoor_air_flow_at_reference_conditions",
            "air_mass_flow_exponent_when_no_outdoor_air_flow",
            "reference_crack_conditions"
        ],
        "alphas": {
            "fields": [
                "name",
                "outdoor_air_mixer_name",
                "reference_crack_conditions"
            ]
        },
        "numerics": {
            "fields": [
                "air_mass_flow_coefficient_when_no_outdoor_air_flow_at_reference_conditions",
                "air_mass_flow_exponent_when_no_outdoor_air_flow"
            ]
        }
    },
    "type": "object",
    "memo": "This object allows variation of air flow rate to perform pressure.",
    "min_fields": 3.0
}
```
