```
{
    "Chiller:EngineDriven": {
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
                        "note": "Nominal Refrigeration Cycle COP",
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
                        "note": "For variable volume this is the maximum flow and for constant flow this is the flow.",
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
                    "design_condenser_water_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "note": "This field is not used for Condenser Type = AirCooled or EvaporativelyCooled",
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
                        "units": "C",
                        "note": "Special EngineDriven Chiller Parameters Below"
                    },
                    "fuel_use_curve_name": {
                        "type": "string",
                        "note": "Curve is a function of Part Load Ratio (PLR) curve = a + b*PLR + c*PLR**2 PLR = Ratio of evaporator heat transfer rate to nominal capacity",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "jacket_heat_recovery_curve_name": {
                        "type": "string",
                        "note": "Curve is a function of Part Load Ratio (PLR) curve = a + b*PLR + c*PLR**2 PLR = Ratio of evaporator heat transfer rate to nominal capacity",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "lube_heat_recovery_curve_name": {
                        "type": "string",
                        "note": "Curve is a function of Part Load Ratio (PLR) curve = a + b*PLR + c*PLR**2 PLR = Ratio of evaporator heat transfer rate to nominal capacity",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "total_exhaust_energy_curve_name": {
                        "type": "string",
                        "note": "Curve is a function of Part Load Ratio (PLR) curve = a + b*PLR + c*PLR**2 PLR = Ratio of evaporator heat transfer rate to nominal capacity",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "exhaust_temperature_curve_name": {
                        "type": "string",
                        "note": "Curve is a function of Part Load Ratio (PLR) curve = a + b*PLR + c*PLR**2 PLR = Ratio of evaporator heat transfer rate to nominal capacity",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "coefficient_1_of_u_factor_times_area_curve": {
                        "type": "number",
                        "note": "curve = C1 * (nominal capacity)**C2"
                    },
                    "coefficient_2_of_u_factor_times_area_curve": {
                        "type": "number",
                        "note": "curve = C1 * (nominal capacity)**C2 typical value .9",
                        "maximum": 2.0
                    },
                    "maximum_exhaust_flow_per_unit_of_power_output": {
                        "type": "number",
                        "units": "(kg/s)/W",
                        "minimum": 0.0
                    },
                    "design_minimum_exhaust_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "fuel_type": {
                        "type": "string",
                        "enum": [
                            "Diesel",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane"
                        ]
                    },
                    "fuel_higher_heating_value": {
                        "type": "number",
                        "units": "kJ/kg"
                    },
                    "design_heat_recovery_water_flow_rate": {
                        "units": "m3/s",
                        "default": 0.0,
                        "note": "If non-zero, then the heat recovery inlet and outlet node names must be entered.",
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
                    "maximum_temperature_for_heat_recovery_at_heat_recovery_outlet_node": {
                        "type": "number",
                        "units": "C",
                        "maximum": 100.0,
                        "minimum": 0.0,
                        "default": 60.0
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
                        "note": "This optional field is the fraction of total rejected heat that can be recovered at full load. Also used to autosize Design Heat Recovery Water Flow Rate as a fraction of Design Condenser Water Flow Rate.",
                        "minimum": 0.0,
                        "maximum": 1.0
                    }
                },
                "required": [
                    "nominal_capacity",
                    "nominal_cop",
                    "chilled_water_inlet_node_name",
                    "chilled_water_outlet_node_name",
                    "temperature_rise_coefficient",
                    "fuel_type"
                ]
            }
        },
        "group": "Plant Heating and Cooling Equipment",
        "name": {
            "type": "string",
            "reference": [
                "Chillers",
                "validBranchEquipmentNames",
                "validPlantEquipmentNames"
            ],
            "is_required": true,
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
                "design_condenser_water_flow_rate": {
                    "field_name": "Design Condenser Water Flow Rate",
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
                "fuel_use_curve_name": {
                    "field_name": "Fuel Use Curve Name",
                    "field_type": "a"
                },
                "jacket_heat_recovery_curve_name": {
                    "field_name": "Jacket Heat Recovery Curve Name",
                    "field_type": "a"
                },
                "lube_heat_recovery_curve_name": {
                    "field_name": "Lube Heat Recovery Curve Name",
                    "field_type": "a"
                },
                "total_exhaust_energy_curve_name": {
                    "field_name": "Total Exhaust Energy Curve Name",
                    "field_type": "a"
                },
                "exhaust_temperature_curve_name": {
                    "field_name": "Exhaust Temperature Curve Name",
                    "field_type": "a"
                },
                "coefficient_1_of_u_factor_times_area_curve": {
                    "field_name": "Coefficient 1 of U-Factor Times Area Curve",
                    "field_type": "n"
                },
                "coefficient_2_of_u_factor_times_area_curve": {
                    "field_name": "Coefficient 2 of U-Factor Times Area Curve",
                    "field_type": "n"
                },
                "maximum_exhaust_flow_per_unit_of_power_output": {
                    "field_name": "Maximum Exhaust Flow per Unit of Power Output",
                    "field_type": "n"
                },
                "design_minimum_exhaust_temperature": {
                    "field_name": "Design Minimum Exhaust Temperature",
                    "field_type": "n"
                },
                "fuel_type": {
                    "field_name": "Fuel Type",
                    "field_type": "a"
                },
                "fuel_higher_heating_value": {
                    "field_name": "Fuel Higher Heating Value",
                    "field_type": "n"
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
                "chiller_flow_mode": {
                    "field_name": "Chiller Flow Mode",
                    "field_type": "a"
                },
                "maximum_temperature_for_heat_recovery_at_heat_recovery_outlet_node": {
                    "field_name": "Maximum Temperature for Heat Recovery at Heat Recovery Outlet Node",
                    "field_type": "n"
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
                "design_condenser_water_flow_rate",
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
                "fuel_use_curve_name",
                "jacket_heat_recovery_curve_name",
                "lube_heat_recovery_curve_name",
                "total_exhaust_energy_curve_name",
                "exhaust_temperature_curve_name",
                "coefficient_1_of_u_factor_times_area_curve",
                "coefficient_2_of_u_factor_times_area_curve",
                "maximum_exhaust_flow_per_unit_of_power_output",
                "design_minimum_exhaust_temperature",
                "fuel_type",
                "fuel_higher_heating_value",
                "design_heat_recovery_water_flow_rate",
                "heat_recovery_inlet_node_name",
                "heat_recovery_outlet_node_name",
                "chiller_flow_mode",
                "maximum_temperature_for_heat_recovery_at_heat_recovery_outlet_node",
                "sizing_factor",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "basin_heater_operating_schedule_name",
                "condenser_heat_recovery_relative_capacity_fraction"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "condenser_type",
                    "chilled_water_inlet_node_name",
                    "chilled_water_outlet_node_name",
                    "condenser_inlet_node_name",
                    "condenser_outlet_node_name",
                    "fuel_use_curve_name",
                    "jacket_heat_recovery_curve_name",
                    "lube_heat_recovery_curve_name",
                    "total_exhaust_energy_curve_name",
                    "exhaust_temperature_curve_name",
                    "fuel_type",
                    "heat_recovery_inlet_node_name",
                    "heat_recovery_outlet_node_name",
                    "chiller_flow_mode",
                    "basin_heater_operating_schedule_name"
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
                    "design_condenser_water_flow_rate",
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
                    "coefficient_1_of_u_factor_times_area_curve",
                    "coefficient_2_of_u_factor_times_area_curve",
                    "maximum_exhaust_flow_per_unit_of_power_output",
                    "design_minimum_exhaust_temperature",
                    "fuel_higher_heating_value",
                    "design_heat_recovery_water_flow_rate",
                    "maximum_temperature_for_heat_recovery_at_heat_recovery_outlet_node",
                    "sizing_factor",
                    "basin_heater_capacity",
                    "basin_heater_setpoint_temperature",
                    "condenser_heat_recovery_relative_capacity_fraction"
                ]
            }
        },
        "type": "object",
        "memo": "This chiller model is the empirical model from the Building Loads and System Thermodynamics (BLAST) program. Chiller performance curves are generated by fitting catalog data to third order polynomial equations. Three sets of coefficients are required.",
        "min_fields": 43.0
    }
}
```
