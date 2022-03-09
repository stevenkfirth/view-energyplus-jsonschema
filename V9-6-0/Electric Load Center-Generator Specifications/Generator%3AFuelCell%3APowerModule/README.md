```
{
    "Generator:FuelCell:PowerModule": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "efficiency_curve_mode": {
                        "type": "string",
                        "enum": [
                            "Annex42",
                            "Normalized"
                        ]
                    },
                    "efficiency_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "nominal_efficiency": {
                        "type": "number",
                        "note": "This field is not used."
                    },
                    "nominal_electrical_power": {
                        "type": "number",
                        "note": "This field is not used",
                        "units": "W"
                    },
                    "number_of_stops_at_start_of_simulation": {
                        "type": "number",
                        "note": "this is Nstops in SOFC model specification"
                    },
                    "cycling_performance_degradation_coefficient": {
                        "type": "number",
                        "note": "this is D in SOFC model specification"
                    },
                    "number_of_run_hours_at_beginning_of_simulation": {
                        "type": "number",
                        "units": "hr"
                    },
                    "accumulated_run_time_degradation_coefficient": {
                        "type": "number",
                        "note": "this is L in SOFC model specification"
                    },
                    "run_time_degradation_initiation_time_threshold": {
                        "type": "number",
                        "units": "hr"
                    },
                    "power_up_transient_limit": {
                        "type": "number",
                        "units": "W/s",
                        "note": "Maximum rate of change in electrical output [power increasing]"
                    },
                    "power_down_transient_limit": {
                        "type": "number",
                        "units": "W/s",
                        "note": "Maximum rate of change in electrical output [power decreasing] Enter positive value for rate of change"
                    },
                    "start_up_time": {
                        "type": "number",
                        "units": "s",
                        "note": "Time from start up to normal operation"
                    },
                    "start_up_fuel": {
                        "type": "number",
                        "units": "kmol"
                    },
                    "start_up_electricity_consumption": {
                        "type": "number",
                        "units": "J"
                    },
                    "start_up_electricity_produced": {
                        "type": "number",
                        "units": "J"
                    },
                    "shut_down_time": {
                        "type": "number",
                        "units": "s"
                    },
                    "shut_down_fuel": {
                        "type": "number",
                        "units": "kmol"
                    },
                    "shut_down_electricity_consumption": {
                        "type": "number",
                        "units": "J"
                    },
                    "ancillary_electricity_constant_term": {
                        "type": "number"
                    },
                    "ancillary_electricity_linear_term": {
                        "type": "number"
                    },
                    "skin_loss_calculation_mode": {
                        "type": "string",
                        "enum": [
                            "ConstantRate",
                            "QuadraticFunctionOfFuelRate",
                            "UAForProcessGasTemperature"
                        ]
                    },
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "skin_loss_radiative_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "constant_skin_loss_rate": {
                        "type": "number",
                        "units": "W"
                    },
                    "skin_loss_u_factor_times_area_term": {
                        "type": "number",
                        "units": "W/K"
                    },
                    "skin_loss_quadratic_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "curve is function of fuel use rate"
                    },
                    "dilution_air_flow_rate": {
                        "type": "number",
                        "units": "kmol/s"
                    },
                    "stack_heat_loss_to_dilution_air": {
                        "type": "number",
                        "units": "W"
                    },
                    "dilution_inlet_air_node_name": {
                        "type": "string"
                    },
                    "dilution_outlet_air_node_name": {
                        "type": "string"
                    },
                    "minimum_operating_point": {
                        "type": "number",
                        "units": "W"
                    },
                    "maximum_operating_point": {
                        "type": "number",
                        "units": "W"
                    }
                },
                "required": [
                    "efficiency_curve_name"
                ]
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "FCPMNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "efficiency_curve_mode": {
                    "field_name": "Efficiency Curve Mode",
                    "field_type": "a"
                },
                "efficiency_curve_name": {
                    "field_name": "Efficiency Curve Name",
                    "field_type": "a"
                },
                "nominal_efficiency": {
                    "field_name": "Nominal Efficiency",
                    "field_type": "n"
                },
                "nominal_electrical_power": {
                    "field_name": "Nominal Electrical Power",
                    "field_type": "n"
                },
                "number_of_stops_at_start_of_simulation": {
                    "field_name": "Number of Stops at Start of Simulation",
                    "field_type": "n"
                },
                "cycling_performance_degradation_coefficient": {
                    "field_name": "Cycling Performance Degradation Coefficient",
                    "field_type": "n"
                },
                "number_of_run_hours_at_beginning_of_simulation": {
                    "field_name": "Number of Run Hours at Beginning of Simulation",
                    "field_type": "n"
                },
                "accumulated_run_time_degradation_coefficient": {
                    "field_name": "Accumulated Run Time Degradation Coefficient",
                    "field_type": "n"
                },
                "run_time_degradation_initiation_time_threshold": {
                    "field_name": "Run Time Degradation Initiation Time Threshold",
                    "field_type": "n"
                },
                "power_up_transient_limit": {
                    "field_name": "Power Up Transient Limit",
                    "field_type": "n"
                },
                "power_down_transient_limit": {
                    "field_name": "Power Down Transient Limit",
                    "field_type": "n"
                },
                "start_up_time": {
                    "field_name": "Start Up Time",
                    "field_type": "n"
                },
                "start_up_fuel": {
                    "field_name": "Start Up Fuel",
                    "field_type": "n"
                },
                "start_up_electricity_consumption": {
                    "field_name": "Start Up Electricity Consumption",
                    "field_type": "n"
                },
                "start_up_electricity_produced": {
                    "field_name": "Start Up Electricity Produced",
                    "field_type": "n"
                },
                "shut_down_time": {
                    "field_name": "Shut Down Time",
                    "field_type": "n"
                },
                "shut_down_fuel": {
                    "field_name": "Shut Down Fuel",
                    "field_type": "n"
                },
                "shut_down_electricity_consumption": {
                    "field_name": "Shut Down Electricity Consumption",
                    "field_type": "n"
                },
                "ancillary_electricity_constant_term": {
                    "field_name": "Ancillary Electricity Constant Term",
                    "field_type": "n"
                },
                "ancillary_electricity_linear_term": {
                    "field_name": "Ancillary Electricity Linear Term",
                    "field_type": "n"
                },
                "skin_loss_calculation_mode": {
                    "field_name": "Skin Loss Calculation Mode",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "skin_loss_radiative_fraction": {
                    "field_name": "Skin Loss Radiative Fraction",
                    "field_type": "n"
                },
                "constant_skin_loss_rate": {
                    "field_name": "Constant Skin Loss Rate",
                    "field_type": "n"
                },
                "skin_loss_u_factor_times_area_term": {
                    "field_name": "Skin Loss U-Factor Times Area Term",
                    "field_type": "n"
                },
                "skin_loss_quadratic_curve_name": {
                    "field_name": "Skin Loss Quadratic Curve Name",
                    "field_type": "a"
                },
                "dilution_air_flow_rate": {
                    "field_name": "Dilution Air Flow Rate",
                    "field_type": "n"
                },
                "stack_heat_loss_to_dilution_air": {
                    "field_name": "Stack Heat loss to Dilution Air",
                    "field_type": "n"
                },
                "dilution_inlet_air_node_name": {
                    "field_name": "Dilution Inlet Air Node Name",
                    "field_type": "a"
                },
                "dilution_outlet_air_node_name": {
                    "field_name": "Dilution Outlet Air Node Name",
                    "field_type": "a"
                },
                "minimum_operating_point": {
                    "field_name": "Minimum Operating Point",
                    "field_type": "n"
                },
                "maximum_operating_point": {
                    "field_name": "Maximum Operating Point",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "efficiency_curve_mode",
                "efficiency_curve_name",
                "nominal_efficiency",
                "nominal_electrical_power",
                "number_of_stops_at_start_of_simulation",
                "cycling_performance_degradation_coefficient",
                "number_of_run_hours_at_beginning_of_simulation",
                "accumulated_run_time_degradation_coefficient",
                "run_time_degradation_initiation_time_threshold",
                "power_up_transient_limit",
                "power_down_transient_limit",
                "start_up_time",
                "start_up_fuel",
                "start_up_electricity_consumption",
                "start_up_electricity_produced",
                "shut_down_time",
                "shut_down_fuel",
                "shut_down_electricity_consumption",
                "ancillary_electricity_constant_term",
                "ancillary_electricity_linear_term",
                "skin_loss_calculation_mode",
                "zone_name",
                "skin_loss_radiative_fraction",
                "constant_skin_loss_rate",
                "skin_loss_u_factor_times_area_term",
                "skin_loss_quadratic_curve_name",
                "dilution_air_flow_rate",
                "stack_heat_loss_to_dilution_air",
                "dilution_inlet_air_node_name",
                "dilution_outlet_air_node_name",
                "minimum_operating_point",
                "maximum_operating_point"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "efficiency_curve_mode",
                    "efficiency_curve_name",
                    "skin_loss_calculation_mode",
                    "zone_name",
                    "skin_loss_quadratic_curve_name",
                    "dilution_inlet_air_node_name",
                    "dilution_outlet_air_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "nominal_efficiency",
                    "nominal_electrical_power",
                    "number_of_stops_at_start_of_simulation",
                    "cycling_performance_degradation_coefficient",
                    "number_of_run_hours_at_beginning_of_simulation",
                    "accumulated_run_time_degradation_coefficient",
                    "run_time_degradation_initiation_time_threshold",
                    "power_up_transient_limit",
                    "power_down_transient_limit",
                    "start_up_time",
                    "start_up_fuel",
                    "start_up_electricity_consumption",
                    "start_up_electricity_produced",
                    "shut_down_time",
                    "shut_down_fuel",
                    "shut_down_electricity_consumption",
                    "ancillary_electricity_constant_term",
                    "ancillary_electricity_linear_term",
                    "skin_loss_radiative_fraction",
                    "constant_skin_loss_rate",
                    "skin_loss_u_factor_times_area_term",
                    "dilution_air_flow_rate",
                    "stack_heat_loss_to_dilution_air",
                    "minimum_operating_point",
                    "maximum_operating_point"
                ]
            }
        },
        "type": "object",
        "memo": "Describe the core power module subsystem of a fuel cell power generator. This includes the fuel cell stack, fuel reformer, and whatever ancillary devices are included inside. If the model has multiple FC generators that are of the exact same type, then only one of these objects is needed and all the Generator:FuelCell objects can reference it."
    }
}
```
