```
{
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
                "design_water_flow_rate": {
                    "units": "m3/s",
                    "note": "Leave field blank if tower performance input method is NominalCapacity",
                    "ip-units": "gal/min",
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
                    "note": "This is the fan motor electric input power",
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
                "design_u_factor_times_area_value": {
                    "units": "W/K",
                    "note": "Leave field blank if tower performance input method is NominalCapacity",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0,
                            "maximum": 2100000.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "free_convection_regime_air_flow_rate": {
                    "units": "m3/s",
                    "default": 0.0,
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
                "free_convection_regime_air_flow_rate_sizing_factor": {
                    "type": "number",
                    "default": 0.1,
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 1.0,
                    "note": "This field is only used if the previous field is set to autocalculate."
                },
                "free_convection_regime_u_factor_times_area_value": {
                    "units": "W/K",
                    "default": 0.0,
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0,
                            "maximum": 300000.0
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
                "free_convection_u_factor_times_area_value_sizing_factor": {
                    "type": "number",
                    "default": 0.1,
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 1.0,
                    "note": "This field is only used if the previous field is set to autocalculate and the Performance Input Method is UFactorTimesAreaAndDesignWaterFlowRate"
                },
                "performance_input_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "NominalCapacity",
                        "UFactorTimesAreaAndDesignWaterFlowRate"
                    ],
                    "default": "UFactorTimesAreaAndDesignWaterFlowRate",
                    "note": "User can define tower thermal performance by specifying the tower UA, the Design Air Flow Rate and the Design Water Flow Rate, or by specifying the tower nominal capacity"
                },
                "heat_rejection_capacity_and_nominal_capacity_sizing_ratio": {
                    "type": "number",
                    "default": 1.25
                },
                "nominal_capacity": {
                    "type": "number",
                    "units": "W",
                    "exclusiveMinimum": 0.0,
                    "note": "Nominal tower capacity with entering water at 35C (95F), leaving water at 29.44C (85F), entering air at 25.56C (78F) wet-bulb temperature and 35C (95F) dry-bulb temperature. Design water flow rate assumed to be 5.382E-8 m3/s per watt (3 gpm/ton). Nominal tower capacity times (1.25) gives the actual tower heat rejection at these operating conditions."
                },
                "free_convection_capacity": {
                    "units": "W",
                    "note": "Tower capacity in free convection regime with entering water at 35C (95F), leaving water at 29.44C (85F), entering air at 25.56C (78F) wet-bulb temperature and 35C (95F) dry-bulb temperature. Design water flow rate assumed to be 5.382E-8 m3/s per watt of nominal tower capacity (3 gpm/ton). Tower free convection capacity times (1.25) gives the actual tower heat rejection at these operating conditions.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "free_convection_nominal_capacity_sizing_factor": {
                    "type": "number",
                    "default": 0.1,
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 1.0,
                    "note": "This field is only used if the previous field is set to autocalculate"
                },
                "design_inlet_air_dry_bulb_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 35.0,
                    "minimum": 20.0,
                    "note": "Enter the tower's design inlet air dry-bulb temperature"
                },
                "design_inlet_air_wet_bulb_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 25.6,
                    "minimum": 20.0,
                    "note": "Enter the tower's design inlet air wet-bulb temperature"
                },
                "design_approach_temperature": {
                    "units": "deltaC",
                    "default": "Autosize",
                    "note": "Enter the approach temperature corresponding to the design inlet air wet-bulb temperature and design range temperature. Design approach temp = outlet water temperature minus inlet air wet-bulb temperature at design conditions. Autosized to 3.9 deltaC.",
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
                "design_range_temperature": {
                    "units": "deltaC",
                    "default": "Autosize",
                    "note": "Enter the range temperature corresponding to the design inlet air wet-bulb temperature and design approach temperature. Design range = inlet water temperature minus outlet water temperature at design conditions. Autosized to 5.5 deltaC.",
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
                    "note": "Rate of water evaporation from the cooling tower and lost to the outdoor air [%/K] Evaporation loss is calculated as percentage of the circulating condenser water rate Value entered here is percent-per-degree K of temperature drop in the condenser water Typical values are from 0.15 to 0.27 [%/K].",
                    "default": 0.2
                },
                "drift_loss_percent": {
                    "type": "number",
                    "default": 0.008,
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
                "capacity_control": {
                    "type": "string",
                    "enum": [
                        "",
                        "FanCycling",
                        "FluidBypass"
                    ],
                    "default": "FanCycling"
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
            "CoolingTowersWithUA",
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
            "design_u_factor_times_area_value": {
                "field_name": "Design U-Factor Times Area Value",
                "field_type": "n"
            },
            "free_convection_regime_air_flow_rate": {
                "field_name": "Free Convection Regime Air Flow Rate",
                "field_type": "n"
            },
            "free_convection_regime_air_flow_rate_sizing_factor": {
                "field_name": "Free Convection Regime Air Flow Rate Sizing Factor",
                "field_type": "n"
            },
            "free_convection_regime_u_factor_times_area_value": {
                "field_name": "Free Convection Regime U-Factor Times Area Value",
                "field_type": "n"
            },
            "free_convection_u_factor_times_area_value_sizing_factor": {
                "field_name": "Free Convection U-Factor Times Area Value Sizing Factor",
                "field_type": "n"
            },
            "performance_input_method": {
                "field_name": "Performance Input Method",
                "field_type": "a"
            },
            "heat_rejection_capacity_and_nominal_capacity_sizing_ratio": {
                "field_name": "Heat Rejection Capacity and Nominal Capacity Sizing Ratio",
                "field_type": "n"
            },
            "nominal_capacity": {
                "field_name": "Nominal Capacity",
                "field_type": "n"
            },
            "free_convection_capacity": {
                "field_name": "Free Convection Capacity",
                "field_type": "n"
            },
            "free_convection_nominal_capacity_sizing_factor": {
                "field_name": "Free Convection Nominal Capacity Sizing Factor",
                "field_type": "n"
            },
            "design_inlet_air_dry_bulb_temperature": {
                "field_name": "Design Inlet Air Dry-Bulb Temperature",
                "field_type": "n"
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
            "capacity_control": {
                "field_name": "Capacity Control",
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
            "design_water_flow_rate",
            "design_air_flow_rate",
            "design_fan_power",
            "design_u_factor_times_area_value",
            "free_convection_regime_air_flow_rate",
            "free_convection_regime_air_flow_rate_sizing_factor",
            "free_convection_regime_u_factor_times_area_value",
            "free_convection_u_factor_times_area_value_sizing_factor",
            "performance_input_method",
            "heat_rejection_capacity_and_nominal_capacity_sizing_ratio",
            "nominal_capacity",
            "free_convection_capacity",
            "free_convection_nominal_capacity_sizing_factor",
            "design_inlet_air_dry_bulb_temperature",
            "design_inlet_air_wet_bulb_temperature",
            "design_approach_temperature",
            "design_range_temperature",
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
            "capacity_control",
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
                "performance_input_method",
                "basin_heater_operating_schedule_name",
                "evaporation_loss_mode",
                "blowdown_calculation_mode",
                "blowdown_makeup_water_usage_schedule_name",
                "supply_water_storage_tank_name",
                "outdoor_air_inlet_node_name",
                "capacity_control",
                "cell_control",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "design_water_flow_rate",
                "design_air_flow_rate",
                "design_fan_power",
                "design_u_factor_times_area_value",
                "free_convection_regime_air_flow_rate",
                "free_convection_regime_air_flow_rate_sizing_factor",
                "free_convection_regime_u_factor_times_area_value",
                "free_convection_u_factor_times_area_value_sizing_factor",
                "heat_rejection_capacity_and_nominal_capacity_sizing_ratio",
                "nominal_capacity",
                "free_convection_capacity",
                "free_convection_nominal_capacity_sizing_factor",
                "design_inlet_air_dry_bulb_temperature",
                "design_inlet_air_wet_bulb_temperature",
                "design_approach_temperature",
                "design_range_temperature",
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
    "memo": "This tower model is based on Merkel's theory, which is also the basis for the tower model in ASHRAE's HVAC1 Toolkit. The open wet cooling tower is modeled as a counter flow heat exchanger with a single-speed fan drawing air through the tower (induced-draft configuration). Added fluid bypass as an additional capacity control. 8/2008. For a multi-cell tower, the capacity and air/water flow rate inputs are for the entire tower.",
    "min_fields": 16.0
}
```
