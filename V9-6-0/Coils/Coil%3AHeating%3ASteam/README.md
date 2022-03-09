```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "maximum_steam_flow_rate": {
                    "units": "m3/s",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "degree_of_subcooling": {
                    "type": "number",
                    "units": "C",
                    "minimum": 1.0,
                    "maximum": 5.0
                },
                "degree_of_loop_subcooling": {
                    "type": "number",
                    "units": "C",
                    "minimum": 10.0,
                    "default": 20.0
                },
                "water_inlet_node_name": {
                    "type": "string"
                },
                "water_outlet_node_name": {
                    "type": "string"
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "coil_control_type": {
                    "type": "string",
                    "note": "Use ZoneLoadControl if the coil is contained within another component such as an air terminal unit, zone HVAC equipment, or unitary system. Use TemperatureSetpointControl if the coil is located directly in an air loop branch or outdoor air equipment list.",
                    "enum": [
                        "TemperatureSetpointControl",
                        "ZoneLoadControl"
                    ]
                },
                "temperature_setpoint_node_name": {
                    "type": "string",
                    "note": "Required if Coil Control Type is TemperatureSetpointControl"
                }
            },
            "required": [
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "HeatingCoilName",
            "validBranchEquipmentNames",
            "validOASysEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validOASysEquipmentTypes"
        ]
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
            "maximum_steam_flow_rate": {
                "field_name": "Maximum Steam Flow Rate",
                "field_type": "n"
            },
            "degree_of_subcooling": {
                "field_name": "Degree of SubCooling",
                "field_type": "n"
            },
            "degree_of_loop_subcooling": {
                "field_name": "Degree of Loop SubCooling",
                "field_type": "n"
            },
            "water_inlet_node_name": {
                "field_name": "Water Inlet Node Name",
                "field_type": "a"
            },
            "water_outlet_node_name": {
                "field_name": "Water Outlet Node Name",
                "field_type": "a"
            },
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "coil_control_type": {
                "field_name": "Coil Control Type",
                "field_type": "a"
            },
            "temperature_setpoint_node_name": {
                "field_name": "Temperature Setpoint Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "maximum_steam_flow_rate",
            "degree_of_subcooling",
            "degree_of_loop_subcooling",
            "water_inlet_node_name",
            "water_outlet_node_name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "coil_control_type",
            "temperature_setpoint_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "coil_control_type",
                "temperature_setpoint_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_steam_flow_rate",
                "degree_of_subcooling",
                "degree_of_loop_subcooling"
            ]
        }
    },
    "type": "object",
    "memo": "Steam heating coil. Condenses and sub-cools steam at loop pressure and discharges condensate through steam traps to low pressure condensate line."
}
```
