```
{
    "Coil:Heating:Electric": {
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
                    "efficiency": {
                        "type": "number",
                        "maximum": 1.0,
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "nominal_capacity": {
                        "units": "W",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "temperature_setpoint_node_name": {
                        "type": "string",
                        "note": "Required if coil is temperature controlled."
                    }
                },
                "required": [
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
                "AFNCoilNames",
                "HeatingCoilName",
                "HeatingCoilsElectric",
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
                "efficiency": {
                    "field_name": "Efficiency",
                    "field_type": "n"
                },
                "nominal_capacity": {
                    "field_name": "Nominal Capacity",
                    "field_type": "n"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
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
                "efficiency",
                "nominal_capacity",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "temperature_setpoint_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "temperature_setpoint_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "efficiency",
                    "nominal_capacity"
                ]
            }
        },
        "type": "object",
        "memo": "Electric heating coil. If the coil is located directly in an air loop branch or outdoor air equipment list, then it is controlled on leaving air temperature and the Temperature Setpoint Node Name must be specified. If the coil is contained within another component such as an air terminal unit, zone HVAC equipment, or unitary system, then the coil is controlled by the parent component and the setpoint node name is not entered."
    }
}
```
