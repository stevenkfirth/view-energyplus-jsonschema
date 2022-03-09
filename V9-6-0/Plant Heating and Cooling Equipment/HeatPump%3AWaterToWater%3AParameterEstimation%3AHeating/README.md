```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "source_side_inlet_node_name": {
                    "type": "string"
                },
                "source_side_outlet_node_name": {
                    "type": "string"
                },
                "load_side_inlet_node_name": {
                    "type": "string"
                },
                "load_side_outlet_node_name": {
                    "type": "string"
                },
                "nominal_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "nominal_capacity": {
                    "type": "number",
                    "units": "W",
                    "exclusiveMinimum": 0.0
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
                "load_side_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "gal/min"
                },
                "source_side_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "gal/min"
                },
                "load_side_heat_transfer_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "exclusiveMinimum": 0.0
                },
                "source_side_heat_transfer_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "exclusiveMinimum": 0.0
                },
                "piston_displacement": {
                    "type": "number",
                    "units": "m3/s",
                    "exclusiveMinimum": 0.0
                },
                "compressor_clearance_factor": {
                    "type": "number",
                    "exclusiveMinimum": 0.0
                },
                "compressor_suction_and_discharge_pressure_drop": {
                    "type": "number",
                    "units": "Pa",
                    "exclusiveMinimum": 0.0
                },
                "superheating": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0
                },
                "constant_part_of_electromechanical_power_losses": {
                    "type": "number",
                    "units": "W",
                    "exclusiveMinimum": 0.0
                },
                "loss_factor": {
                    "type": "number",
                    "note": "Used to define electromechanical loss that is proportional to the theoretical power %",
                    "exclusiveMinimum": 0.0
                },
                "high_pressure_cut_off": {
                    "type": "number",
                    "units": "Pa",
                    "minimum": 0.0,
                    "default": 500000000.0
                },
                "low_pressure_cut_off": {
                    "type": "number",
                    "units": "Pa",
                    "minimum": 0.0,
                    "default": 0.0
                }
            },
            "required": [
                "source_side_inlet_node_name",
                "source_side_outlet_node_name",
                "load_side_inlet_node_name",
                "load_side_outlet_node_name"
            ]
        }
    },
    "group": "Plant Heating and Cooling Equipment",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validPlantEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
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
            "source_side_inlet_node_name": {
                "field_name": "Source Side Inlet Node Name",
                "field_type": "a"
            },
            "source_side_outlet_node_name": {
                "field_name": "Source Side Outlet Node Name",
                "field_type": "a"
            },
            "load_side_inlet_node_name": {
                "field_name": "Load Side Inlet Node Name",
                "field_type": "a"
            },
            "load_side_outlet_node_name": {
                "field_name": "Load Side Outlet Node Name",
                "field_type": "a"
            },
            "nominal_cop": {
                "field_name": "Nominal COP",
                "field_type": "n"
            },
            "nominal_capacity": {
                "field_name": "Nominal Capacity",
                "field_type": "n"
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
            "load_side_flow_rate": {
                "field_name": "Load Side Flow Rate",
                "field_type": "n"
            },
            "source_side_flow_rate": {
                "field_name": "Source Side Flow Rate",
                "field_type": "n"
            },
            "load_side_heat_transfer_coefficient": {
                "field_name": "Load Side Heat Transfer Coefficient",
                "field_type": "n"
            },
            "source_side_heat_transfer_coefficient": {
                "field_name": "Source Side Heat Transfer Coefficient",
                "field_type": "n"
            },
            "piston_displacement": {
                "field_name": "Piston Displacement",
                "field_type": "n"
            },
            "compressor_clearance_factor": {
                "field_name": "Compressor Clearance Factor",
                "field_type": "n"
            },
            "compressor_suction_and_discharge_pressure_drop": {
                "field_name": "Compressor Suction and Discharge Pressure Drop",
                "field_type": "n"
            },
            "superheating": {
                "field_name": "Superheating",
                "field_type": "n"
            },
            "constant_part_of_electromechanical_power_losses": {
                "field_name": "Constant Part of Electromechanical Power Losses",
                "field_type": "n"
            },
            "loss_factor": {
                "field_name": "Loss Factor",
                "field_type": "n"
            },
            "high_pressure_cut_off": {
                "field_name": "High Pressure Cut Off",
                "field_type": "n"
            },
            "low_pressure_cut_off": {
                "field_name": "Low Pressure Cut Off",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "source_side_inlet_node_name",
            "source_side_outlet_node_name",
            "load_side_inlet_node_name",
            "load_side_outlet_node_name",
            "nominal_cop",
            "nominal_capacity",
            "minimum_part_load_ratio",
            "maximum_part_load_ratio",
            "optimum_part_load_ratio",
            "load_side_flow_rate",
            "source_side_flow_rate",
            "load_side_heat_transfer_coefficient",
            "source_side_heat_transfer_coefficient",
            "piston_displacement",
            "compressor_clearance_factor",
            "compressor_suction_and_discharge_pressure_drop",
            "superheating",
            "constant_part_of_electromechanical_power_losses",
            "loss_factor",
            "high_pressure_cut_off",
            "low_pressure_cut_off"
        ],
        "alphas": {
            "fields": [
                "name",
                "source_side_inlet_node_name",
                "source_side_outlet_node_name",
                "load_side_inlet_node_name",
                "load_side_outlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "nominal_cop",
                "nominal_capacity",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "load_side_flow_rate",
                "source_side_flow_rate",
                "load_side_heat_transfer_coefficient",
                "source_side_heat_transfer_coefficient",
                "piston_displacement",
                "compressor_clearance_factor",
                "compressor_suction_and_discharge_pressure_drop",
                "superheating",
                "constant_part_of_electromechanical_power_losses",
                "loss_factor",
                "high_pressure_cut_off",
                "low_pressure_cut_off"
            ]
        }
    },
    "type": "object",
    "memo": "OSU parameter estimation model",
    "min_fields": 20.0
}
```
