```
{
    "AirflowNetwork:ZoneControl:PressureController": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "control_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "control_object_type": {
                        "type": "string",
                        "enum": [
                            "AirflowNetwork:Distribution:Component:ReliefAirFlow",
                            "AirflowNetwork:MultiZone:Component:ZoneExhaustFan"
                        ],
                        "note": "The current selection is AirflowNetwork:MultiZone:Component:ZoneExhaustFan or AirflowNetwork:Distribution:Component:ReliefAirFlow."
                    },
                    "control_object_name": {
                        "type": "string",
                        "note": "Control names are names of individual control objects",
                        "data_type": "object_list",
                        "object_list": [
                            "AFNReliefAirFlowNames",
                            "FansZoneExhaust"
                        ]
                    },
                    "pressure_control_availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for pressure controller. Schedule value > 0 means the pressure controller is enabled. If this field is blank, then pressure controller is always enabled.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "pressure_setpoint_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "control_zone_name",
                    "control_object_type",
                    "control_object_name",
                    "pressure_setpoint_schedule_name"
                ]
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AirflowNetworkZoneControlPressureControllerNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "control_zone_name": {
                    "field_name": "Control Zone Name",
                    "field_type": "a"
                },
                "control_object_type": {
                    "field_name": "Control Object Type",
                    "field_type": "a"
                },
                "control_object_name": {
                    "field_name": "Control Object Name",
                    "field_type": "a"
                },
                "pressure_control_availability_schedule_name": {
                    "field_name": "Pressure Control Availability Schedule Name",
                    "field_type": "a"
                },
                "pressure_setpoint_schedule_name": {
                    "field_name": "Pressure Setpoint Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "control_zone_name",
                "control_object_type",
                "control_object_name",
                "pressure_control_availability_schedule_name",
                "pressure_setpoint_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "control_zone_name",
                    "control_object_type",
                    "control_object_name",
                    "pressure_control_availability_schedule_name",
                    "pressure_setpoint_schedule_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "This object is used to control a zone to a specified indoor pressure using the AirflowNetwork model. The specified pressure setpoint is used to control the zone exhaust fan flow rate in a controlled zone or the relief air flow rate in an air loop."
    }
}
```
