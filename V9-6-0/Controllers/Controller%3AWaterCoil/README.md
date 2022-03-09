```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "control_variable": {
                    "type": "string",
                    "enum": [
                        "HumidityRatio",
                        "Temperature",
                        "TemperatureAndHumidityRatio"
                    ],
                    "note": "keys HumidityRatio or TemperatureAndHumidityRatio requires a ZoneControl:Humidistat object along with SetpointManager:SingleZone:Humidity:Maximum, SetpointManager:MultiZone:MaximumHumidity:Average, or SetpointManager:Multizone:Humidity:Maximum object"
                },
                "action": {
                    "type": "string",
                    "enum": [
                        "Normal",
                        "Reverse"
                    ],
                    "note": "Leave blank to have this automatically selected from coil type. Chilled water coils should be reverse action Hot water coils should be normal action"
                },
                "actuator_variable": {
                    "type": "string",
                    "enum": [
                        "Flow"
                    ]
                },
                "sensor_node_name": {
                    "type": "string"
                },
                "actuator_node_name": {
                    "type": "string"
                },
                "controller_convergence_tolerance": {
                    "units": "deltaC",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "maximum_actuated_flow": {
                    "default": "Autosize",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "minimum_actuated_flow": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 0.0,
                    "units": "m3/s",
                    "ip-units": "gal/min"
                }
            },
            "required": [
                "control_variable",
                "actuator_variable",
                "sensor_node_name",
                "actuator_node_name"
            ]
        }
    },
    "group": "Controllers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AirLoopControllers",
            "WaterCoilControllers"
        ]
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
            "action": {
                "field_name": "Action",
                "field_type": "a"
            },
            "actuator_variable": {
                "field_name": "Actuator Variable",
                "field_type": "a"
            },
            "sensor_node_name": {
                "field_name": "Sensor Node Name",
                "field_type": "a"
            },
            "actuator_node_name": {
                "field_name": "Actuator Node Name",
                "field_type": "a"
            },
            "controller_convergence_tolerance": {
                "field_name": "Controller Convergence Tolerance",
                "field_type": "n"
            },
            "maximum_actuated_flow": {
                "field_name": "Maximum Actuated Flow",
                "field_type": "n"
            },
            "minimum_actuated_flow": {
                "field_name": "Minimum Actuated Flow",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "control_variable",
            "action",
            "actuator_variable",
            "sensor_node_name",
            "actuator_node_name",
            "controller_convergence_tolerance",
            "maximum_actuated_flow",
            "minimum_actuated_flow"
        ],
        "alphas": {
            "fields": [
                "name",
                "control_variable",
                "action",
                "actuator_variable",
                "sensor_node_name",
                "actuator_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "controller_convergence_tolerance",
                "maximum_actuated_flow",
                "minimum_actuated_flow"
            ]
        }
    },
    "type": "object",
    "memo": "Controller for a water coil which is located directly in an air loop branch or outdoor air equipment list. Controls the coil water flow to meet the specified leaving air setpoint(s). Used with Coil:Heating:Water, Coil:Cooling:Water, Coil:Cooling:Water:DetailedGeometry, and CoilSystem:Cooling:Water:HeatexchangerAssisted.",
    "min_fields": 9.0
}
```
