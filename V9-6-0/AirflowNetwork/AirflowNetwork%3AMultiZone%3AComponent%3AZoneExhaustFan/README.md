```
{
    "AirflowNetwork:MultiZone:Component:ZoneExhaustFan": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "air_mass_flow_coefficient_when_the_zone_exhaust_fan_is_off_at_reference_conditions": {
                        "type": "number",
                        "units": "kg/s",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the air mass flow coefficient at the conditions defined in the Reference Crack Conditions object. Defined at 1 Pa pressure difference. Enter the coefficient used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent. Used only when the fan is off."
                    },
                    "air_mass_flow_exponent_when_the_zone_exhaust_fan_is_off": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.65,
                        "note": "Enter the exponent used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent. Used only when the fan is off."
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
                    "air_mass_flow_coefficient_when_the_zone_exhaust_fan_is_off_at_reference_conditions"
                ]
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "data_type": "object_list",
            "object_list": [
                "FansZoneExhaust"
            ],
            "reference": [
                "SurfaceAirflowLeakageNames"
            ],
            "note": "Enter the name of a Fan:ZoneExhaust object."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "air_mass_flow_coefficient_when_the_zone_exhaust_fan_is_off_at_reference_conditions": {
                    "field_name": "Air Mass Flow Coefficient When the Zone Exhaust Fan is Off at Reference Conditions",
                    "field_type": "n"
                },
                "air_mass_flow_exponent_when_the_zone_exhaust_fan_is_off": {
                    "field_name": "Air Mass Flow Exponent When the Zone Exhaust Fan is Off",
                    "field_type": "n"
                },
                "reference_crack_conditions": {
                    "field_name": "Reference Crack Conditions",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "air_mass_flow_coefficient_when_the_zone_exhaust_fan_is_off_at_reference_conditions",
                "air_mass_flow_exponent_when_the_zone_exhaust_fan_is_off",
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
                    "air_mass_flow_coefficient_when_the_zone_exhaust_fan_is_off_at_reference_conditions",
                    "air_mass_flow_exponent_when_the_zone_exhaust_fan_is_off"
                ]
            }
        },
        "type": "object",
        "memo": "This object specifies the additional properties for a zone exhaust fan to perform multizone airflow calculations.",
        "min_fields": 3.0
    }
}
```
