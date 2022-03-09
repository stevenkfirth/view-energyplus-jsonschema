```
{
    "TemperingValve": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "inlet_node_name": {
                        "type": "string",
                        "note": "Name of a Node"
                    },
                    "outlet_node_name": {
                        "type": "string",
                        "note": "Name of a Node"
                    },
                    "stream_2_source_node_name": {
                        "type": "string",
                        "note": "Name of a Node"
                    },
                    "temperature_setpoint_node_name": {
                        "type": "string",
                        "note": "Name of a Node"
                    },
                    "pump_outlet_node_name": {
                        "type": "string"
                    }
                },
                "required": [
                    "inlet_node_name",
                    "outlet_node_name",
                    "stream_2_source_node_name",
                    "temperature_setpoint_node_name",
                    "pump_outlet_node_name"
                ]
            }
        },
        "group": "Plant-Condenser Flow Control",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validCondenserEquipmentTypes",
                "validPlantEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames",
                "validCondenserEquipmentNames",
                "validPlantEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "inlet_node_name": {
                    "field_name": "Inlet Node Name",
                    "field_type": "a"
                },
                "outlet_node_name": {
                    "field_name": "Outlet Node Name",
                    "field_type": "a"
                },
                "stream_2_source_node_name": {
                    "field_name": "Stream 2 Source Node Name",
                    "field_type": "a"
                },
                "temperature_setpoint_node_name": {
                    "field_name": "Temperature Setpoint Node Name",
                    "field_type": "a"
                },
                "pump_outlet_node_name": {
                    "field_name": "Pump Outlet Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "inlet_node_name",
                "outlet_node_name",
                "stream_2_source_node_name",
                "temperature_setpoint_node_name",
                "pump_outlet_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "inlet_node_name",
                    "outlet_node_name",
                    "stream_2_source_node_name",
                    "temperature_setpoint_node_name",
                    "pump_outlet_node_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Temperature-controlled diversion valve used to divert flow around one or more plant components such as a hot water heater. It can only be used on one of two branches between a Splitter and a Mixer."
    }
}
```
