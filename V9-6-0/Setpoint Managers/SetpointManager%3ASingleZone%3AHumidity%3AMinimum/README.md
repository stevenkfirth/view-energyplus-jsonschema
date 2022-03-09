```
{
    "SetpointManager:SingleZone:Humidity:Minimum": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "setpoint_node_or_nodelist_name": {
                        "type": "string",
                        "note": "Node(s) at which humidity ratio setpoint will be set"
                    },
                    "control_zone_air_node_name": {
                        "type": "string",
                        "note": "Name of the zone air node for the humidity control zone"
                    }
                },
                "required": [
                    "setpoint_node_or_nodelist_name",
                    "control_zone_air_node_name"
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
                "setpoint_node_or_nodelist_name": {
                    "field_name": "Setpoint Node or NodeList Name",
                    "field_type": "a"
                },
                "control_zone_air_node_name": {
                    "field_name": "Control Zone Air Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "setpoint_node_or_nodelist_name",
                "control_zone_air_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "setpoint_node_or_nodelist_name",
                    "control_zone_air_node_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "The Single Zone Minimum Humidity Setpoint Manager allows the control of a single zone minimum humidity level. This setpoint manager can be used in conjunction with object ZoneControl:Humidistat to detect humidity levels."
    }
}
```
