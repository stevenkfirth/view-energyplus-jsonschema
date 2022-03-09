```
{
    "ThermalStorage:ChilledWater:Mixed": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "tank_volume": {
                        "type": "number",
                        "units": "m3",
                        "exclusiveMinimum": 0.0,
                        "default": 0.1,
                        "ip-units": "gal"
                    },
                    "setpoint_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "deadband_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "exclusiveMinimum": 0.0,
                        "default": 0.5
                    },
                    "minimum_temperature_limit": {
                        "type": "number",
                        "units": "C"
                    },
                    "nominal_cooling_capacity": {
                        "type": "number",
                        "units": "W"
                    },
                    "ambient_temperature_indicator": {
                        "type": "string",
                        "enum": [
                            "Outdoors",
                            "Schedule",
                            "Zone"
                        ]
                    },
                    "ambient_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "ambient_temperature_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "ambient_temperature_outdoor_air_node_name": {
                        "type": "string",
                        "note": "required when field Ambient Temperature Indicator=Outdoors"
                    },
                    "heat_gain_coefficient_from_ambient_temperature": {
                        "type": "number",
                        "units": "W/K",
                        "minimum": 0.0
                    },
                    "use_side_inlet_node_name": {
                        "type": "string"
                    },
                    "use_side_outlet_node_name": {
                        "type": "string"
                    },
                    "use_side_heat_transfer_effectiveness": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "use_side_availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for use side. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "use_side_design_flow_rate": {
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
                    "source_side_inlet_node_name": {
                        "type": "string"
                    },
                    "source_side_outlet_node_name": {
                        "type": "string"
                    },
                    "source_side_heat_transfer_effectiveness": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "source_side_availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for source side. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "source_side_design_flow_rate": {
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
                    "tank_recovery_time": {
                        "type": "number",
                        "default": 4.0,
                        "note": "Parameter for autosizing design flow rates for indirectly cooled water tanks time required to lower temperature of entire tank from 14.4C to 9.0C",
                        "units": "hr",
                        "exclusiveMinimum": 0.0
                    }
                },
                "required": [
                    "ambient_temperature_indicator"
                ]
            }
        },
        "group": "Water Heaters and Thermal Storage",
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
                "tank_volume": {
                    "field_name": "Tank Volume",
                    "field_type": "n"
                },
                "setpoint_temperature_schedule_name": {
                    "field_name": "Setpoint Temperature Schedule Name",
                    "field_type": "a"
                },
                "deadband_temperature_difference": {
                    "field_name": "Deadband Temperature Difference",
                    "field_type": "n"
                },
                "minimum_temperature_limit": {
                    "field_name": "Minimum Temperature Limit",
                    "field_type": "n"
                },
                "nominal_cooling_capacity": {
                    "field_name": "Nominal Cooling Capacity",
                    "field_type": "n"
                },
                "ambient_temperature_indicator": {
                    "field_name": "Ambient Temperature Indicator",
                    "field_type": "a"
                },
                "ambient_temperature_schedule_name": {
                    "field_name": "Ambient Temperature Schedule Name",
                    "field_type": "a"
                },
                "ambient_temperature_zone_name": {
                    "field_name": "Ambient Temperature Zone Name",
                    "field_type": "a"
                },
                "ambient_temperature_outdoor_air_node_name": {
                    "field_name": "Ambient Temperature Outdoor Air Node Name",
                    "field_type": "a"
                },
                "heat_gain_coefficient_from_ambient_temperature": {
                    "field_name": "Heat Gain Coefficient from Ambient Temperature",
                    "field_type": "n"
                },
                "use_side_inlet_node_name": {
                    "field_name": "Use Side Inlet Node Name",
                    "field_type": "a"
                },
                "use_side_outlet_node_name": {
                    "field_name": "Use Side Outlet Node Name",
                    "field_type": "a"
                },
                "use_side_heat_transfer_effectiveness": {
                    "field_name": "Use Side Heat Transfer Effectiveness",
                    "field_type": "n"
                },
                "use_side_availability_schedule_name": {
                    "field_name": "Use Side Availability Schedule Name",
                    "field_type": "a"
                },
                "use_side_design_flow_rate": {
                    "field_name": "Use Side Design Flow Rate",
                    "field_type": "n"
                },
                "source_side_inlet_node_name": {
                    "field_name": "Source Side Inlet Node Name",
                    "field_type": "a"
                },
                "source_side_outlet_node_name": {
                    "field_name": "Source Side Outlet Node Name",
                    "field_type": "a"
                },
                "source_side_heat_transfer_effectiveness": {
                    "field_name": "Source Side Heat Transfer Effectiveness",
                    "field_type": "n"
                },
                "source_side_availability_schedule_name": {
                    "field_name": "Source Side Availability Schedule Name",
                    "field_type": "a"
                },
                "source_side_design_flow_rate": {
                    "field_name": "Source Side Design Flow Rate",
                    "field_type": "n"
                },
                "tank_recovery_time": {
                    "field_name": "Tank Recovery Time",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "tank_volume",
                "setpoint_temperature_schedule_name",
                "deadband_temperature_difference",
                "minimum_temperature_limit",
                "nominal_cooling_capacity",
                "ambient_temperature_indicator",
                "ambient_temperature_schedule_name",
                "ambient_temperature_zone_name",
                "ambient_temperature_outdoor_air_node_name",
                "heat_gain_coefficient_from_ambient_temperature",
                "use_side_inlet_node_name",
                "use_side_outlet_node_name",
                "use_side_heat_transfer_effectiveness",
                "use_side_availability_schedule_name",
                "use_side_design_flow_rate",
                "source_side_inlet_node_name",
                "source_side_outlet_node_name",
                "source_side_heat_transfer_effectiveness",
                "source_side_availability_schedule_name",
                "source_side_design_flow_rate",
                "tank_recovery_time"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "setpoint_temperature_schedule_name",
                    "ambient_temperature_indicator",
                    "ambient_temperature_schedule_name",
                    "ambient_temperature_zone_name",
                    "ambient_temperature_outdoor_air_node_name",
                    "use_side_inlet_node_name",
                    "use_side_outlet_node_name",
                    "use_side_availability_schedule_name",
                    "source_side_inlet_node_name",
                    "source_side_outlet_node_name",
                    "source_side_availability_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "tank_volume",
                    "deadband_temperature_difference",
                    "minimum_temperature_limit",
                    "nominal_cooling_capacity",
                    "heat_gain_coefficient_from_ambient_temperature",
                    "use_side_heat_transfer_effectiveness",
                    "use_side_design_flow_rate",
                    "source_side_heat_transfer_effectiveness",
                    "source_side_design_flow_rate",
                    "tank_recovery_time"
                ]
            }
        },
        "type": "object",
        "memo": "Chilled water storage with a well-mixed, single-node tank. The chilled water is \"used\" by drawing from the \"Use Side\" of the water tank. The tank is indirectly charged by circulating cold water through the \"Source Side\" of the water tank."
    }
}
```
