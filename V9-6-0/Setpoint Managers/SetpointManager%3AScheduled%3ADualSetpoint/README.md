```
{
    "SetpointManager:Scheduled:DualSetpoint": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "control_variable": {
                        "type": "string",
                        "enum": [
                            "",
                            "Temperature"
                        ],
                        "default": "Temperature"
                    },
                    "high_setpoint_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "low_setpoint_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "setpoint_node_or_nodelist_name": {
                        "type": "string",
                        "note": "Node(s) at which temperature will be set"
                    }
                },
                "required": [
                    "high_setpoint_schedule_name",
                    "low_setpoint_schedule_name",
                    "setpoint_node_or_nodelist_name"
                ]
            }
        },
        "group": "Setpoint Managers",
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
                "control_variable": {
                    "field_name": "Control Variable",
                    "field_type": "a"
                },
                "high_setpoint_schedule_name": {
                    "field_name": "High Setpoint Schedule Name",
                    "field_type": "a"
                },
                "low_setpoint_schedule_name": {
                    "field_name": "Low Setpoint Schedule Name",
                    "field_type": "a"
                },
                "setpoint_node_or_nodelist_name": {
                    "field_name": "Setpoint Node or NodeList Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "control_variable",
                "high_setpoint_schedule_name",
                "low_setpoint_schedule_name",
                "setpoint_node_or_nodelist_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "control_variable",
                    "high_setpoint_schedule_name",
                    "low_setpoint_schedule_name",
                    "setpoint_node_or_nodelist_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This setpoint manager places a high and low schedule value on one or more nodes."
    }
}
```
