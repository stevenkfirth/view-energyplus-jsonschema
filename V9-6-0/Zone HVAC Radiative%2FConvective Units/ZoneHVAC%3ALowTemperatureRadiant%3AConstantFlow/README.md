```
{
    "ZoneHVAC:LowTemperatureRadiant:ConstantFlow": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "design_object": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "RadiantDesignObject"
                        ]
                    },
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "zone_name": {
                        "type": "string",
                        "note": "Name of zone system is serving",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "surface_name_or_radiant_surface_group_name": {
                        "type": "string",
                        "note": "Identifies surfaces that radiant system is embedded in. For a system with multiple surfaces, enter the name of a ZoneHVAC:LowTemperatureRadiant:SurfaceGroup object.",
                        "data_type": "object_list",
                        "object_list": [
                            "RadiantGroupNames",
                            "RadiantSurfaceNames"
                        ]
                    },
                    "hydronic_tubing_length": {
                        "note": "(total length of pipe embedded in surface)",
                        "units": "m",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
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
                    "rated_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
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
                    "pump_flow_rate_schedule_name": {
                        "type": "string",
                        "note": "Modifies the Rated Flow Rate of the pump on a time basis the default is that the pump is ON and runs according to its other operational requirements specified above. The schedule is for special pump operations. Values here are between 0 and 1 and are multipliers on the previous field (Rated Flow Rate).",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "rated_pump_head": {
                        "type": "number",
                        "units": "Pa",
                        "default": 179352.0,
                        "note": "default head is 60 feet"
                    },
                    "rated_power_consumption": {
                        "type": "number",
                        "units": "W"
                    },
                    "heating_water_inlet_node_name": {
                        "type": "string"
                    },
                    "heating_water_outlet_node_name": {
                        "type": "string"
                    },
                    "heating_high_water_temperature_schedule_name": {
                        "type": "string",
                        "note": "Water and control temperatures for heating work together to provide a linear function that determines the water temperature sent to the radiant system. The current control temperature (see Temperature Control Type above) is compared to the high and low control temperatures at the current time. If the control temperature is above the high temperature, then the inlet water temperature is set to the low water temperature. If the control temperature is below the low temperature, then the inlet water temperature is set to the high water temperature. If the control temperature is between the high and low value, then the inlet water temperature is linearly interpolated between the low and high water temperature values.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_low_water_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_high_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_low_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_water_inlet_node_name": {
                        "type": "string"
                    },
                    "cooling_water_outlet_node_name": {
                        "type": "string"
                    },
                    "cooling_high_water_temperature_schedule_name": {
                        "type": "string",
                        "note": "See note for Heating High Water Temperature Schedule above for interpretation information (or see the Input/Output Reference).",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_low_water_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_high_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_low_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "number_of_circuits": {
                        "type": "string",
                        "enum": [
                            "",
                            "CalculateFromCircuitLength",
                            "OnePerSurface"
                        ],
                        "default": "OnePerSurface"
                    },
                    "circuit_length": {
                        "type": "number",
                        "units": "m",
                        "default": 106.7
                    }
                }
            }
        },
        "group": "Zone HVAC Radiative/Convective Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ],
            "reference": [
                "ZoneEquipmentNames",
                "validBranchEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "design_object": {
                    "field_name": "Design Object",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "surface_name_or_radiant_surface_group_name": {
                    "field_name": "Surface Name or Radiant Surface Group Name",
                    "field_type": "a"
                },
                "hydronic_tubing_length": {
                    "field_name": "Hydronic Tubing Length",
                    "field_type": "n"
                },
                "rated_flow_rate": {
                    "field_name": "Rated Flow Rate",
                    "field_type": "n"
                },
                "pump_flow_rate_schedule_name": {
                    "field_name": "Pump Flow Rate Schedule Name",
                    "field_type": "a"
                },
                "rated_pump_head": {
                    "field_name": "Rated Pump Head",
                    "field_type": "n"
                },
                "rated_power_consumption": {
                    "field_name": "Rated Power Consumption",
                    "field_type": "n"
                },
                "heating_water_inlet_node_name": {
                    "field_name": "Heating Water Inlet Node Name",
                    "field_type": "a"
                },
                "heating_water_outlet_node_name": {
                    "field_name": "Heating Water Outlet Node Name",
                    "field_type": "a"
                },
                "heating_high_water_temperature_schedule_name": {
                    "field_name": "Heating High Water Temperature Schedule Name",
                    "field_type": "a"
                },
                "heating_low_water_temperature_schedule_name": {
                    "field_name": "Heating Low Water Temperature Schedule Name",
                    "field_type": "a"
                },
                "heating_high_control_temperature_schedule_name": {
                    "field_name": "Heating High Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "heating_low_control_temperature_schedule_name": {
                    "field_name": "Heating Low Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_water_inlet_node_name": {
                    "field_name": "Cooling Water Inlet Node Name",
                    "field_type": "a"
                },
                "cooling_water_outlet_node_name": {
                    "field_name": "Cooling Water Outlet Node Name",
                    "field_type": "a"
                },
                "cooling_high_water_temperature_schedule_name": {
                    "field_name": "Cooling High Water Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_low_water_temperature_schedule_name": {
                    "field_name": "Cooling Low Water Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_high_control_temperature_schedule_name": {
                    "field_name": "Cooling High Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_low_control_temperature_schedule_name": {
                    "field_name": "Cooling Low Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "number_of_circuits": {
                    "field_name": "Number of Circuits",
                    "field_type": "a"
                },
                "circuit_length": {
                    "field_name": "Circuit Length",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "design_object",
                "availability_schedule_name",
                "zone_name",
                "surface_name_or_radiant_surface_group_name",
                "hydronic_tubing_length",
                "rated_flow_rate",
                "pump_flow_rate_schedule_name",
                "rated_pump_head",
                "rated_power_consumption",
                "heating_water_inlet_node_name",
                "heating_water_outlet_node_name",
                "heating_high_water_temperature_schedule_name",
                "heating_low_water_temperature_schedule_name",
                "heating_high_control_temperature_schedule_name",
                "heating_low_control_temperature_schedule_name",
                "cooling_water_inlet_node_name",
                "cooling_water_outlet_node_name",
                "cooling_high_water_temperature_schedule_name",
                "cooling_low_water_temperature_schedule_name",
                "cooling_high_control_temperature_schedule_name",
                "cooling_low_control_temperature_schedule_name",
                "number_of_circuits",
                "circuit_length"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "design_object",
                    "availability_schedule_name",
                    "zone_name",
                    "surface_name_or_radiant_surface_group_name",
                    "pump_flow_rate_schedule_name",
                    "heating_water_inlet_node_name",
                    "heating_water_outlet_node_name",
                    "heating_high_water_temperature_schedule_name",
                    "heating_low_water_temperature_schedule_name",
                    "heating_high_control_temperature_schedule_name",
                    "heating_low_control_temperature_schedule_name",
                    "cooling_water_inlet_node_name",
                    "cooling_water_outlet_node_name",
                    "cooling_high_water_temperature_schedule_name",
                    "cooling_low_water_temperature_schedule_name",
                    "cooling_high_control_temperature_schedule_name",
                    "cooling_low_control_temperature_schedule_name",
                    "number_of_circuits"
                ]
            },
            "numerics": {
                "fields": [
                    "hydronic_tubing_length",
                    "rated_flow_rate",
                    "rated_pump_head",
                    "rated_power_consumption",
                    "circuit_length"
                ]
            }
        },
        "type": "object",
        "memo": "Low temperature hydronic radiant heating and/or cooling system embedded in a building surface (wall, ceiling, or floor). Controlled by varying the hot or chilled water temperature circulating through the unit.",
        "min_fields": 24.0
    }
}
```
