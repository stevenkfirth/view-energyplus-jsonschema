```
{
    "ThermalStorage:ChilledWater:Stratified": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "tank_volume": {
                        "type": "number",
                        "units": "m3",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "gal"
                    },
                    "tank_height": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "note": "Height is measured in the axial direction for horizontal cylinders"
                    },
                    "tank_shape": {
                        "type": "string",
                        "enum": [
                            "",
                            "HorizontalCylinder",
                            "Other",
                            "VerticalCylinder"
                        ],
                        "default": "VerticalCylinder"
                    },
                    "tank_perimeter": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "note": "Only used if Tank Shape is Other"
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
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "temperature_sensor_height": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0
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
                        "note": "required for Ambient Temperature Indicator=Outdoors"
                    },
                    "uniform_skin_loss_coefficient_per_unit_area_to_ambient_temperature": {
                        "type": "number",
                        "units": "W/m2-K",
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
                        "default": 1.0,
                        "note": "The use side effectiveness in the stratified tank model is a simplified analogy of a heat exchanger's effectiveness. This effectiveness is equal to the fraction of use mass flow rate that directly mixes with the tank fluid. And one minus the effectiveness is the fraction that bypasses the tank. The use side mass flow rate that bypasses the tank is mixed with the fluid or water leaving the stratified tank."
                    },
                    "use_side_availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for use side. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "use_side_inlet_height": {
                        "units": "m",
                        "default": "Autocalculate",
                        "note": "Defaults to top of tank",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "use_side_outlet_height": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Defaults to bottom of tank"
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
                        "default": 1.0,
                        "note": "The source side effectiveness in the stratified tank model is a simplified analogy of a heat exchanger's effectiveness. This effectiveness is equal to the fraction of source mass flow rate that directly mixes with the tank fluid. And one minus the effectiveness is the fraction that bypasses the tank. The source side mass flow rate that bypasses the tank is mixed with the fluid or water leaving the stratified tank."
                    },
                    "source_side_availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for use side. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "source_side_inlet_height": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Defaults to bottom of tank"
                    },
                    "source_side_outlet_height": {
                        "units": "m",
                        "default": "Autocalculate",
                        "note": "Defaults to top of tank",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autocalculate"
                                ]
                            }
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
                    },
                    "inlet_mode": {
                        "type": "string",
                        "enum": [
                            "",
                            "Fixed",
                            "Seeking"
                        ],
                        "default": "Fixed"
                    },
                    "number_of_nodes": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 10.0,
                        "default": 1.0
                    },
                    "additional_destratification_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "node_1_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    },
                    "node_2_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    },
                    "node_3_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    },
                    "node_4_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    },
                    "node_5_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    },
                    "node_6_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    },
                    "node_7_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    },
                    "node_8_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    },
                    "node_9_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    },
                    "node_10_additional_loss_coefficient": {
                        "type": "number",
                        "units": "W/K",
                        "default": 0.0
                    }
                },
                "required": [
                    "tank_volume",
                    "tank_height",
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
                "tank_height": {
                    "field_name": "Tank Height",
                    "field_type": "n"
                },
                "tank_shape": {
                    "field_name": "Tank Shape",
                    "field_type": "a"
                },
                "tank_perimeter": {
                    "field_name": "Tank Perimeter",
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
                "temperature_sensor_height": {
                    "field_name": "Temperature Sensor Height",
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
                "uniform_skin_loss_coefficient_per_unit_area_to_ambient_temperature": {
                    "field_name": "Uniform Skin Loss Coefficient per Unit Area to Ambient Temperature",
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
                "use_side_inlet_height": {
                    "field_name": "Use Side Inlet Height",
                    "field_type": "n"
                },
                "use_side_outlet_height": {
                    "field_name": "Use Side Outlet Height",
                    "field_type": "n"
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
                "source_side_inlet_height": {
                    "field_name": "Source Side Inlet Height",
                    "field_type": "n"
                },
                "source_side_outlet_height": {
                    "field_name": "Source Side Outlet Height",
                    "field_type": "n"
                },
                "source_side_design_flow_rate": {
                    "field_name": "Source Side Design Flow Rate",
                    "field_type": "n"
                },
                "tank_recovery_time": {
                    "field_name": "Tank Recovery Time",
                    "field_type": "n"
                },
                "inlet_mode": {
                    "field_name": "Inlet Mode",
                    "field_type": "a"
                },
                "number_of_nodes": {
                    "field_name": "Number of Nodes",
                    "field_type": "n"
                },
                "additional_destratification_conductivity": {
                    "field_name": "Additional Destratification Conductivity",
                    "field_type": "n"
                },
                "node_1_additional_loss_coefficient": {
                    "field_name": "Node 1 Additional Loss Coefficient",
                    "field_type": "n"
                },
                "node_2_additional_loss_coefficient": {
                    "field_name": "Node 2 Additional Loss Coefficient",
                    "field_type": "n"
                },
                "node_3_additional_loss_coefficient": {
                    "field_name": "Node 3 Additional Loss Coefficient",
                    "field_type": "n"
                },
                "node_4_additional_loss_coefficient": {
                    "field_name": "Node 4 Additional Loss Coefficient",
                    "field_type": "n"
                },
                "node_5_additional_loss_coefficient": {
                    "field_name": "Node 5 Additional Loss Coefficient",
                    "field_type": "n"
                },
                "node_6_additional_loss_coefficient": {
                    "field_name": "Node 6 Additional Loss Coefficient",
                    "field_type": "n"
                },
                "node_7_additional_loss_coefficient": {
                    "field_name": "Node 7 Additional Loss Coefficient",
                    "field_type": "n"
                },
                "node_8_additional_loss_coefficient": {
                    "field_name": "Node 8 Additional Loss Coefficient",
                    "field_type": "n"
                },
                "node_9_additional_loss_coefficient": {
                    "field_name": "Node 9 Additional Loss Coefficient",
                    "field_type": "n"
                },
                "node_10_additional_loss_coefficient": {
                    "field_name": "Node 10 Additional Loss Coefficient",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "tank_volume",
                "tank_height",
                "tank_shape",
                "tank_perimeter",
                "setpoint_temperature_schedule_name",
                "deadband_temperature_difference",
                "temperature_sensor_height",
                "minimum_temperature_limit",
                "nominal_cooling_capacity",
                "ambient_temperature_indicator",
                "ambient_temperature_schedule_name",
                "ambient_temperature_zone_name",
                "ambient_temperature_outdoor_air_node_name",
                "uniform_skin_loss_coefficient_per_unit_area_to_ambient_temperature",
                "use_side_inlet_node_name",
                "use_side_outlet_node_name",
                "use_side_heat_transfer_effectiveness",
                "use_side_availability_schedule_name",
                "use_side_inlet_height",
                "use_side_outlet_height",
                "use_side_design_flow_rate",
                "source_side_inlet_node_name",
                "source_side_outlet_node_name",
                "source_side_heat_transfer_effectiveness",
                "source_side_availability_schedule_name",
                "source_side_inlet_height",
                "source_side_outlet_height",
                "source_side_design_flow_rate",
                "tank_recovery_time",
                "inlet_mode",
                "number_of_nodes",
                "additional_destratification_conductivity",
                "node_1_additional_loss_coefficient",
                "node_2_additional_loss_coefficient",
                "node_3_additional_loss_coefficient",
                "node_4_additional_loss_coefficient",
                "node_5_additional_loss_coefficient",
                "node_6_additional_loss_coefficient",
                "node_7_additional_loss_coefficient",
                "node_8_additional_loss_coefficient",
                "node_9_additional_loss_coefficient",
                "node_10_additional_loss_coefficient"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "tank_shape",
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
                    "source_side_availability_schedule_name",
                    "inlet_mode"
                ]
            },
            "numerics": {
                "fields": [
                    "tank_volume",
                    "tank_height",
                    "tank_perimeter",
                    "deadband_temperature_difference",
                    "temperature_sensor_height",
                    "minimum_temperature_limit",
                    "nominal_cooling_capacity",
                    "uniform_skin_loss_coefficient_per_unit_area_to_ambient_temperature",
                    "use_side_heat_transfer_effectiveness",
                    "use_side_inlet_height",
                    "use_side_outlet_height",
                    "use_side_design_flow_rate",
                    "source_side_heat_transfer_effectiveness",
                    "source_side_inlet_height",
                    "source_side_outlet_height",
                    "source_side_design_flow_rate",
                    "tank_recovery_time",
                    "number_of_nodes",
                    "additional_destratification_conductivity",
                    "node_1_additional_loss_coefficient",
                    "node_2_additional_loss_coefficient",
                    "node_3_additional_loss_coefficient",
                    "node_4_additional_loss_coefficient",
                    "node_5_additional_loss_coefficient",
                    "node_6_additional_loss_coefficient",
                    "node_7_additional_loss_coefficient",
                    "node_8_additional_loss_coefficient",
                    "node_9_additional_loss_coefficient",
                    "node_10_additional_loss_coefficient"
                ]
            }
        },
        "type": "object",
        "memo": "Chilled water storage with a stratified, multi-node tank. The chilled water is \"used\" by drawing from the \"Use Side\" of the water tank. The tank is indirectly charged by circulating cold water through the \"Source Side\" of the water tank."
    }
}
```
