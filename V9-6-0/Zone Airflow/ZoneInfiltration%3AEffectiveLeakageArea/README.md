```
{
    "ZoneInfiltration:EffectiveLeakageArea": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "effective_air_leakage_area": {
                        "type": "number",
                        "units": "cm2",
                        "note": "\"AL\" in Equation units are cm2 (square centimeters)",
                        "exclusiveMinimum": 0.0
                    },
                    "stack_coefficient": {
                        "type": "number",
                        "note": "\"Cs\" in Equation",
                        "exclusiveMinimum": 0.0
                    },
                    "wind_coefficient": {
                        "type": "number",
                        "note": "\"Cw\" in Equation",
                        "exclusiveMinimum": 0.0
                    }
                },
                "required": [
                    "zone_name",
                    "schedule_name",
                    "effective_air_leakage_area",
                    "stack_coefficient",
                    "wind_coefficient"
                ]
            }
        },
        "group": "Zone Airflow",
        "name": {
            "type": "string",
            "is_required": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                },
                "effective_air_leakage_area": {
                    "field_name": "Effective Air Leakage Area",
                    "field_type": "n"
                },
                "stack_coefficient": {
                    "field_name": "Stack Coefficient",
                    "field_type": "n"
                },
                "wind_coefficient": {
                    "field_name": "Wind Coefficient",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "schedule_name",
                "effective_air_leakage_area",
                "stack_coefficient",
                "wind_coefficient"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "effective_air_leakage_area",
                    "stack_coefficient",
                    "wind_coefficient"
                ]
            }
        },
        "type": "object",
        "memo": "Infiltration is specified as effective leakage area at 4 Pa, schedule fraction, stack and wind coefficients, and is a function of temperature difference and wind speed: Infiltration=FSchedule * (AL /1000) SQRT(Cs*|(Tzone-Todb)| +  Cw*WindSpd**2 )",
        "min_fields": 6.0
    }
}
```
