```
{
    "FaultModel:Fouling:AirFilter": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "fan_object_type": {
                        "type": "string",
                        "note": "Choose the type of the fan Support for Fan:SystemModel is pending",
                        "enum": [
                            "Fan:ConstantVolume",
                            "Fan:OnOff",
                            "Fan:VariableVolume"
                        ]
                    },
                    "fan_name": {
                        "type": "string",
                        "note": "Enter the name of a fan object",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandOnOffandVAV",
                            "FansSystemModel"
                        ]
                    },
                    "availability_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "pressure_fraction_schedule_name": {
                        "type": "string",
                        "note": "Enter the name of a schedule describing the variations of the fan pressure rise in terms of multipliers to the fan design pressure rise",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "fan_curve_name": {
                        "type": "string",
                        "note": "The curve describes the relationship between the fan pressure rise and air flow rate",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    }
                },
                "required": [
                    "fan_object_type",
                    "fan_name",
                    "pressure_fraction_schedule_name",
                    "fan_curve_name"
                ]
            }
        },
        "group": "Operational Faults",
        "name": {
            "type": "string",
            "note": "Enter the name of the fault",
            "is_required": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "fan_object_type": {
                    "field_name": "Fan Object Type",
                    "field_type": "a"
                },
                "fan_name": {
                    "field_name": "Fan Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "pressure_fraction_schedule_name": {
                    "field_name": "Pressure Fraction Schedule Name",
                    "field_type": "a"
                },
                "fan_curve_name": {
                    "field_name": "Fan Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "fan_object_type",
                "fan_name",
                "availability_schedule_name",
                "pressure_fraction_schedule_name",
                "fan_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "fan_object_type",
                    "fan_name",
                    "availability_schedule_name",
                    "pressure_fraction_schedule_name",
                    "fan_curve_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object describes fault of dirty air filters",
        "min_fields": 6.0
    }
}
```
