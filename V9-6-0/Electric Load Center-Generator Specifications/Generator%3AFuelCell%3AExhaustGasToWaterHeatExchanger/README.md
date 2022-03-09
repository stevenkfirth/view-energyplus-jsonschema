```
{
    "Generator:FuelCell:ExhaustGasToWaterHeatExchanger": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "heat_recovery_water_inlet_node_name": {
                        "type": "string"
                    },
                    "heat_recovery_water_outlet_node_name": {
                        "type": "string"
                    },
                    "heat_recovery_water_maximum_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min"
                    },
                    "exhaust_outlet_air_node_name": {
                        "type": "string"
                    },
                    "heat_exchanger_calculation_method": {
                        "type": "string",
                        "enum": [
                            "Condensing",
                            "EmpiricalUAeff",
                            "FixedEffectiveness",
                            "FundementalUAeff"
                        ]
                    },
                    "method_1_heat_exchanger_effectiveness": {
                        "type": "number"
                    },
                    "method_2_parameter_hxs0": {
                        "type": "number"
                    },
                    "method_2_parameter_hxs1": {
                        "type": "number"
                    },
                    "method_2_parameter_hxs2": {
                        "type": "number"
                    },
                    "method_2_parameter_hxs3": {
                        "type": "number"
                    },
                    "method_2_parameter_hxs4": {
                        "type": "number"
                    },
                    "method_3_h0gas_coefficient": {
                        "type": "number"
                    },
                    "method_3_ndotgasref_coefficient": {
                        "type": "number"
                    },
                    "method_3_n_coefficient": {
                        "type": "number"
                    },
                    "method_3_gas_area": {
                        "type": "number",
                        "units": "m2"
                    },
                    "method_3_h0_water_coefficient": {
                        "type": "number"
                    },
                    "method_3_n_dot_water_ref_coefficient": {
                        "type": "number"
                    },
                    "method_3_m_coefficient": {
                        "type": "number"
                    },
                    "method_3_water_area": {
                        "type": "number",
                        "units": "m2"
                    },
                    "method_3_f_adjustment_factor": {
                        "type": "number"
                    },
                    "method_4_hxl1_coefficient": {
                        "type": "number"
                    },
                    "method_4_hxl2_coefficient": {
                        "type": "number"
                    },
                    "method_4_condensation_threshold": {
                        "type": "number",
                        "units": "C"
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "FCExhaustHXNames",
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
                "heat_recovery_water_inlet_node_name": {
                    "field_name": "Heat Recovery Water Inlet Node Name",
                    "field_type": "a"
                },
                "heat_recovery_water_outlet_node_name": {
                    "field_name": "Heat Recovery Water Outlet Node Name",
                    "field_type": "a"
                },
                "heat_recovery_water_maximum_flow_rate": {
                    "field_name": "Heat Recovery Water Maximum Flow Rate",
                    "field_type": "n"
                },
                "exhaust_outlet_air_node_name": {
                    "field_name": "Exhaust Outlet Air Node Name",
                    "field_type": "a"
                },
                "heat_exchanger_calculation_method": {
                    "field_name": "Heat Exchanger Calculation Method",
                    "field_type": "a"
                },
                "method_1_heat_exchanger_effectiveness": {
                    "field_name": "Method 1 Heat Exchanger Effectiveness",
                    "field_type": "n"
                },
                "method_2_parameter_hxs0": {
                    "field_name": "Method 2 Parameter hxs0",
                    "field_type": "n"
                },
                "method_2_parameter_hxs1": {
                    "field_name": "Method 2 Parameter hxs1",
                    "field_type": "n"
                },
                "method_2_parameter_hxs2": {
                    "field_name": "Method 2 Parameter hxs2",
                    "field_type": "n"
                },
                "method_2_parameter_hxs3": {
                    "field_name": "Method 2 Parameter hxs3",
                    "field_type": "n"
                },
                "method_2_parameter_hxs4": {
                    "field_name": "Method 2 Parameter hxs4",
                    "field_type": "n"
                },
                "method_3_h0gas_coefficient": {
                    "field_name": "Method 3 h0Gas Coefficient",
                    "field_type": "n"
                },
                "method_3_ndotgasref_coefficient": {
                    "field_name": "Method 3 NdotGasRef Coefficient",
                    "field_type": "n"
                },
                "method_3_n_coefficient": {
                    "field_name": "Method 3 n Coefficient",
                    "field_type": "n"
                },
                "method_3_gas_area": {
                    "field_name": "Method 3 Gas Area",
                    "field_type": "n"
                },
                "method_3_h0_water_coefficient": {
                    "field_name": "Method 3 h0 Water Coefficient",
                    "field_type": "n"
                },
                "method_3_n_dot_water_ref_coefficient": {
                    "field_name": "Method 3 N dot Water ref Coefficient",
                    "field_type": "n"
                },
                "method_3_m_coefficient": {
                    "field_name": "Method 3 m Coefficient",
                    "field_type": "n"
                },
                "method_3_water_area": {
                    "field_name": "Method 3 Water Area",
                    "field_type": "n"
                },
                "method_3_f_adjustment_factor": {
                    "field_name": "Method 3 F Adjustment Factor",
                    "field_type": "n"
                },
                "method_4_hxl1_coefficient": {
                    "field_name": "Method 4 hxl1 Coefficient",
                    "field_type": "n"
                },
                "method_4_hxl2_coefficient": {
                    "field_name": "Method 4 hxl2 Coefficient",
                    "field_type": "n"
                },
                "method_4_condensation_threshold": {
                    "field_name": "Method 4 Condensation Threshold",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "heat_recovery_water_inlet_node_name",
                "heat_recovery_water_outlet_node_name",
                "heat_recovery_water_maximum_flow_rate",
                "exhaust_outlet_air_node_name",
                "heat_exchanger_calculation_method",
                "method_1_heat_exchanger_effectiveness",
                "method_2_parameter_hxs0",
                "method_2_parameter_hxs1",
                "method_2_parameter_hxs2",
                "method_2_parameter_hxs3",
                "method_2_parameter_hxs4",
                "method_3_h0gas_coefficient",
                "method_3_ndotgasref_coefficient",
                "method_3_n_coefficient",
                "method_3_gas_area",
                "method_3_h0_water_coefficient",
                "method_3_n_dot_water_ref_coefficient",
                "method_3_m_coefficient",
                "method_3_water_area",
                "method_3_f_adjustment_factor",
                "method_4_hxl1_coefficient",
                "method_4_hxl2_coefficient",
                "method_4_condensation_threshold"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "heat_recovery_water_inlet_node_name",
                    "heat_recovery_water_outlet_node_name",
                    "exhaust_outlet_air_node_name",
                    "heat_exchanger_calculation_method"
                ]
            },
            "numerics": {
                "fields": [
                    "heat_recovery_water_maximum_flow_rate",
                    "method_1_heat_exchanger_effectiveness",
                    "method_2_parameter_hxs0",
                    "method_2_parameter_hxs1",
                    "method_2_parameter_hxs2",
                    "method_2_parameter_hxs3",
                    "method_2_parameter_hxs4",
                    "method_3_h0gas_coefficient",
                    "method_3_ndotgasref_coefficient",
                    "method_3_n_coefficient",
                    "method_3_gas_area",
                    "method_3_h0_water_coefficient",
                    "method_3_n_dot_water_ref_coefficient",
                    "method_3_m_coefficient",
                    "method_3_water_area",
                    "method_3_f_adjustment_factor",
                    "method_4_hxl1_coefficient",
                    "method_4_hxl2_coefficient",
                    "method_4_condensation_threshold"
                ]
            }
        },
        "type": "object",
        "memo": "Describes the exhaust gas heat exchanger subsystem of a fuel cell power generator used to recovery thermal energy"
    }
}
```
