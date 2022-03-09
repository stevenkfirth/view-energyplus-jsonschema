```
{
    "FaultModel:HumiditySensorOffset:OutdoorAir": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "severity_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "controller_object_type": {
                        "type": "string",
                        "enum": [
                            "Controller:OutdoorAir"
                        ]
                    },
                    "controller_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "OAControllerNames"
                        ]
                    },
                    "humidity_sensor_offset": {
                        "type": "number",
                        "exclusiveMinimum": -0.02,
                        "exclusiveMaximum": 0.02,
                        "default": 0.0,
                        "units": "kgWater/kgDryAir"
                    }
                },
                "required": [
                    "controller_object_type",
                    "controller_object_name"
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
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "severity_schedule_name": {
                    "field_name": "Severity Schedule Name",
                    "field_type": "a"
                },
                "controller_object_type": {
                    "field_name": "Controller Object Type",
                    "field_type": "a"
                },
                "controller_object_name": {
                    "field_name": "Controller Object Name",
                    "field_type": "a"
                },
                "humidity_sensor_offset": {
                    "field_name": "Humidity Sensor Offset",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "severity_schedule_name",
                "controller_object_type",
                "controller_object_name",
                "humidity_sensor_offset"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "severity_schedule_name",
                    "controller_object_type",
                    "controller_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "humidity_sensor_offset"
                ]
            }
        },
        "type": "object",
        "memo": "This object describes outdoor air humidity sensor offset",
        "min_fields": 6.0
    }
}
```
