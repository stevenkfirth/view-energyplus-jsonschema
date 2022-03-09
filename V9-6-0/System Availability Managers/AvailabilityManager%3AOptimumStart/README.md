```
{
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
                "control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "ControlZone",
                        "MaximumofZoneList",
                        "StayOff"
                    ],
                    "default": "ControlZone"
                },
                "control_zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "zone_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneListNames"
                    ]
                },
                "maximum_value_for_optimum_start_time": {
                    "type": "number",
                    "default": 6.0,
                    "units": "hr",
                    "note": "this is the maximum number of hours that a system can start before occupancy"
                },
                "control_algorithm": {
                    "type": "string",
                    "enum": [
                        "",
                        "AdaptiveASHRAE",
                        "AdaptiveTemperatureGradient",
                        "ConstantStartTime",
                        "ConstantTemperatureGradient"
                    ],
                    "default": "AdaptiveASHRAE"
                },
                "constant_temperature_gradient_during_cooling": {
                    "type": "number",
                    "units": "deltaC/hr"
                },
                "constant_temperature_gradient_during_heating": {
                    "type": "number",
                    "units": "deltaC/hr"
                },
                "initial_temperature_gradient_during_cooling": {
                    "type": "number",
                    "units": "deltaC/hr"
                },
                "initial_temperature_gradient_during_heating": {
                    "type": "number",
                    "units": "deltaC/hr"
                },
                "constant_start_time": {
                    "type": "number",
                    "units": "hr",
                    "note": "this is the number of hours before occupancy for a system"
                },
                "number_of_previous_days": {
                    "type": "number",
                    "units": "days",
                    "minimum": 2.0,
                    "default": 2.0,
                    "maximum": 5.0,
                    "note": "this is the number of days that their actual temperature gradients will be used in the AdaptiveTemperatureGradient method"
                }
            },
            "required": [
                "applicability_schedule_name",
                "fan_schedule_name"
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
            "control_type": {
                "field_name": "Control Type",
                "field_type": "a"
            },
            "control_zone_name": {
                "field_name": "Control Zone Name",
                "field_type": "a"
            },
            "zone_list_name": {
                "field_name": "Zone List Name",
                "field_type": "a"
            },
            "maximum_value_for_optimum_start_time": {
                "field_name": "Maximum Value for Optimum Start Time",
                "field_type": "n"
            },
            "control_algorithm": {
                "field_name": "Control Algorithm",
                "field_type": "a"
            },
            "constant_temperature_gradient_during_cooling": {
                "field_name": "Constant Temperature Gradient during Cooling",
                "field_type": "n"
            },
            "constant_temperature_gradient_during_heating": {
                "field_name": "Constant Temperature Gradient during Heating",
                "field_type": "n"
            },
            "initial_temperature_gradient_during_cooling": {
                "field_name": "Initial Temperature Gradient during Cooling",
                "field_type": "n"
            },
            "initial_temperature_gradient_during_heating": {
                "field_name": "Initial Temperature Gradient during Heating",
                "field_type": "n"
            },
            "constant_start_time": {
                "field_name": "Constant Start Time",
                "field_type": "n"
            },
            "number_of_previous_days": {
                "field_name": "Number of Previous Days",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "applicability_schedule_name",
            "fan_schedule_name",
            "control_type",
            "control_zone_name",
            "zone_list_name",
            "maximum_value_for_optimum_start_time",
            "control_algorithm",
            "constant_temperature_gradient_during_cooling",
            "constant_temperature_gradient_during_heating",
            "initial_temperature_gradient_during_cooling",
            "initial_temperature_gradient_during_heating",
            "constant_start_time",
            "number_of_previous_days"
        ],
        "alphas": {
            "fields": [
                "name",
                "applicability_schedule_name",
                "fan_schedule_name",
                "control_type",
                "control_zone_name",
                "zone_list_name",
                "control_algorithm"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_value_for_optimum_start_time",
                "constant_temperature_gradient_during_cooling",
                "constant_temperature_gradient_during_heating",
                "initial_temperature_gradient_during_cooling",
                "initial_temperature_gradient_during_heating",
                "constant_start_time",
                "number_of_previous_days"
            ]
        }
    },
    "type": "object",
    "memo": "Determines the optimal start of HVAC systems before occupancy."
}
```
