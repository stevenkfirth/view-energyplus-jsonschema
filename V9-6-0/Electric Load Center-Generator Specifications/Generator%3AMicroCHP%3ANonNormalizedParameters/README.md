```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "maximum_electric_power": {
                    "type": "number",
                    "units": "W"
                },
                "minimum_electric_power": {
                    "type": "number",
                    "units": "W"
                },
                "minimum_cooling_water_flow_rate": {
                    "type": "number",
                    "units": "kg/s"
                },
                "maximum_cooling_water_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "electrical_efficiency_curve_name": {
                    "type": "string",
                    "note": "TriQuadratic",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "thermal_efficiency_curve_name": {
                    "type": "string",
                    "note": "TriQuadratic",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "cooling_water_flow_rate_mode": {
                    "type": "string",
                    "enum": [
                        "InternalControl",
                        "PlantControl"
                    ]
                },
                "cooling_water_flow_rate_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "air_flow_rate_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "maximum_net_electrical_power_rate_of_change": {
                    "type": "number",
                    "units": "W/s"
                },
                "maximum_fuel_flow_rate_of_change": {
                    "type": "number",
                    "units": "kg/s2"
                },
                "heat_exchanger_u_factor_times_area_value": {
                    "type": "number",
                    "units": "W/K"
                },
                "skin_loss_u_factor_times_area_value": {
                    "type": "number",
                    "units": "W/K"
                },
                "skin_loss_radiative_fraction": {
                    "type": "number"
                },
                "aggregated_thermal_mass_of_energy_conversion_portion_of_generator": {
                    "type": "number",
                    "units": "W/K",
                    "exclusiveMinimum": 0.0
                },
                "aggregated_thermal_mass_of_heat_recovery_portion_of_generator": {
                    "type": "number",
                    "units": "W/K",
                    "exclusiveMinimum": 0.0
                },
                "standby_power": {
                    "type": "number",
                    "units": "W"
                },
                "warm_up_mode": {
                    "type": "string",
                    "enum": [
                        "NominalEngineTemperature",
                        "TimeDelay"
                    ],
                    "note": "Stirling engines use Nominal Engine Temperature Internal combustion engines use Time Delay"
                },
                "warm_up_fuel_flow_rate_coefficient": {
                    "type": "number"
                },
                "nominal_engine_operating_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "warm_up_power_coefficient": {
                    "type": "number"
                },
                "warm_up_fuel_flow_rate_limit_ratio": {
                    "type": "number"
                },
                "warm_up_delay_time": {
                    "type": "number",
                    "units": "s"
                },
                "cool_down_power": {
                    "type": "number",
                    "units": "W"
                },
                "cool_down_delay_time": {
                    "type": "number",
                    "units": "s"
                },
                "restart_mode": {
                    "type": "string",
                    "enum": [
                        "MandatoryCoolDown",
                        "OptionalCoolDown"
                    ]
                }
            }
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "reference": [
            "MicroCHPParametersNames"
        ]
    },
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "maximum_electric_power": {
                "field_name": "Maximum Electric Power",
                "field_type": "n"
            },
            "minimum_electric_power": {
                "field_name": "Minimum Electric Power",
                "field_type": "n"
            },
            "minimum_cooling_water_flow_rate": {
                "field_name": "Minimum Cooling Water Flow Rate",
                "field_type": "n"
            },
            "maximum_cooling_water_temperature": {
                "field_name": "Maximum Cooling Water Temperature",
                "field_type": "n"
            },
            "electrical_efficiency_curve_name": {
                "field_name": "Electrical Efficiency Curve Name",
                "field_type": "a"
            },
            "thermal_efficiency_curve_name": {
                "field_name": "Thermal Efficiency Curve Name",
                "field_type": "a"
            },
            "cooling_water_flow_rate_mode": {
                "field_name": "Cooling Water Flow Rate Mode",
                "field_type": "a"
            },
            "cooling_water_flow_rate_curve_name": {
                "field_name": "Cooling Water Flow Rate Curve Name",
                "field_type": "a"
            },
            "air_flow_rate_curve_name": {
                "field_name": "Air Flow Rate Curve Name",
                "field_type": "a"
            },
            "maximum_net_electrical_power_rate_of_change": {
                "field_name": "Maximum Net Electrical Power Rate of Change",
                "field_type": "n"
            },
            "maximum_fuel_flow_rate_of_change": {
                "field_name": "Maximum Fuel Flow Rate of Change",
                "field_type": "n"
            },
            "heat_exchanger_u_factor_times_area_value": {
                "field_name": "Heat Exchanger U-Factor Times Area Value",
                "field_type": "n"
            },
            "skin_loss_u_factor_times_area_value": {
                "field_name": "Skin Loss U-Factor Times Area Value",
                "field_type": "n"
            },
            "skin_loss_radiative_fraction": {
                "field_name": "Skin Loss Radiative Fraction",
                "field_type": "n"
            },
            "aggregated_thermal_mass_of_energy_conversion_portion_of_generator": {
                "field_name": "Aggregated Thermal Mass of Energy Conversion Portion of Generator",
                "field_type": "n"
            },
            "aggregated_thermal_mass_of_heat_recovery_portion_of_generator": {
                "field_name": "Aggregated Thermal Mass of Heat Recovery Portion of Generator",
                "field_type": "n"
            },
            "standby_power": {
                "field_name": "Standby Power",
                "field_type": "n"
            },
            "warm_up_mode": {
                "field_name": "Warm Up Mode",
                "field_type": "a"
            },
            "warm_up_fuel_flow_rate_coefficient": {
                "field_name": "Warm Up Fuel Flow Rate Coefficient",
                "field_type": "n"
            },
            "nominal_engine_operating_temperature": {
                "field_name": "Nominal Engine Operating Temperature",
                "field_type": "n"
            },
            "warm_up_power_coefficient": {
                "field_name": "Warm Up Power Coefficient",
                "field_type": "n"
            },
            "warm_up_fuel_flow_rate_limit_ratio": {
                "field_name": "Warm Up Fuel Flow Rate Limit Ratio",
                "field_type": "n"
            },
            "warm_up_delay_time": {
                "field_name": "Warm Up Delay Time",
                "field_type": "n"
            },
            "cool_down_power": {
                "field_name": "Cool Down Power",
                "field_type": "n"
            },
            "cool_down_delay_time": {
                "field_name": "Cool Down Delay Time",
                "field_type": "n"
            },
            "restart_mode": {
                "field_name": "Restart Mode",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "maximum_electric_power",
            "minimum_electric_power",
            "minimum_cooling_water_flow_rate",
            "maximum_cooling_water_temperature",
            "electrical_efficiency_curve_name",
            "thermal_efficiency_curve_name",
            "cooling_water_flow_rate_mode",
            "cooling_water_flow_rate_curve_name",
            "air_flow_rate_curve_name",
            "maximum_net_electrical_power_rate_of_change",
            "maximum_fuel_flow_rate_of_change",
            "heat_exchanger_u_factor_times_area_value",
            "skin_loss_u_factor_times_area_value",
            "skin_loss_radiative_fraction",
            "aggregated_thermal_mass_of_energy_conversion_portion_of_generator",
            "aggregated_thermal_mass_of_heat_recovery_portion_of_generator",
            "standby_power",
            "warm_up_mode",
            "warm_up_fuel_flow_rate_coefficient",
            "nominal_engine_operating_temperature",
            "warm_up_power_coefficient",
            "warm_up_fuel_flow_rate_limit_ratio",
            "warm_up_delay_time",
            "cool_down_power",
            "cool_down_delay_time",
            "restart_mode"
        ],
        "alphas": {
            "fields": [
                "name",
                "electrical_efficiency_curve_name",
                "thermal_efficiency_curve_name",
                "cooling_water_flow_rate_mode",
                "cooling_water_flow_rate_curve_name",
                "air_flow_rate_curve_name",
                "warm_up_mode",
                "restart_mode"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_electric_power",
                "minimum_electric_power",
                "minimum_cooling_water_flow_rate",
                "maximum_cooling_water_temperature",
                "maximum_net_electrical_power_rate_of_change",
                "maximum_fuel_flow_rate_of_change",
                "heat_exchanger_u_factor_times_area_value",
                "skin_loss_u_factor_times_area_value",
                "skin_loss_radiative_fraction",
                "aggregated_thermal_mass_of_energy_conversion_portion_of_generator",
                "aggregated_thermal_mass_of_heat_recovery_portion_of_generator",
                "standby_power",
                "warm_up_fuel_flow_rate_coefficient",
                "nominal_engine_operating_temperature",
                "warm_up_power_coefficient",
                "warm_up_fuel_flow_rate_limit_ratio",
                "warm_up_delay_time",
                "cool_down_power",
                "cool_down_delay_time"
            ]
        }
    },
    "type": "object",
    "memo": "This object is referenced by a Generator:MicroCHP object and provides the non-normalized parameters for the MicroCHP generator model."
}
```
