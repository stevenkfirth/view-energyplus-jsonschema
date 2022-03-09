```
{
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
                "flow_coefficient": {
                    "type": "number",
                    "note": "\"c\" in Equation",
                    "exclusiveMinimum": 0.0
                },
                "stack_coefficient": {
                    "type": "number",
                    "note": "\"Cs\" in Equation",
                    "exclusiveMinimum": 0.0
                },
                "pressure_exponent": {
                    "type": "number",
                    "note": "\"n\" in Equation",
                    "exclusiveMinimum": 0.0,
                    "default": 0.67
                },
                "wind_coefficient": {
                    "type": "number",
                    "note": "\"Cw\" in Equation",
                    "exclusiveMinimum": 0.0
                },
                "shelter_factor": {
                    "type": "number",
                    "note": "\"s\" in Equation",
                    "exclusiveMinimum": 0.0
                }
            },
            "required": [
                "zone_name",
                "schedule_name",
                "flow_coefficient",
                "stack_coefficient",
                "wind_coefficient",
                "shelter_factor"
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
            "flow_coefficient": {
                "field_name": "Flow Coefficient",
                "field_type": "n"
            },
            "stack_coefficient": {
                "field_name": "Stack Coefficient",
                "field_type": "n"
            },
            "pressure_exponent": {
                "field_name": "Pressure Exponent",
                "field_type": "n"
            },
            "wind_coefficient": {
                "field_name": "Wind Coefficient",
                "field_type": "n"
            },
            "shelter_factor": {
                "field_name": "Shelter Factor",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "zone_name",
            "schedule_name",
            "flow_coefficient",
            "stack_coefficient",
            "pressure_exponent",
            "wind_coefficient",
            "shelter_factor"
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
                "flow_coefficient",
                "stack_coefficient",
                "pressure_exponent",
                "wind_coefficient",
                "shelter_factor"
            ]
        }
    },
    "type": "object",
    "memo": "Infiltration is specified as flow coefficient, schedule fraction, stack and wind coefficients, and is a function of temperature difference and wind speed: Infiltration=FSchedule * SQRT( (c * Cs*|(Tzone-Todb)|**n)**2 + (c* Cw*(s * WindSpd)**2n)**2 )",
    "min_fields": 8.0
}
```
