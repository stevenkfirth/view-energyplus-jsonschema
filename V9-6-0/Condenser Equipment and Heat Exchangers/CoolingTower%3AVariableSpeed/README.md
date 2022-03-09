```
{
    "CoolingTower:VariableSpeed": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "water_inlet_node_name": {
                        "type": "string",
                        "note": "Name of tower water inlet node"
                    },
                    "water_outlet_node_name": {
                        "type": "string",
                        "note": "Name of tower water outlet node"
                    },
                    "model_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "CoolToolsCrossFlow",
                            "CoolToolsUserDefined",
                            "YorkCalc",
                            "YorkCalcUserDefined"
                        ],
                        "default": "YorkCalc",
                        "note": "Determines the coefficients and form of the equation for calculating approach temperature"
                    },
                    "model_coefficient_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "VariableSpeedTowerCoefficient"
                        ],
                        "note": "Name of the tower model coefficient object. Used only when tower Model Type is either CoolToolsUserDefined or YorkCalcUserDefined."
                    },
                    "design_inlet_air_wet_bulb_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 25.6,
                        "minimum": 20.0,
                        "note": "Enter the tower's design inlet air wet-bulb temperature"
                    },
                    "design_approach_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "default": 3.9,
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the approach temperature corresponding to the design inlet air wet-bulb temperature and design range temperature. Design approach temp = outlet water temperature minus inlet air wet-bulb temperature at design conditions."
                    },
                    "design_range_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "default": 5.6,
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the range temperature corresponding to the design inlet air wet-bulb temperature and design approach temperature. Design range = inlet water temperature minus outlet water temperature at design conditions."
                    },
                    "design_water_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "note": "Water flow rate through the tower at design conditions",
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
                    "design_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Design (maximum) air flow rate through the tower",
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
                    "design_fan_power": {
                        "units": "W",
                        "ip-units": "W",
                        "note": "Enter the fan motor electric input power at design (max) air flow through the tower Standard conversion for horsepower is 1 HP = 745.7 W",
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
                    "fan_power_ratio_function_of_air_flow_rate_ratio_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "FPR = a + b*AFR + c*AFR**2 + d*AFR**3 FPR = fraction of the design fan power AFR = fraction of the design air flow rate If left blank, then fan power is assumed to be proportional to (air flow rate ratio)^3"
                    },
                    "minimum_air_flow_rate_ratio": {
                        "type": "number",
                        "minimum": 0.2,
                        "maximum": 0.5,
                        "default": 0.2,
                        "note": "Enter the minimum air flow rate ratio. This is typically determined by the variable speed drive that controls the fan motor speed. Valid entries are from 0.2 to 0.5."
                    },
                    "fraction_of_tower_capacity_in_free_convection_regime": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 0.2,
                        "default": 0.125,
                        "note": "Enter the fraction of tower capacity in the free convection regime. This is the fraction of the tower capacity, at the current inlet air wet-bulb temperature, that is available when the tower fan is off. Manufacturers typically estimate the free convection capacity at approximately 10-15%. Values are entered as a fraction and can range from 0 to 0.2."
                    },
                    "basin_heater_capacity": {
                        "type": "number",
                        "units": "W/K",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "This heater maintains the basin water temperature at the basin heater setpoint temperature when the outdoor air temperature falls below the setpoint temperature. The basin heater only operates when water is not flowing through the tower."
                    },
                    "basin_heater_setpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "minimum": 2.0,
                        "default": 2.0,
                        "note": "Enter the outdoor dry-bulb temperature when the basin heater turns on"
                    },
                    "basin_heater_operating_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values greater than 0 allow the basin heater to operate whenever the outdoor air dry-bulb temperature is below the basin heater setpoint temperature. If a schedule name is not entered, the basin heater is allowed to operate throughout the entire simulation."
                    },
                    "evaporation_loss_mode": {
                        "type": "string",
                        "enum": [
                            "LossFactor",
                            "SaturatedExit"
                        ]
                    },
                    "evaporation_loss_factor": {
                        "type": "number",
                        "units": "percent/K",
                        "note": "Rate of water evaporated from the cooling tower and lost to the outdoor air [%/K] Evaporation loss is calculated as percentage of the circulating condenser water rate Value entered here is percent-per-degree K of temperature drop in the condenser water Typical values are from 0.15 to 0.27 [percent/K].",
                        "default": 0.2
                    },
                    "drift_loss_percent": {
                        "type": "number",
                        "units": "percent",
                        "note": "Rate of drift loss as a percentage of circulating condenser water flow rate Typical values are between 0.002 and 0.2% The default value is 0.008%"
                    },
                    "blowdown_calculation_mode": {
                        "type": "string",
                        "enum": [
                            "ConcentrationRatio",
                            "ScheduledRate"
                        ]
                    },
                    "blowdown_concentration_ratio": {
                        "type": "number",
                        "minimum": 2.0,
                        "default": 3.0,
                        "note": "Characterizes the rate of blowdown in the cooling tower. Blowdown is water intentionally drained from the tower in order to offset the build up of solids in the water that would otherwise occur because of evaporation. Ratio of solids in the blowdown water to solids in the make up water. Typical values for tower operation are 3 to 5. The default value is 3."
                    },
                    "blowdown_makeup_water_usage_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Makeup water usage due to blowdown results from occasionally draining a small amount of water in the tower basin to purge scale or other contaminants to reduce their concentration in order to maintain an acceptable level of water quality. Schedule values should reflect water usage in m3/s."
                    },
                    "supply_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    },
                    "outdoor_air_inlet_node_name": {
                        "type": "string",
                        "note": "Enter the name of an outdoor air node"
                    },
                    "number_of_cells": {
                        "type": "number",
                        "minimum": 1.0,
                        "default": 1.0
                    },
                    "cell_control": {
                        "type": "string",
                        "enum": [
                            "",
                            "MaximalCell",
                            "MinimalCell"
                        ],
                        "default": "MinimalCell"
                    },
                    "cell_minimum_water_flow_rate_fraction": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.33,
                        "note": "The allowable minimal fraction of the nominal flow rate per cell"
                    },
                    "cell_maximum_water_flow_rate_fraction": {
                        "type": "number",
                        "minimum": 1.0,
                        "default": 2.5,
                        "note": "The allowable maximal fraction of the nominal flow rate per cell"
                    },
                    "sizing_factor": {
                        "type": "number",
                        "note": "Multiplies the autosized capacity and flow rates",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                        "retaincase": true,
                        "default": "General"
                    }
                },
                "required": [
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "design_water_flow_rate",
                    "design_air_flow_rate",
                    "design_fan_power"
                ]
            }
        },
        "group": "Condenser Equipment and Heat Exchangers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "CoolingTowers",
                "validBranchEquipmentNames",
                "validCondenserEquipmentNames",
                "validPlantEquipmentNames"
            ],
            "note": "Tower Name",
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validCondenserEquipmentTypes",
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
                "water_inlet_node_name": {
                    "field_name": "Water Inlet Node Name",
                    "field_type": "a"
                },
                "water_outlet_node_name": {
                    "field_name": "Water Outlet Node Name",
                    "field_type": "a"
                },
                "model_type": {
                    "field_name": "Model Type",
                    "field_type": "a"
                },
                "model_coefficient_name": {
                    "field_name": "Model Coefficient Name",
                    "field_type": "a"
                },
                "design_inlet_air_wet_bulb_temperature": {
                    "field_name": "Design Inlet Air Wet-Bulb Temperature",
                    "field_type": "n"
                },
                "design_approach_temperature": {
                    "field_name": "Design Approach Temperature",
                    "field_type": "n"
                },
                "design_range_temperature": {
                    "field_name": "Design Range Temperature",
                    "field_type": "n"
                },
                "design_water_flow_rate": {
                    "field_name": "Design Water Flow Rate",
                    "field_type": "n"
                },
                "design_air_flow_rate": {
                    "field_name": "Design Air Flow Rate",
                    "field_type": "n"
                },
                "design_fan_power": {
                    "field_name": "Design Fan Power",
                    "field_type": "n"
                },
                "fan_power_ratio_function_of_air_flow_rate_ratio_curve_name": {
                    "field_name": "Fan Power Ratio Function of Air Flow Rate Ratio Curve Name",
                    "field_type": "a"
                },
                "minimum_air_flow_rate_ratio": {
                    "field_name": "Minimum Air Flow Rate Ratio",
                    "field_type": "n"
                },
                "fraction_of_tower_capacity_in_free_convection_regime": {
                    "field_name": "Fraction of Tower Capacity in Free Convection Regime",
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
                "evaporation_loss_mode": {
                    "field_name": "Evaporation Loss Mode",
                    "field_type": "a"
                },
                "evaporation_loss_factor": {
                    "field_name": "Evaporation Loss Factor",
                    "field_type": "n"
                },
                "drift_loss_percent": {
                    "field_name": "Drift Loss Percent",
                    "field_type": "n"
                },
                "blowdown_calculation_mode": {
                    "field_name": "Blowdown Calculation Mode",
                    "field_type": "a"
                },
                "blowdown_concentration_ratio": {
                    "field_name": "Blowdown Concentration Ratio",
                    "field_type": "n"
                },
                "blowdown_makeup_water_usage_schedule_name": {
                    "field_name": "Blowdown Makeup Water Usage Schedule Name",
                    "field_type": "a"
                },
                "supply_water_storage_tank_name": {
                    "field_name": "Supply Water Storage Tank Name",
                    "field_type": "a"
                },
                "outdoor_air_inlet_node_name": {
                    "field_name": "Outdoor Air Inlet Node Name",
                    "field_type": "a"
                },
                "number_of_cells": {
                    "field_name": "Number of Cells",
                    "field_type": "n"
                },
                "cell_control": {
                    "field_name": "Cell Control",
                    "field_type": "a"
                },
                "cell_minimum_water_flow_rate_fraction": {
                    "field_name": "Cell Minimum  Water Flow Rate Fraction",
                    "field_type": "n"
                },
                "cell_maximum_water_flow_rate_fraction": {
                    "field_name": "Cell Maximum Water Flow Rate Fraction",
                    "field_type": "n"
                },
                "sizing_factor": {
                    "field_name": "Sizing Factor",
                    "field_type": "n"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "model_type",
                "model_coefficient_name",
                "design_inlet_air_wet_bulb_temperature",
                "design_approach_temperature",
                "design_range_temperature",
                "design_water_flow_rate",
                "design_air_flow_rate",
                "design_fan_power",
                "fan_power_ratio_function_of_air_flow_rate_ratio_curve_name",
                "minimum_air_flow_rate_ratio",
                "fraction_of_tower_capacity_in_free_convection_regime",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "basin_heater_operating_schedule_name",
                "evaporation_loss_mode",
                "evaporation_loss_factor",
                "drift_loss_percent",
                "blowdown_calculation_mode",
                "blowdown_concentration_ratio",
                "blowdown_makeup_water_usage_schedule_name",
                "supply_water_storage_tank_name",
                "outdoor_air_inlet_node_name",
                "number_of_cells",
                "cell_control",
                "cell_minimum_water_flow_rate_fraction",
                "cell_maximum_water_flow_rate_fraction",
                "sizing_factor",
                "end_use_subcategory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "model_type",
                    "model_coefficient_name",
                    "fan_power_ratio_function_of_air_flow_rate_ratio_curve_name",
                    "basin_heater_operating_schedule_name",
                    "evaporation_loss_mode",
                    "blowdown_calculation_mode",
                    "blowdown_makeup_water_usage_schedule_name",
                    "supply_water_storage_tank_name",
                    "outdoor_air_inlet_node_name",
                    "cell_control",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "design_inlet_air_wet_bulb_temperature",
                    "design_approach_temperature",
                    "design_range_temperature",
                    "design_water_flow_rate",
                    "design_air_flow_rate",
                    "design_fan_power",
                    "minimum_air_flow_rate_ratio",
                    "fraction_of_tower_capacity_in_free_convection_regime",
                    "basin_heater_capacity",
                    "basin_heater_setpoint_temperature",
                    "evaporation_loss_factor",
                    "drift_loss_percent",
                    "blowdown_concentration_ratio",
                    "number_of_cells",
                    "cell_minimum_water_flow_rate_fraction",
                    "cell_maximum_water_flow_rate_fraction",
                    "sizing_factor"
                ]
            }
        },
        "type": "object",
        "memo": "This open wet tower model is based on purely empirical algorithms derived from manufacturer's performance data or field measurements. The user can select from two existing algorithms (CoolTools or YorkCalc), or they can enter their own correlation for approach temperature by using a variable speed tower model coefficient object. For a multi-cell tower, the capacity and air/water flow rate inputs are for the entire tower.",
        "min_fields": 15.0
    }
}
```
