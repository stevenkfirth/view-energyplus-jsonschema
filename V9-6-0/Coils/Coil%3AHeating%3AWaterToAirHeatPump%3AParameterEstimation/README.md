```
{
    "Coil:Heating:WaterToAirHeatPump:ParameterEstimation": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "compressor_type": {
                        "type": "string",
                        "enum": [
                            "Reciprocating",
                            "Rotary",
                            "Scroll"
                        ],
                        "note": "Parameters 1-4 are as named below. Parameters 5-9 depend on the type of compressor. Refer to the InputOutputReference on the parameters required"
                    },
                    "refrigerant_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FluidNames"
                        ],
                        "default": "R22"
                    },
                    "design_source_side_flow_rate": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m3/s",
                        "ip-units": "gal/min"
                    },
                    "gross_rated_heating_capacity": {
                        "type": "number",
                        "note": "Heating capacity not accounting for the effect of supply air fan heat",
                        "exclusiveMinimum": 0.0,
                        "units": "W"
                    },
                    "high_pressure_cutoff": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "Pa"
                    },
                    "low_pressure_cutoff": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "Pa"
                    },
                    "water_inlet_node_name": {
                        "type": "string"
                    },
                    "water_outlet_node_name": {
                        "type": "string"
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "load_side_total_heat_transfer_coefficient": {
                        "type": "number",
                        "note": "Previously called Parameter 1",
                        "exclusiveMinimum": 0.0,
                        "units": "W/K"
                    },
                    "superheat_temperature_at_the_evaporator_outlet": {
                        "type": "number",
                        "note": "Previously called Parameter 2",
                        "exclusiveMinimum": 0.0,
                        "units": "C"
                    },
                    "compressor_power_losses": {
                        "type": "number",
                        "note": "Accounts for the loss of work due to mechanical and electrical losses in the compressor. Previously called Parameter 3",
                        "exclusiveMinimum": 0.0,
                        "units": "W"
                    },
                    "compressor_efficiency": {
                        "type": "number",
                        "note": "Previously called Parameter 4",
                        "exclusiveMinimum": 0.0
                    },
                    "compressor_piston_displacement": {
                        "type": "number",
                        "note": "Use when Compressor Type is Reciprocating or Rotary Leave this field blank for Compressor Type is Scroll. Previously part of Parameter 5",
                        "units": "m3/s",
                        "exclusiveMinimum": 0.0
                    },
                    "compressor_suction_discharge_pressure_drop": {
                        "type": "number",
                        "note": "Used when Compressor Type is Rotary or Reciprocating Leave this field blank for Compressor Type is Scroll. Previously part of Parameter 6",
                        "units": "Pa",
                        "exclusiveMinimum": 0.0
                    },
                    "compressor_clearance_factor": {
                        "type": "number",
                        "note": "Used when Compressor Type is Reciprocating. Leave this field blank for Compressor Type is Rotary or Scroll. Previously part of Parameter 7",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0
                    },
                    "refrigerant_volume_flow_rate": {
                        "type": "number",
                        "note": "Use when Compressor Type is Scroll Leave this field blank for Compressor Type is Rotary or Reciprocating. Previously part of Parameter 5",
                        "units": "m3/s",
                        "exclusiveMinimum": 0.0
                    },
                    "volume_ratio": {
                        "type": "number",
                        "note": "Use when Compressor Type is Scroll. Leave this field blank for Compressor Type is Rotary or Reciprocating. Previously part of Parameter 6",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0
                    },
                    "leak_rate_coefficient": {
                        "type": "number",
                        "note": "Use when Compressor Type is Scroll. Leave this field blank for Compressor Type is Rotary or Reciprocating. Previously part of Parameter 7",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "source_side_heat_transfer_coefficient": {
                        "type": "number",
                        "note": "Use when Source Side Fluid Name is Water Leave this field blank when Source Side Fluid is an antifreeze Previously part of Parameter 8",
                        "units": "W/K",
                        "minimum": 0.0
                    },
                    "source_side_heat_transfer_resistance1": {
                        "type": "number",
                        "note": "Use when Source Side Fluid Name is an antifreeze Leave this field blank for Source Side Fluid is Water Previously part of Parameter 8",
                        "minimum": 0.0,
                        "units": "dimensionless"
                    },
                    "source_side_heat_transfer_resistance2": {
                        "type": "number",
                        "note": "Use when Source Side Fluid Name is an antifreeze Leave this field blank for Source Side Fluid is Water Previously part of Parameter 9",
                        "units": "W/K",
                        "minimum": 0.0
                    }
                },
                "required": [
                    "compressor_type",
                    "design_source_side_flow_rate",
                    "gross_rated_heating_capacity",
                    "high_pressure_cutoff",
                    "low_pressure_cutoff",
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "load_side_total_heat_transfer_coefficient",
                    "superheat_temperature_at_the_evaporator_outlet",
                    "compressor_power_losses",
                    "compressor_efficiency"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "HeatingCoilsWaterToAirHP",
                "validBranchEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "compressor_type": {
                    "field_name": "Compressor Type",
                    "field_type": "a"
                },
                "refrigerant_type": {
                    "field_name": "Refrigerant Type",
                    "field_type": "a"
                },
                "design_source_side_flow_rate": {
                    "field_name": "Design Source Side Flow Rate",
                    "field_type": "n"
                },
                "gross_rated_heating_capacity": {
                    "field_name": "Gross Rated Heating Capacity",
                    "field_type": "n"
                },
                "high_pressure_cutoff": {
                    "field_name": "High Pressure Cutoff",
                    "field_type": "n"
                },
                "low_pressure_cutoff": {
                    "field_name": "Low Pressure Cutoff",
                    "field_type": "n"
                },
                "water_inlet_node_name": {
                    "field_name": "Water Inlet Node Name",
                    "field_type": "a"
                },
                "water_outlet_node_name": {
                    "field_name": "Water Outlet Node Name",
                    "field_type": "a"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "load_side_total_heat_transfer_coefficient": {
                    "field_name": "Load Side Total Heat Transfer Coefficient",
                    "field_type": "n"
                },
                "superheat_temperature_at_the_evaporator_outlet": {
                    "field_name": "Superheat Temperature at the Evaporator Outlet",
                    "field_type": "n"
                },
                "compressor_power_losses": {
                    "field_name": "Compressor Power Losses",
                    "field_type": "n"
                },
                "compressor_efficiency": {
                    "field_name": "Compressor Efficiency",
                    "field_type": "n"
                },
                "compressor_piston_displacement": {
                    "field_name": "Compressor Piston Displacement",
                    "field_type": "n"
                },
                "compressor_suction_discharge_pressure_drop": {
                    "field_name": "Compressor Suction/Discharge Pressure Drop",
                    "field_type": "n"
                },
                "compressor_clearance_factor": {
                    "field_name": "Compressor Clearance Factor",
                    "field_type": "n"
                },
                "refrigerant_volume_flow_rate": {
                    "field_name": "Refrigerant Volume Flow Rate",
                    "field_type": "n"
                },
                "volume_ratio": {
                    "field_name": "Volume Ratio",
                    "field_type": "n"
                },
                "leak_rate_coefficient": {
                    "field_name": "Leak Rate Coefficient",
                    "field_type": "n"
                },
                "source_side_heat_transfer_coefficient": {
                    "field_name": "Source Side Heat Transfer Coefficient",
                    "field_type": "n"
                },
                "source_side_heat_transfer_resistance1": {
                    "field_name": "Source Side Heat Transfer Resistance1",
                    "field_type": "n"
                },
                "source_side_heat_transfer_resistance2": {
                    "field_name": "Source Side Heat Transfer Resistance2",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "compressor_type",
                "refrigerant_type",
                "design_source_side_flow_rate",
                "gross_rated_heating_capacity",
                "high_pressure_cutoff",
                "low_pressure_cutoff",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "load_side_total_heat_transfer_coefficient",
                "superheat_temperature_at_the_evaporator_outlet",
                "compressor_power_losses",
                "compressor_efficiency",
                "compressor_piston_displacement",
                "compressor_suction_discharge_pressure_drop",
                "compressor_clearance_factor",
                "refrigerant_volume_flow_rate",
                "volume_ratio",
                "leak_rate_coefficient",
                "source_side_heat_transfer_coefficient",
                "source_side_heat_transfer_resistance1",
                "source_side_heat_transfer_resistance2"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "compressor_type",
                    "refrigerant_type",
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "design_source_side_flow_rate",
                    "gross_rated_heating_capacity",
                    "high_pressure_cutoff",
                    "low_pressure_cutoff",
                    "load_side_total_heat_transfer_coefficient",
                    "superheat_temperature_at_the_evaporator_outlet",
                    "compressor_power_losses",
                    "compressor_efficiency",
                    "compressor_piston_displacement",
                    "compressor_suction_discharge_pressure_drop",
                    "compressor_clearance_factor",
                    "refrigerant_volume_flow_rate",
                    "volume_ratio",
                    "leak_rate_coefficient",
                    "source_side_heat_transfer_coefficient",
                    "source_side_heat_transfer_resistance1",
                    "source_side_heat_transfer_resistance2"
                ]
            }
        },
        "type": "object",
        "memo": "Direct expansion (DX) heating coil for water-to-air heat pump (includes electric compressor), single-speed, parameter estimation model. Parameter estimation model is a deterministic model that requires a consistent set of parameters to describe the operating conditions of the heat pump components.",
        "min_fields": 15.0
    }
}
```
