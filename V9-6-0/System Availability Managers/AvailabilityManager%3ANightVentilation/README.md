```
{
    "AvailabilityManager:NightVentilation": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "applicability_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "fan_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "ventilation_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "One zone temperature must be above this scheduled temperature for night ventilation to be enabled"
                    },
                    "ventilation_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "default": 2.0,
                        "note": "The outdoor air temperature minus the control zone temperature must be greater than the ventilation delta T"
                    },
                    "ventilation_temperature_low_limit": {
                        "type": "number",
                        "units": "C",
                        "default": 15.0,
                        "note": "Night ventilation is disabled if any conditioned zone served by the system falls below this temperature"
                    },
                    "night_venting_flow_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 1.0,
                        "note": "the fraction (could be > 1) of the design system Flow Rate at which night ventilation will be done"
                    },
                    "control_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "When AvailabilityManager:NightVentilation is used in the zone component availability manager assignment list, the Control Zone Name should be the name of the zone in which the zone component is."
                    }
                },
                "required": [
                    "applicability_schedule_name",
                    "fan_schedule_name",
                    "control_zone_name"
                ]
            }
        },
        "group": "System Availability Managers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SystemAvailabilityManagers"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "applicability_schedule_name": {
                    "field_name": "Applicability Schedule Name",
                    "field_type": "a"
                },
                "fan_schedule_name": {
                    "field_name": "Fan Schedule Name",
                    "field_type": "a"
                },
                "ventilation_temperature_schedule_name": {
                    "field_name": "Ventilation Temperature Schedule Name",
                    "field_type": "a"
                },
                "ventilation_temperature_difference": {
                    "field_name": "Ventilation Temperature Difference",
                    "field_type": "n"
                },
                "ventilation_temperature_low_limit": {
                    "field_name": "Ventilation Temperature Low Limit",
                    "field_type": "n"
                },
                "night_venting_flow_fraction": {
                    "field_name": "Night Venting Flow Fraction",
                    "field_type": "n"
                },
                "control_zone_name": {
                    "field_name": "Control Zone Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "applicability_schedule_name",
                "fan_schedule_name",
                "ventilation_temperature_schedule_name",
                "ventilation_temperature_difference",
                "ventilation_temperature_low_limit",
                "night_venting_flow_fraction",
                "control_zone_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "applicability_schedule_name",
                    "fan_schedule_name",
                    "ventilation_temperature_schedule_name",
                    "control_zone_name"
                ]
            },
            "numerics": {
                "fields": [
                    "ventilation_temperature_difference",
                    "ventilation_temperature_low_limit",
                    "night_venting_flow_fraction"
                ]
            }
        },
        "type": "object",
        "memo": "depending on zone and outdoor conditions overrides fan schedule to do precooling with outdoor air",
        "min_fields": 7.0
    }
}
```
