```
{
    "SetpointManager:Scheduled": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "control_variable": {
                        "type": "string",
                        "enum": [
                            "HumidityRatio",
                            "MassFlowRate",
                            "MaximumHumidityRatio",
                            "MaximumMassFlowRate",
                            "MaximumTemperature",
                            "MinimumHumidityRatio",
                            "MinimumMassFlowRate",
                            "MinimumTemperature",
                            "Temperature"
                        ]
                    },
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "setpoint_node_or_nodelist_name": {
                        "type": "string",
                        "note": "Node(s) at which control variable will be set"
                    }
                },
                "required": [
                    "control_variable",
                    "schedule_name",
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
                "schedule_name": {
                    "field_name": "Schedule Name",
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
                "schedule_name",
                "setpoint_node_or_nodelist_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "control_variable",
                    "schedule_name",
                    "setpoint_node_or_nodelist_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "The simplest Setpoint Manager simply uses a schedule to determine one or more setpoints. Values of the nodes are not used as input."
    }
}
```
