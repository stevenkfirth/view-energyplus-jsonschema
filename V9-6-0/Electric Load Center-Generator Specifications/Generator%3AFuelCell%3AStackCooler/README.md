```
{
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
                "nominal_stack_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "actual_stack_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "coefficient_r0": {
                    "type": "number"
                },
                "coefficient_r1": {
                    "type": "number"
                },
                "coefficient_r2": {
                    "type": "number"
                },
                "coefficient_r3": {
                    "type": "number"
                },
                "stack_coolant_flow_rate": {
                    "type": "number",
                    "units": "kg/s"
                },
                "stack_cooler_u_factor_times_area_value": {
                    "type": "number",
                    "units": "W/K"
                },
                "fs_cogen_adjustment_factor": {
                    "type": "number"
                },
                "stack_cogeneration_exchanger_area": {
                    "type": "number",
                    "units": "m2"
                },
                "stack_cogeneration_exchanger_nominal_flow_rate": {
                    "type": "number",
                    "units": "kg/s"
                },
                "stack_cogeneration_exchanger_nominal_heat_transfer_coefficient": {
                    "type": "number",
                    "units": "W/m2-K"
                },
                "stack_cogeneration_exchanger_nominal_heat_transfer_coefficient_exponent": {
                    "type": "number"
                },
                "stack_cooler_pump_power": {
                    "type": "number",
                    "units": "W"
                },
                "stack_cooler_pump_heat_loss_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "stack_air_cooler_fan_coefficient_f0": {
                    "type": "number"
                },
                "stack_air_cooler_fan_coefficient_f1": {
                    "type": "number"
                },
                "stack_air_cooler_fan_coefficient_f2": {
                    "type": "number"
                }
            }
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "FCStackCoolerNames",
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
            "heat_recovery_water_inlet_node_name": {
                "field_name": "Heat Recovery Water Inlet Node Name",
                "field_type": "a"
            },
            "heat_recovery_water_outlet_node_name": {
                "field_name": "Heat Recovery Water Outlet Node Name",
                "field_type": "a"
            },
            "nominal_stack_temperature": {
                "field_name": "Nominal Stack Temperature",
                "field_type": "n"
            },
            "actual_stack_temperature": {
                "field_name": "Actual Stack Temperature",
                "field_type": "n"
            },
            "coefficient_r0": {
                "field_name": "Coefficient r0",
                "field_type": "n"
            },
            "coefficient_r1": {
                "field_name": "Coefficient r1",
                "field_type": "n"
            },
            "coefficient_r2": {
                "field_name": "Coefficient r2",
                "field_type": "n"
            },
            "coefficient_r3": {
                "field_name": "Coefficient r3",
                "field_type": "n"
            },
            "stack_coolant_flow_rate": {
                "field_name": "Stack Coolant Flow Rate",
                "field_type": "n"
            },
            "stack_cooler_u_factor_times_area_value": {
                "field_name": "Stack Cooler U-Factor Times Area Value",
                "field_type": "n"
            },
            "fs_cogen_adjustment_factor": {
                "field_name": "Fs-cogen Adjustment Factor",
                "field_type": "n"
            },
            "stack_cogeneration_exchanger_area": {
                "field_name": "Stack Cogeneration Exchanger Area",
                "field_type": "n"
            },
            "stack_cogeneration_exchanger_nominal_flow_rate": {
                "field_name": "Stack Cogeneration Exchanger Nominal Flow Rate",
                "field_type": "n"
            },
            "stack_cogeneration_exchanger_nominal_heat_transfer_coefficient": {
                "field_name": "Stack Cogeneration Exchanger Nominal Heat Transfer Coefficient",
                "field_type": "n"
            },
            "stack_cogeneration_exchanger_nominal_heat_transfer_coefficient_exponent": {
                "field_name": "Stack Cogeneration Exchanger Nominal Heat Transfer Coefficient Exponent",
                "field_type": "n"
            },
            "stack_cooler_pump_power": {
                "field_name": "Stack Cooler Pump Power",
                "field_type": "n"
            },
            "stack_cooler_pump_heat_loss_fraction": {
                "field_name": "Stack Cooler Pump Heat Loss Fraction",
                "field_type": "n"
            },
            "stack_air_cooler_fan_coefficient_f0": {
                "field_name": "Stack Air Cooler Fan Coefficient f0",
                "field_type": "n"
            },
            "stack_air_cooler_fan_coefficient_f1": {
                "field_name": "Stack Air Cooler Fan Coefficient f1",
                "field_type": "n"
            },
            "stack_air_cooler_fan_coefficient_f2": {
                "field_name": "Stack Air Cooler Fan Coefficient f2",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "heat_recovery_water_inlet_node_name",
            "heat_recovery_water_outlet_node_name",
            "nominal_stack_temperature",
            "actual_stack_temperature",
            "coefficient_r0",
            "coefficient_r1",
            "coefficient_r2",
            "coefficient_r3",
            "stack_coolant_flow_rate",
            "stack_cooler_u_factor_times_area_value",
            "fs_cogen_adjustment_factor",
            "stack_cogeneration_exchanger_area",
            "stack_cogeneration_exchanger_nominal_flow_rate",
            "stack_cogeneration_exchanger_nominal_heat_transfer_coefficient",
            "stack_cogeneration_exchanger_nominal_heat_transfer_coefficient_exponent",
            "stack_cooler_pump_power",
            "stack_cooler_pump_heat_loss_fraction",
            "stack_air_cooler_fan_coefficient_f0",
            "stack_air_cooler_fan_coefficient_f1",
            "stack_air_cooler_fan_coefficient_f2"
        ],
        "alphas": {
            "fields": [
                "name",
                "heat_recovery_water_inlet_node_name",
                "heat_recovery_water_outlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "nominal_stack_temperature",
                "actual_stack_temperature",
                "coefficient_r0",
                "coefficient_r1",
                "coefficient_r2",
                "coefficient_r3",
                "stack_coolant_flow_rate",
                "stack_cooler_u_factor_times_area_value",
                "fs_cogen_adjustment_factor",
                "stack_cogeneration_exchanger_area",
                "stack_cogeneration_exchanger_nominal_flow_rate",
                "stack_cogeneration_exchanger_nominal_heat_transfer_coefficient",
                "stack_cogeneration_exchanger_nominal_heat_transfer_coefficient_exponent",
                "stack_cooler_pump_power",
                "stack_cooler_pump_heat_loss_fraction",
                "stack_air_cooler_fan_coefficient_f0",
                "stack_air_cooler_fan_coefficient_f1",
                "stack_air_cooler_fan_coefficient_f2"
            ]
        }
    },
    "type": "object",
    "memo": "This object is optional and is used to define details needed to model the stack cooler on PEMFC."
}
```
