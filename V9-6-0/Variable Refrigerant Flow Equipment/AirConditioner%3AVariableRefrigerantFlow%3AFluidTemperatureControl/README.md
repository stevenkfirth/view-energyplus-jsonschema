```
{
    "AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "heat_pump_name": {
                        "type": "string",
                        "note": "Enter a unique name for this variable refrigerant flow heat pump"
                    },
                    "availability_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Enter the name of a schedule that defines the availability of the unit Schedule values of 0 denote the unit is off. All other values denote the unit is available If this field is left blank, the unit is available the entire simulation"
                    },
                    "zone_terminal_unit_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneTerminalUnitListNames"
                        ],
                        "note": "Enter the name of a ZoneTerminalUnitList. This list connects zone terminal units to this heat pump"
                    },
                    "refrigerant_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FluidNames"
                        ],
                        "default": "R410A"
                    },
                    "rated_evaporative_capacity": {
                        "units": "W",
                        "default": 40000.0,
                        "note": "Enter the total evaporative capacity in watts at rated conditions This is the capacity corresponding to the max compressor speed at rated conditions The actual evaporative capacity is obtained by multiplying the rated capacity with the modification factor calculated by Evaporative Capacity Multiplier Function of Temperature Curve",
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
                    "rated_compressor_power_per_unit_of_rated_evaporative_capacity": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "default": 0.35,
                        "note": "Enter the rated compressor power per Watt of rated evaporative capacity [W/W] Rated compressor power corresponds to the max compressor speed at rated conditions The actual compressor power is obtained by multiplying the rated power with the modification factor calculated by Compressor Power Multiplier Function of Temperature Curve"
                    },
                    "minimum_outdoor_air_temperature_in_cooling_mode": {
                        "type": "number",
                        "units": "C",
                        "default": -6.0,
                        "note": "Enter the minimum outdoor temperature allowed for cooling operation Cooling is disabled below this temperature"
                    },
                    "maximum_outdoor_air_temperature_in_cooling_mode": {
                        "type": "number",
                        "units": "C",
                        "default": 43.0,
                        "note": "Enter the maximum outdoor temperature allowed for cooling operation Cooling is disabled above this temperature"
                    },
                    "minimum_outdoor_air_temperature_in_heating_mode": {
                        "type": "number",
                        "units": "C",
                        "default": -20.0,
                        "note": "Enter the minimum outdoor temperature allowed for heating operation Heating is disabled below this temperature"
                    },
                    "maximum_outdoor_air_temperature_in_heating_mode": {
                        "type": "number",
                        "units": "C",
                        "default": 16.0,
                        "note": "Enter the maximum outdoor temperature allowed for heating operation Heating is disabled below this temperature"
                    },
                    "reference_outdoor_unit_superheating": {
                        "type": "number",
                        "units": "deltaC",
                        "default": 3.0
                    },
                    "reference_outdoor_unit_subcooling": {
                        "type": "number",
                        "units": "deltaC",
                        "default": 5.0
                    },
                    "refrigerant_temperature_control_algorithm_for_indoor_unit": {
                        "type": "string",
                        "enum": [
                            "",
                            "ConstantTemp",
                            "VariableTemp"
                        ],
                        "default": "VariableTemp"
                    },
                    "reference_evaporating_temperature_for_indoor_unit": {
                        "type": "number",
                        "note": "This field is used if Refrigerant Temperature Control Algorithm is ConstantTemp Evaporating temperature is the refrigerant temperature, not air temperature",
                        "units": "C",
                        "default": 6.0
                    },
                    "reference_condensing_temperature_for_indoor_unit": {
                        "type": "number",
                        "note": "This field is used if Refrigerant Temperature Control Algorithm is ConstantTemp Condensing temperature is the refrigerant temperature, not air temperature",
                        "units": "C",
                        "default": 44.0
                    },
                    "variable_evaporating_temperature_minimum_for_indoor_unit": {
                        "type": "number",
                        "note": "This field is used if Refrigerant Temperature Control Algorithm is VariableTemp Evaporating temperature is the refrigerant temperature, not air temperature",
                        "units": "C",
                        "default": 4.0
                    },
                    "variable_evaporating_temperature_maximum_for_indoor_unit": {
                        "type": "number",
                        "note": "This field is used if Refrigerant Temperature Control Algorithm is VariableTemp Evaporating temperature is the refrigerant temperature, not air temperature",
                        "units": "C",
                        "default": 13.0
                    },
                    "variable_condensing_temperature_minimum_for_indoor_unit": {
                        "type": "number",
                        "note": "This field is used if Refrigerant Temperature Control Algorithm is VariableTemp Condensing temperature is the refrigerant temperature, not air temperature",
                        "units": "C",
                        "default": 42.0
                    },
                    "variable_condensing_temperature_maximum_for_indoor_unit": {
                        "type": "number",
                        "note": "This field is used if Refrigerant Temperature Control Algorithm is VariableTemp Condensing temperature is the refrigerant temperature, not air temperature",
                        "units": "C",
                        "default": 46.0
                    },
                    "outdoor_unit_fan_power_per_unit_of_rated_evaporative_capacity": {
                        "type": "number",
                        "note": "Enter the outdoor unit fan power per Watt of rated evaporative capacity [W/W]",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "default": 0.00425
                    },
                    "outdoor_unit_fan_flow_rate_per_unit_of_rated_evaporative_capacity": {
                        "type": "number",
                        "note": "This field is only used if the previous is set to autocalculate and performance input method is NominalCapacity",
                        "units": "m3/s-W",
                        "exclusiveMinimum": 0.0,
                        "default": 7.5e-05
                    },
                    "outdoor_unit_evaporating_temperature_function_of_superheating_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "outdoor_unit_condensing_temperature_function_of_subcooling_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "diameter_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint": {
                        "type": "number",
                        "note": "used to calculate the piping loss",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.0762
                    },
                    "length_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint": {
                        "type": "number",
                        "note": "used to calculate the heat loss of the main pipe",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 30.0
                    },
                    "equivalent_length_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint": {
                        "type": "number",
                        "note": "used to calculate the refrigerant pressure drop of the main pipe",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 36.0
                    },
                    "height_difference_between_outdoor_unit_and_indoor_units": {
                        "type": "number",
                        "note": "Difference between outdoor unit height and indoor unit height Positive means outdoor unit is higher than indoor unit Negative means outdoor unit is lower than indoor unit",
                        "units": "m",
                        "default": 5.0
                    },
                    "main_pipe_insulation_thickness": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.02
                    },
                    "main_pipe_insulation_thermal_conductivity": {
                        "type": "number",
                        "units": "W/m-K",
                        "minimum": 0.0,
                        "default": 0.032
                    },
                    "crankcase_heater_power_per_compressor": {
                        "type": "number",
                        "units": "W",
                        "default": 33.0,
                        "note": "Enter the value of the resistive heater located in the compressor(s). This heater is used to warm the refrigerant and oil when the compressor is off"
                    },
                    "number_of_compressors": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 2.0,
                        "note": "Enter the total number of compressor. This input is used only for crankcase heater calculations."
                    },
                    "ratio_of_compressor_size_to_total_compressor_capacity": {
                        "type": "number",
                        "units": "W/W",
                        "default": 0.5,
                        "note": "Enter the ratio of the first stage compressor to total compressor capacity All other compressors are assumed to be equally sized. This inputs is used only for crankcase heater calculations"
                    },
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater": {
                        "type": "number",
                        "units": "C",
                        "default": 5.0,
                        "note": "Enter the maximum outdoor temperature above which the crankcase heaters are disabled"
                    },
                    "defrost_strategy": {
                        "type": "string",
                        "enum": [
                            "",
                            "Resistive",
                            "ReverseCycle"
                        ],
                        "default": "Resistive",
                        "note": "Select a defrost strategy. Reverse cycle reverses the operating mode from heating to cooling to melt frost formation on the condenser coil The resistive strategy uses a resistive heater to melt the frost."
                    },
                    "defrost_control": {
                        "type": "string",
                        "enum": [
                            "",
                            "OnDemand",
                            "Timed"
                        ],
                        "default": "Timed",
                        "note": "Choose a defrost control type Either use a fixed Timed defrost period or select OnDemand to defrost only when necessary"
                    },
                    "defrost_energy_input_ratio_modifier_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "A valid performance curve must be used if ReverseCycle defrost strategy is selected"
                    },
                    "defrost_time_period_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.058333,
                        "note": "Fraction of time in defrost mode Only applicable if timed defrost control is specified"
                    },
                    "resistive_defrost_heater_capacity": {
                        "default": 0.0,
                        "units": "W",
                        "note": "Enter the size of the resistive defrost heating element Only applicable if resistive defrost strategy is specified",
                        "ip-units": "W",
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
                    "maximum_outdoor_dry_bulb_temperature_for_defrost_operation": {
                        "type": "number",
                        "units": "C",
                        "default": 5.0,
                        "note": "Enter the maximum outdoor temperature above which the defrost operation is disabled"
                    },
                    "compressor_maximum_delta_pressure": {
                        "type": "number",
                        "units": "Pa",
                        "default": 4500000.0,
                        "minimum": 0.0,
                        "maximum": 50000000.0
                    },
                    "number_of_compressor_loading_index_entries": {
                        "type": "number",
                        "default": 2.0,
                        "minimum": 2.0,
                        "maximum": 9.0,
                        "note": "First index represents minimal capacity operation Last index represents full capacity operation"
                    },
                    "loading_indices": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "compressor_speed_at_loading_index": {
                                    "type": "number",
                                    "note": "Minimum compressor speed",
                                    "units": "rev/min",
                                    "exclusiveMinimum": 0.0
                                },
                                "loading_index_evaporative_capacity_multiplier_function_of_temperature_curve_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "BivariateFunctions"
                                    ]
                                },
                                "loading_index_compressor_power_multiplier_function_of_temperature_curve_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "BivariateFunctions"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "compressor_speed_at_loading_index",
                                "loading_index_compressor_power_multiplier_function_of_temperature_curve_name",
                                "loading_index_evaporative_capacity_multiplier_function_of_temperature_curve_name"
                            ]
                        }
                    }
                },
                "required": [
                    "heat_pump_name",
                    "zone_terminal_unit_list_name",
                    "outdoor_unit_evaporating_temperature_function_of_superheating_curve_name",
                    "outdoor_unit_condensing_temperature_function_of_subcooling_curve_name"
                ]
            }
        },
        "group": "Variable Refrigerant Flow Equipment",
        "legacy_idd": {
            "field_info": {
                "heat_pump_name": {
                    "field_name": "Heat Pump Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "zone_terminal_unit_list_name": {
                    "field_name": "Zone Terminal Unit List Name",
                    "field_type": "a"
                },
                "refrigerant_type": {
                    "field_name": "Refrigerant Type",
                    "field_type": "a"
                },
                "rated_evaporative_capacity": {
                    "field_name": "Rated Evaporative Capacity",
                    "field_type": "n"
                },
                "rated_compressor_power_per_unit_of_rated_evaporative_capacity": {
                    "field_name": "Rated Compressor Power Per Unit of Rated Evaporative Capacity",
                    "field_type": "n"
                },
                "minimum_outdoor_air_temperature_in_cooling_mode": {
                    "field_name": "Minimum Outdoor Air Temperature in Cooling Mode",
                    "field_type": "n"
                },
                "maximum_outdoor_air_temperature_in_cooling_mode": {
                    "field_name": "Maximum Outdoor Air Temperature in Cooling Mode",
                    "field_type": "n"
                },
                "minimum_outdoor_air_temperature_in_heating_mode": {
                    "field_name": "Minimum Outdoor Air Temperature in Heating Mode",
                    "field_type": "n"
                },
                "maximum_outdoor_air_temperature_in_heating_mode": {
                    "field_name": "Maximum Outdoor Air Temperature in Heating Mode",
                    "field_type": "n"
                },
                "reference_outdoor_unit_superheating": {
                    "field_name": "Reference Outdoor Unit Superheating",
                    "field_type": "n"
                },
                "reference_outdoor_unit_subcooling": {
                    "field_name": "Reference Outdoor Unit Subcooling",
                    "field_type": "n"
                },
                "refrigerant_temperature_control_algorithm_for_indoor_unit": {
                    "field_name": "Refrigerant Temperature Control Algorithm for Indoor Unit",
                    "field_type": "a"
                },
                "reference_evaporating_temperature_for_indoor_unit": {
                    "field_name": "Reference Evaporating Temperature for Indoor Unit",
                    "field_type": "n"
                },
                "reference_condensing_temperature_for_indoor_unit": {
                    "field_name": "Reference Condensing Temperature for Indoor Unit",
                    "field_type": "n"
                },
                "variable_evaporating_temperature_minimum_for_indoor_unit": {
                    "field_name": "Variable Evaporating Temperature Minimum for Indoor Unit",
                    "field_type": "n"
                },
                "variable_evaporating_temperature_maximum_for_indoor_unit": {
                    "field_name": "Variable Evaporating Temperature Maximum for Indoor Unit",
                    "field_type": "n"
                },
                "variable_condensing_temperature_minimum_for_indoor_unit": {
                    "field_name": "Variable Condensing Temperature Minimum for Indoor Unit",
                    "field_type": "n"
                },
                "variable_condensing_temperature_maximum_for_indoor_unit": {
                    "field_name": "Variable Condensing Temperature Maximum for Indoor Unit",
                    "field_type": "n"
                },
                "outdoor_unit_fan_power_per_unit_of_rated_evaporative_capacity": {
                    "field_name": "Outdoor Unit Fan Power Per Unit of Rated Evaporative Capacity",
                    "field_type": "n"
                },
                "outdoor_unit_fan_flow_rate_per_unit_of_rated_evaporative_capacity": {
                    "field_name": "Outdoor Unit Fan Flow Rate Per Unit of Rated Evaporative Capacity",
                    "field_type": "n"
                },
                "outdoor_unit_evaporating_temperature_function_of_superheating_curve_name": {
                    "field_name": "Outdoor Unit Evaporating Temperature Function of Superheating Curve Name",
                    "field_type": "a"
                },
                "outdoor_unit_condensing_temperature_function_of_subcooling_curve_name": {
                    "field_name": "Outdoor Unit Condensing Temperature Function of Subcooling Curve Name",
                    "field_type": "a"
                },
                "diameter_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint": {
                    "field_name": "Diameter of Main Pipe Connecting Outdoor Unit to the First Branch Joint",
                    "field_type": "n"
                },
                "length_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint": {
                    "field_name": "Length of Main Pipe Connecting Outdoor Unit to the First Branch Joint",
                    "field_type": "n"
                },
                "equivalent_length_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint": {
                    "field_name": "Equivalent Length of Main Pipe Connecting Outdoor Unit to the First Branch Joint",
                    "field_type": "n"
                },
                "height_difference_between_outdoor_unit_and_indoor_units": {
                    "field_name": "Height Difference Between Outdoor Unit and Indoor Units",
                    "field_type": "n"
                },
                "main_pipe_insulation_thickness": {
                    "field_name": "Main Pipe Insulation Thickness",
                    "field_type": "n"
                },
                "main_pipe_insulation_thermal_conductivity": {
                    "field_name": "Main Pipe Insulation Thermal Conductivity",
                    "field_type": "n"
                },
                "crankcase_heater_power_per_compressor": {
                    "field_name": "Crankcase Heater Power per Compressor",
                    "field_type": "n"
                },
                "number_of_compressors": {
                    "field_name": "Number of Compressors",
                    "field_type": "n"
                },
                "ratio_of_compressor_size_to_total_compressor_capacity": {
                    "field_name": "Ratio of Compressor Size to Total Compressor Capacity",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater": {
                    "field_name": "Maximum Outdoor Dry-Bulb Temperature for Crankcase Heater",
                    "field_type": "n"
                },
                "defrost_strategy": {
                    "field_name": "Defrost Strategy",
                    "field_type": "a"
                },
                "defrost_control": {
                    "field_name": "Defrost Control",
                    "field_type": "a"
                },
                "defrost_energy_input_ratio_modifier_function_of_temperature_curve_name": {
                    "field_name": "Defrost Energy Input Ratio Modifier Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "defrost_time_period_fraction": {
                    "field_name": "Defrost Time Period Fraction",
                    "field_type": "n"
                },
                "resistive_defrost_heater_capacity": {
                    "field_name": "Resistive Defrost Heater Capacity",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_defrost_operation": {
                    "field_name": "Maximum Outdoor Dry-bulb Temperature for Defrost Operation",
                    "field_type": "n"
                },
                "compressor_maximum_delta_pressure": {
                    "field_name": "Compressor maximum delta Pressure",
                    "field_type": "n"
                },
                "number_of_compressor_loading_index_entries": {
                    "field_name": "Number of Compressor Loading Index Entries",
                    "field_type": "n"
                },
                "compressor_speed_at_loading_index": {
                    "field_name": "Compressor Speed at Loading Index",
                    "field_type": "n"
                },
                "loading_index_evaporative_capacity_multiplier_function_of_temperature_curve_name": {
                    "field_name": "Loading Index Evaporative Capacity Multiplier Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "loading_index_compressor_power_multiplier_function_of_temperature_curve_name": {
                    "field_name": "Loading Index Compressor Power Multiplier Function of Temperature Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "heat_pump_name",
                "availability_schedule_name",
                "zone_terminal_unit_list_name",
                "refrigerant_type",
                "rated_evaporative_capacity",
                "rated_compressor_power_per_unit_of_rated_evaporative_capacity",
                "minimum_outdoor_air_temperature_in_cooling_mode",
                "maximum_outdoor_air_temperature_in_cooling_mode",
                "minimum_outdoor_air_temperature_in_heating_mode",
                "maximum_outdoor_air_temperature_in_heating_mode",
                "reference_outdoor_unit_superheating",
                "reference_outdoor_unit_subcooling",
                "refrigerant_temperature_control_algorithm_for_indoor_unit",
                "reference_evaporating_temperature_for_indoor_unit",
                "reference_condensing_temperature_for_indoor_unit",
                "variable_evaporating_temperature_minimum_for_indoor_unit",
                "variable_evaporating_temperature_maximum_for_indoor_unit",
                "variable_condensing_temperature_minimum_for_indoor_unit",
                "variable_condensing_temperature_maximum_for_indoor_unit",
                "outdoor_unit_fan_power_per_unit_of_rated_evaporative_capacity",
                "outdoor_unit_fan_flow_rate_per_unit_of_rated_evaporative_capacity",
                "outdoor_unit_evaporating_temperature_function_of_superheating_curve_name",
                "outdoor_unit_condensing_temperature_function_of_subcooling_curve_name",
                "diameter_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint",
                "length_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint",
                "equivalent_length_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint",
                "height_difference_between_outdoor_unit_and_indoor_units",
                "main_pipe_insulation_thickness",
                "main_pipe_insulation_thermal_conductivity",
                "crankcase_heater_power_per_compressor",
                "number_of_compressors",
                "ratio_of_compressor_size_to_total_compressor_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater",
                "defrost_strategy",
                "defrost_control",
                "defrost_energy_input_ratio_modifier_function_of_temperature_curve_name",
                "defrost_time_period_fraction",
                "resistive_defrost_heater_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_defrost_operation",
                "compressor_maximum_delta_pressure",
                "number_of_compressor_loading_index_entries"
            ],
            "alphas": {
                "fields": [
                    "heat_pump_name",
                    "availability_schedule_name",
                    "zone_terminal_unit_list_name",
                    "refrigerant_type",
                    "refrigerant_temperature_control_algorithm_for_indoor_unit",
                    "outdoor_unit_evaporating_temperature_function_of_superheating_curve_name",
                    "outdoor_unit_condensing_temperature_function_of_subcooling_curve_name",
                    "defrost_strategy",
                    "defrost_control",
                    "defrost_energy_input_ratio_modifier_function_of_temperature_curve_name"
                ],
                "extensions": [
                    "loading_index_evaporative_capacity_multiplier_function_of_temperature_curve_name",
                    "loading_index_compressor_power_multiplier_function_of_temperature_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_evaporative_capacity",
                    "rated_compressor_power_per_unit_of_rated_evaporative_capacity",
                    "minimum_outdoor_air_temperature_in_cooling_mode",
                    "maximum_outdoor_air_temperature_in_cooling_mode",
                    "minimum_outdoor_air_temperature_in_heating_mode",
                    "maximum_outdoor_air_temperature_in_heating_mode",
                    "reference_outdoor_unit_superheating",
                    "reference_outdoor_unit_subcooling",
                    "reference_evaporating_temperature_for_indoor_unit",
                    "reference_condensing_temperature_for_indoor_unit",
                    "variable_evaporating_temperature_minimum_for_indoor_unit",
                    "variable_evaporating_temperature_maximum_for_indoor_unit",
                    "variable_condensing_temperature_minimum_for_indoor_unit",
                    "variable_condensing_temperature_maximum_for_indoor_unit",
                    "outdoor_unit_fan_power_per_unit_of_rated_evaporative_capacity",
                    "outdoor_unit_fan_flow_rate_per_unit_of_rated_evaporative_capacity",
                    "diameter_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint",
                    "length_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint",
                    "equivalent_length_of_main_pipe_connecting_outdoor_unit_to_the_first_branch_joint",
                    "height_difference_between_outdoor_unit_and_indoor_units",
                    "main_pipe_insulation_thickness",
                    "main_pipe_insulation_thermal_conductivity",
                    "crankcase_heater_power_per_compressor",
                    "number_of_compressors",
                    "ratio_of_compressor_size_to_total_compressor_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater",
                    "defrost_time_period_fraction",
                    "resistive_defrost_heater_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_defrost_operation",
                    "compressor_maximum_delta_pressure",
                    "number_of_compressor_loading_index_entries"
                ],
                "extensions": [
                    "compressor_speed_at_loading_index"
                ]
            },
            "extensibles": [
                "compressor_speed_at_loading_index",
                "loading_index_evaporative_capacity_multiplier_function_of_temperature_curve_name",
                "loading_index_compressor_power_multiplier_function_of_temperature_curve_name"
            ],
            "extension": "loading_indices"
        },
        "type": "object",
        "memo": "This is a key object in the new physics based VRF model applicable for Fluid Temperature Control It describes the Variable Refrigerant Flow system excluding the performance of indoor units Indoor units are modeled separately, see ZoneHVAC:TerminalUnit:VariableRefrigerantFlow",
        "min_fields": 41.0,
        "extensible_size": 3.0
    }
}
```
