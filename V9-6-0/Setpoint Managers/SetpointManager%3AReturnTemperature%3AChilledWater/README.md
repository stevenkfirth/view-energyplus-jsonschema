```
{
    "SetpointManager:ReturnTemperature:ChilledWater": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "plant_loop_supply_outlet_node": {
                        "type": "string",
                        "note": "This is the name of the supply outlet node for the plant being controlled by this setpoint manager. Typically this is where the setpoint will be actuated for supply equipment to control to, but not necessarily. This setpoint manager will mine that information from the internal plant data structures."
                    },
                    "plant_loop_supply_inlet_node": {
                        "type": "string",
                        "note": "This is the name of the supply inlet node for the plant being controlled with this setpoint manager. The temperature on this node is controlled by actuating the supply setpoint."
                    },
                    "minimum_supply_temperature_setpoint": {
                        "type": "number",
                        "note": "This is the minimum chilled water supply temperature setpoint. This is also used as the default setpoint during no-load or negative-load conditions and during initialization.",
                        "units": "C",
                        "default": 5.0
                    },
                    "maximum_supply_temperature_setpoint": {
                        "type": "number",
                        "note": "This is the maximum reset temperature for the chilled water supply.",
                        "units": "C",
                        "default": 10.0
                    },
                    "return_temperature_setpoint_input_type": {
                        "type": "string",
                        "note": "This defines whether the chilled water return temperature target is constant, scheduled, or specified on the supply inlet node by a separate setpoint manager.",
                        "enum": [
                            "Constant",
                            "ReturnTemperatureSetpoint",
                            "Scheduled"
                        ]
                    },
                    "return_temperature_setpoint_constant_value": {
                        "type": "number",
                        "note": "This is the desired return temperature target, which is met by adjusting the supply temperature setpoint. This constant value is only used if the Design Chilled Water Return Temperature Input Type is Constant",
                        "units": "C",
                        "default": 13.0
                    },
                    "return_temperature_setpoint_schedule_name": {
                        "type": "string",
                        "note": "This is the desired return temperature target, which is met by adjusting the supply temperature setpoint. This is a schedule name to allow the return temperature target value to be scheduled. This field is only used if the Design Chilled Water Return Temperature Input Type is Scheduled",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "plant_loop_supply_outlet_node",
                    "plant_loop_supply_inlet_node",
                    "return_temperature_setpoint_input_type"
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
                "plant_loop_supply_outlet_node": {
                    "field_name": "Plant Loop Supply Outlet Node",
                    "field_type": "a"
                },
                "plant_loop_supply_inlet_node": {
                    "field_name": "Plant Loop Supply Inlet Node",
                    "field_type": "a"
                },
                "minimum_supply_temperature_setpoint": {
                    "field_name": "Minimum Supply Temperature Setpoint",
                    "field_type": "n"
                },
                "maximum_supply_temperature_setpoint": {
                    "field_name": "Maximum Supply Temperature Setpoint",
                    "field_type": "n"
                },
                "return_temperature_setpoint_input_type": {
                    "field_name": "Return Temperature Setpoint Input Type",
                    "field_type": "a"
                },
                "return_temperature_setpoint_constant_value": {
                    "field_name": "Return Temperature Setpoint Constant Value",
                    "field_type": "n"
                },
                "return_temperature_setpoint_schedule_name": {
                    "field_name": "Return Temperature Setpoint Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "plant_loop_supply_outlet_node",
                "plant_loop_supply_inlet_node",
                "minimum_supply_temperature_setpoint",
                "maximum_supply_temperature_setpoint",
                "return_temperature_setpoint_input_type",
                "return_temperature_setpoint_constant_value",
                "return_temperature_setpoint_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "plant_loop_supply_outlet_node",
                    "plant_loop_supply_inlet_node",
                    "return_temperature_setpoint_input_type",
                    "return_temperature_setpoint_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_supply_temperature_setpoint",
                    "maximum_supply_temperature_setpoint",
                    "return_temperature_setpoint_constant_value"
                ]
            }
        },
        "type": "object",
        "memo": "This setpoint manager is used to place a temperature setpoint on a plant supply outlet node based on a target return water setpoint. The setpoint manager attempts to achieve the desired return water temperature by adjusting the supply temperature setpoint based on the plant conditions at each system time step.",
        "min_fields": 7.0
    }
}
```
