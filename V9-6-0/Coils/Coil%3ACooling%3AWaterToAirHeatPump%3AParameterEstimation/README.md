```
{
    "Coil:Cooling:WaterToAirHeatPump:ParameterEstimation": {
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
                        "note": "Parameters 1-5 are as named below. Parameters 6-10 depend on the type of compressor and fluid. Refer to the InputOutputReference on the parameters required"
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
                    "nominal_cooling_coil_capacity": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W"
                    },
                    "nominal_time_for_condensate_removal_to_begin": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 3000.0,
                        "default": 0.0,
                        "note": "The nominal time for condensate to begin leaving the coil's condensate drain line at the coil's rated air flow rate and temperature conditions. Nominal time is equal to the ratio of the energy of the coil's maximum condensate holding capacity (J) to the coil's steady state latent capacity (W). Suggested value is 1000; zero value means latent degradation model is disabled."
                    },
                    "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0,
                        "note": "Ratio of the initial moisture evaporation rate from the cooling coil (when the compressor first turns off) and the coil's steady state latent capacity at rated air flow rate and temperature conditions. Suggested value is 1.5; zero value means latent degradation model is disabled."
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
                    "load_side_outside_surface_heat_transfer_coefficient": {
                        "type": "number",
                        "note": "Previously called Parameter 2",
                        "exclusiveMinimum": 0.0,
                        "units": "W/K"
                    },
                    "superheat_temperature_at_the_evaporator_outlet": {
                        "type": "number",
                        "note": "Previously called Parameter 3",
                        "exclusiveMinimum": 0.0,
                        "units": "C"
                    },
                    "compressor_power_losses": {
                        "type": "number",
                        "note": "Accounts for the loss of work due to mechanical and electrical losses in the compressor. Previously called Parameter 4",
                        "exclusiveMinimum": 0.0,
                        "units": "W"
                    },
                    "compressor_efficiency": {
                        "type": "number",
                        "note": "Previously called Parameter 5",
                        "exclusiveMinimum": 0.0
                    },
                    "compressor_piston_displacement": {
                        "type": "number",
                        "note": "Use when Compressor Type is Reciprocating or Rotary Leave this field blank for Compressor Type is Scroll. Previously part of Parameter 6",
                        "units": "m3/s",
                        "exclusiveMinimum": 0.0
                    },
                    "compressor_suction_discharge_pressure_drop": {
                        "type": "number",
                        "note": "Used when Compressor Type is Rotary or Reciprocating Leave this field blank for Compressor Type is Scroll. Previously part of Parameter 7",
                        "units": "Pa",
                        "exclusiveMinimum": 0.0
                    },
                    "compressor_clearance_factor": {
                        "type": "number",
                        "note": "Used when Compressor Type is Reciprocating. Leave this field blank for Compressor Type is Rotary or Scroll. Previously part of Parameter 8",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0
                    },
                    "refrigerant_volume_flow_rate": {
                        "type": "number",
                        "note": "Use when Compressor Type is Scroll Leave this field blank for Compressor Type is Rotary or Reciprocating. Previously part of Parameter 6",
                        "units": "m3/s",
                        "exclusiveMinimum": 0.0
                    },
                    "volume_ratio": {
                        "type": "number",
                        "note": "Use when Compressor Type is Scroll. Leave this field blank for Compressor Type is Rotary or Reciprocating. Previously part of Parameter 7",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0
                    },
                    "leak_rate_coefficient": {
                        "type": "number",
                        "note": "Use when Compressor Type is Scroll. Leave this field blank for Compressor Type is Rotary or Reciprocating. Previously part of Parameter 8",
                        "minimum": 0.0
                    },
                    "source_side_heat_transfer_coefficient": {
                        "type": "number",
                        "note": "Use when Source Side Fluid Name is Water Leave this field blank when Source Side Fluid Name is an antifreeze Previously part of Parameter 9",
                        "units": "W/K",
                        "minimum": 0.0
                    },
                    "source_side_heat_transfer_resistance1": {
                        "type": "number",
                        "note": "Use when Source Side Fluid Name is an antifreeze Leave this field blank for Source Side Fluid is Water Previously part of Parameter 9",
                        "minimum": 0.0,
                        "units": "dimensionless"
                    },
                    "source_side_heat_transfer_resistance2": {
                        "type": "number",
                        "note": "Use when Source Side Fluid Name is an antifreeze Leave this field blank for Source Side Fluid is Water Previously part of Parameter 10",
                        "units": "W/K",
                        "minimum": 0.0
                    }
                },
                "required": [
                    "compressor_type",
                    "design_source_side_flow_rate",
                    "nominal_cooling_coil_capacity",
                    "high_pressure_cutoff",
                    "low_pressure_cutoff",
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "load_side_total_heat_transfer_coefficient",
                    "load_side_outside_surface_heat_transfer_coefficient",
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
                "CoolingCoilsWaterToAirHP",
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
                "nominal_cooling_coil_capacity": {
                    "field_name": "Nominal Cooling Coil Capacity",
                    "field_type": "n"
                },
                "nominal_time_for_condensate_removal_to_begin": {
                    "field_name": "Nominal Time for Condensate Removal to Begin",
                    "field_type": "n"
                },
                "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                    "field_name": "Ratio of Initial Moisture Evaporation Rate and Steady State Latent Capacity",
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
                "load_side_outside_surface_heat_transfer_coefficient": {
                    "field_name": "Load Side Outside Surface Heat Transfer Coefficient",
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
                "nominal_cooling_coil_capacity",
                "nominal_time_for_condensate_removal_to_begin",
                "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                "high_pressure_cutoff",
                "low_pressure_cutoff",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "load_side_total_heat_transfer_coefficient",
                "load_side_outside_surface_heat_transfer_coefficient",
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
                    "nominal_cooling_coil_capacity",
                    "nominal_time_for_condensate_removal_to_begin",
                    "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                    "high_pressure_cutoff",
                    "low_pressure_cutoff",
                    "load_side_total_heat_transfer_coefficient",
                    "load_side_outside_surface_heat_transfer_coefficient",
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
        "memo": "Direct expansion (DX) cooling coil for water-to-air heat pump (includes electric compressor), single-speed, parameter estimation model. Optional inputs for moisture evaporation from wet coil when compressor cycles off with continuous fan operation. Parameter estimation model is a deterministic model that requires a consistent set of parameters to describe the operating conditions of the heat pump components.",
        "min_fields": 18.0
    }
}
```
