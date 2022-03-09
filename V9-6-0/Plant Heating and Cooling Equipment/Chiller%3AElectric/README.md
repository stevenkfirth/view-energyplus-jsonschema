```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "condenser_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AirCooled",
                        "EvaporativelyCooled",
                        "WaterCooled"
                    ],
                    "default": "AirCooled"
                },
                "nominal_capacity": {
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "nominal_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "chilled_water_inlet_node_name": {
                    "type": "string"
                },
                "chilled_water_outlet_node_name": {
                    "type": "string"
                },
                "condenser_inlet_node_name": {
                    "type": "string"
                },
                "condenser_outlet_node_name": {
                    "type": "string"
                },
                "minimum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0
                },
                "maximum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0
                },
                "optimum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0
                },
                "design_condenser_inlet_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "temperature_rise_coefficient": {
                    "type": "number",
                    "exclusiveMinimum": 0.0
                },
                "design_chilled_water_outlet_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "design_chilled_water_flow_rate": {
                    "note": "For variable volume this is the maximum flow & for constant flow this is the flow.",
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
                                "Autosize"
                            ]
                        }
                    ]
                },
                "design_condenser_fluid_flow_rate": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "note": "This field is only used for Condenser Type = AirCooled or EvaporativelyCooled when Heat Recovery is specified",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "coefficient_1_of_capacity_ratio_curve": {
                    "type": "number"
                },
                "coefficient_2_of_capacity_ratio_curve": {
                    "type": "number"
                },
                "coefficient_3_of_capacity_ratio_curve": {
                    "type": "number"
                },
                "coefficient_1_of_power_ratio_curve": {
                    "type": "number"
                },
                "coefficient_2_of_power_ratio_curve": {
                    "type": "number"
                },
                "coefficient_3_of_power_ratio_curve": {
                    "type": "number"
                },
                "coefficient_1_of_full_load_ratio_curve": {
                    "type": "number"
                },
                "coefficient_2_of_full_load_ratio_curve": {
                    "type": "number"
                },
                "coefficient_3_of_full_load_ratio_curve": {
                    "type": "number"
                },
                "chilled_water_outlet_temperature_lower_limit": {
                    "type": "number",
                    "units": "C"
                },
                "chiller_flow_mode": {
                    "type": "string",
                    "note": "Select operating mode for fluid flow through the chiller. \"NotModulated\" is for either variable or constant pumping with flow controlled by the external plant system. \"ConstantFlow\" is for constant pumping with flow controlled by chiller to operate at full design flow rate. \"LeavingSetpointModulated\" is for variable pumping with flow controlled by chiller to vary flow to target a leaving temperature setpoint.",
                    "enum": [
                        "",
                        "ConstantFlow",
                        "LeavingSetpointModulated",
                        "NotModulated"
                    ],
                    "default": "NotModulated"
                },
                "design_heat_recovery_water_flow_rate": {
                    "units": "m3/s",
                    "default": 0.0,
                    "note": "If non-zero, then the heat recovery inlet and outlet node names must be entered. Heat recovery is only available with Condenser Type = WaterCooled.",
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
                "heat_recovery_inlet_node_name": {
                    "type": "string"
                },
                "heat_recovery_outlet_node_name": {
                    "type": "string"
                },
                "sizing_factor": {
                    "type": "number",
                    "note": "Multiplies the autosized capacity and flow rates",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "basin_heater_capacity": {
                    "type": "number",
                    "units": "W/K",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled and for periods when the basin heater is available (field Basin Heater Operating Schedule Name). For this situation, the heater maintains the basin water temperature at the basin heater setpoint temperature when the outdoor air temperature falls below the setpoint temperature. The basin heater only operates when the chiller is not operating."
                },
                "basin_heater_setpoint_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 2.0,
                    "default": 2.0,
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled. Enter the outdoor dry-bulb temperature when the basin heater turns on."
                },
                "basin_heater_operating_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled. Schedule values greater than 0 allow the basin heater to operate whenever the outdoor air dry-bulb temperature is below the basin heater setpoint temperature. If a schedule name is not entered, the basin heater is allowed to operate throughout the entire simulation."
                },
                "condenser_heat_recovery_relative_capacity_fraction": {
                    "type": "number",
                    "note": "This optional field is the fraction of total rejected heat that can be recovered at full load",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "heat_recovery_inlet_high_temperature_limit_schedule_name": {
                    "type": "string",
                    "note": "This optional schedule of temperatures will turn off heat recovery if inlet exceeds the value",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "heat_recovery_leaving_temperature_setpoint_node_name": {
                    "type": "string",
                    "note": "This optional field provides control over the heat recovery Using this triggers a model more suited to series bundle and chillers with higher temperature heat recovery If this field is not used, the bundles are modeled as being in parallel"
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                }
            },
            "required": [
                "nominal_capacity",
                "nominal_cop",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "temperature_rise_coefficient"
            ]
        }
    },
    "group": "Plant Heating and Cooling Equipment",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "Chillers",
            "validBranchEquipmentNames",
            "validPlantEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validPlantEquipmentTypes"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "condenser_type": {
                "field_name": "Condenser Type",
                "field_type": "a"
            },
            "nominal_capacity": {
                "field_name": "Nominal Capacity",
                "field_type": "n"
            },
            "nominal_cop": {
                "field_name": "Nominal COP",
                "field_type": "n"
            },
            "chilled_water_inlet_node_name": {
                "field_name": "Chilled Water Inlet Node Name",
                "field_type": "a"
            },
            "chilled_water_outlet_node_name": {
                "field_name": "Chilled Water Outlet Node Name",
                "field_type": "a"
            },
            "condenser_inlet_node_name": {
                "field_name": "Condenser Inlet Node Name",
                "field_type": "a"
            },
            "condenser_outlet_node_name": {
                "field_name": "Condenser Outlet Node Name",
                "field_type": "a"
            },
            "minimum_part_load_ratio": {
                "field_name": "Minimum Part Load Ratio",
                "field_type": "n"
            },
            "maximum_part_load_ratio": {
                "field_name": "Maximum Part Load Ratio",
                "field_type": "n"
            },
            "optimum_part_load_ratio": {
                "field_name": "Optimum Part Load Ratio",
                "field_type": "n"
            },
            "design_condenser_inlet_temperature": {
                "field_name": "Design Condenser Inlet Temperature",
                "field_type": "n"
            },
            "temperature_rise_coefficient": {
                "field_name": "Temperature Rise Coefficient",
                "field_type": "n"
            },
            "design_chilled_water_outlet_temperature": {
                "field_name": "Design Chilled Water Outlet Temperature",
                "field_type": "n"
            },
            "design_chilled_water_flow_rate": {
                "field_name": "Design Chilled Water Flow Rate",
                "field_type": "n"
            },
            "design_condenser_fluid_flow_rate": {
                "field_name": "Design Condenser Fluid Flow Rate",
                "field_type": "n"
            },
            "coefficient_1_of_capacity_ratio_curve": {
                "field_name": "Coefficient 1 of Capacity Ratio Curve",
                "field_type": "n"
            },
            "coefficient_2_of_capacity_ratio_curve": {
                "field_name": "Coefficient 2 of Capacity Ratio Curve",
                "field_type": "n"
            },
            "coefficient_3_of_capacity_ratio_curve": {
                "field_name": "Coefficient 3 of Capacity Ratio Curve",
                "field_type": "n"
            },
            "coefficient_1_of_power_ratio_curve": {
                "field_name": "Coefficient 1 of Power Ratio Curve",
                "field_type": "n"
            },
            "coefficient_2_of_power_ratio_curve": {
                "field_name": "Coefficient 2 of Power Ratio Curve",
                "field_type": "n"
            },
            "coefficient_3_of_power_ratio_curve": {
                "field_name": "Coefficient 3 of Power Ratio Curve",
                "field_type": "n"
            },
            "coefficient_1_of_full_load_ratio_curve": {
                "field_name": "Coefficient 1 of Full Load Ratio Curve",
                "field_type": "n"
            },
            "coefficient_2_of_full_load_ratio_curve": {
                "field_name": "Coefficient 2 of Full Load Ratio Curve",
                "field_type": "n"
            },
            "coefficient_3_of_full_load_ratio_curve": {
                "field_name": "Coefficient 3 of Full Load Ratio Curve",
                "field_type": "n"
            },
            "chilled_water_outlet_temperature_lower_limit": {
                "field_name": "Chilled Water Outlet Temperature Lower Limit",
                "field_type": "n"
            },
            "chiller_flow_mode": {
                "field_name": "Chiller Flow Mode",
                "field_type": "a"
            },
            "design_heat_recovery_water_flow_rate": {
                "field_name": "Design Heat Recovery Water Flow Rate",
                "field_type": "n"
            },
            "heat_recovery_inlet_node_name": {
                "field_name": "Heat Recovery Inlet Node Name",
                "field_type": "a"
            },
            "heat_recovery_outlet_node_name": {
                "field_name": "Heat Recovery Outlet Node Name",
                "field_type": "a"
            },
            "sizing_factor": {
                "field_name": "Sizing Factor",
                "field_type": "n"
            },
            "basin_heater_capacity": {
                "field_name": "Basin Heater Capacity",
                "field_type": "n"
            },
            "basin_heater_setpoint_temperature": {
                "field_name": "Basin Heater Setpoint Temperature",
                "field_type": "n"
            },
            "basin_heater_operating_schedule_name": {
                "field_name": "Basin Heater Operating Schedule Name",
                "field_type": "a"
            },
            "condenser_heat_recovery_relative_capacity_fraction": {
                "field_name": "Condenser Heat Recovery Relative Capacity Fraction",
                "field_type": "n"
            },
            "heat_recovery_inlet_high_temperature_limit_schedule_name": {
                "field_name": "Heat Recovery Inlet High Temperature Limit Schedule Name",
                "field_type": "a"
            },
            "heat_recovery_leaving_temperature_setpoint_node_name": {
                "field_name": "Heat Recovery Leaving Temperature Setpoint Node Name",
                "field_type": "a"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "condenser_type",
            "nominal_capacity",
            "nominal_cop",
            "chilled_water_inlet_node_name",
            "chilled_water_outlet_node_name",
            "condenser_inlet_node_name",
            "condenser_outlet_node_name",
            "minimum_part_load_ratio",
            "maximum_part_load_ratio",
            "optimum_part_load_ratio",
            "design_condenser_inlet_temperature",
            "temperature_rise_coefficient",
            "design_chilled_water_outlet_temperature",
            "design_chilled_water_flow_rate",
            "design_condenser_fluid_flow_rate",
            "coefficient_1_of_capacity_ratio_curve",
            "coefficient_2_of_capacity_ratio_curve",
            "coefficient_3_of_capacity_ratio_curve",
            "coefficient_1_of_power_ratio_curve",
            "coefficient_2_of_power_ratio_curve",
            "coefficient_3_of_power_ratio_curve",
            "coefficient_1_of_full_load_ratio_curve",
            "coefficient_2_of_full_load_ratio_curve",
            "coefficient_3_of_full_load_ratio_curve",
            "chilled_water_outlet_temperature_lower_limit",
            "chiller_flow_mode",
            "design_heat_recovery_water_flow_rate",
            "heat_recovery_inlet_node_name",
            "heat_recovery_outlet_node_name",
            "sizing_factor",
            "basin_heater_capacity",
            "basin_heater_setpoint_temperature",
            "basin_heater_operating_schedule_name",
            "condenser_heat_recovery_relative_capacity_fraction",
            "heat_recovery_inlet_high_temperature_limit_schedule_name",
            "heat_recovery_leaving_temperature_setpoint_node_name",
            "end_use_subcategory"
        ],
        "alphas": {
            "fields": [
                "name",
                "condenser_type",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name",
                "chiller_flow_mode",
                "heat_recovery_inlet_node_name",
                "heat_recovery_outlet_node_name",
                "basin_heater_operating_schedule_name",
                "heat_recovery_inlet_high_temperature_limit_schedule_name",
                "heat_recovery_leaving_temperature_setpoint_node_name",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "nominal_capacity",
                "nominal_cop",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "design_condenser_inlet_temperature",
                "temperature_rise_coefficient",
                "design_chilled_water_outlet_temperature",
                "design_chilled_water_flow_rate",
                "design_condenser_fluid_flow_rate",
                "coefficient_1_of_capacity_ratio_curve",
                "coefficient_2_of_capacity_ratio_curve",
                "coefficient_3_of_capacity_ratio_curve",
                "coefficient_1_of_power_ratio_curve",
                "coefficient_2_of_power_ratio_curve",
                "coefficient_3_of_power_ratio_curve",
                "coefficient_1_of_full_load_ratio_curve",
                "coefficient_2_of_full_load_ratio_curve",
                "coefficient_3_of_full_load_ratio_curve",
                "chilled_water_outlet_temperature_lower_limit",
                "design_heat_recovery_water_flow_rate",
                "sizing_factor",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "condenser_heat_recovery_relative_capacity_fraction"
            ]
        }
    },
    "type": "object",
    "memo": "This chiller model is the empirical model from the Building Loads and System Thermodynamics (BLAST) program. Chiller performance curves are generated by fitting catalog data to third order polynomial equations. Three sets of coefficients are required.",
    "min_fields": 27.0
}
```
