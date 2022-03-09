```
{
    "ElectricLoadCenter:Storage:Battery": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "Enter name of zone to receive electrical storage losses as heat if blank then electrical storage losses are dissipated to outdoors"
                    },
                    "radiative_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "number_of_battery_modules_in_parallel": {
                        "type": "number",
                        "minimum": 1.0,
                        "default": 1.0,
                        "note": "A module usually consists of several cells. The total number of modules in the battery bank is equal to number of modules in parallel times number of modules in series."
                    },
                    "number_of_battery_modules_in_series": {
                        "type": "number",
                        "minimum": 1.0,
                        "default": 1.0,
                        "note": "A module usually consists of several cells. The total number of modules in the battery bank is equal to number of modules in parallel times number of modules in series."
                    },
                    "maximum_module_capacity": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "Ah",
                        "note": "The capacity is for each module. A model parameter from manufacturer's data or test data."
                    },
                    "initial_fractional_state_of_charge": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0,
                        "note": "The state of charge is evaluated based on the maximum capacity defined in the next field."
                    },
                    "fraction_of_available_charge_capacity": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "note": "A model parameter usually derived from test data by curve fitting."
                    },
                    "change_rate_from_bound_charge_to_available_charge": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "1/hr",
                        "note": "A model parameter usually derived from test data by curve fitting."
                    },
                    "fully_charged_module_open_circuit_voltage": {
                        "type": "number",
                        "units": "V",
                        "minimum": 0.0,
                        "note": "The voltage is for each battery module."
                    },
                    "fully_discharged_module_open_circuit_voltage": {
                        "type": "number",
                        "units": "V",
                        "minimum": 0.0,
                        "note": "The voltage is for each battery module."
                    },
                    "voltage_change_curve_name_for_charging": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Determines how the open circuit voltage change with state of charge relative to the fully discharged state."
                    },
                    "voltage_change_curve_name_for_discharging": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Determines how the open circuit voltage change with state of charge relative to the fully charged state."
                    },
                    "module_internal_electrical_resistance": {
                        "type": "number",
                        "units": "ohms",
                        "minimum": 0.0,
                        "note": "A model parameter from manufacture or derived from test data. Internal resistance is assumed to be constant. The internal resistance is for each battery module."
                    },
                    "maximum_module_discharging_current": {
                        "type": "number",
                        "units": "A",
                        "minimum": 0.0,
                        "note": "The constraint on discharging current is for each battery module."
                    },
                    "module_cut_off_voltage": {
                        "type": "number",
                        "units": "V",
                        "minimum": 0.0,
                        "note": "The voltage constraint is for each battery module."
                    },
                    "module_charge_rate_limit": {
                        "type": "number",
                        "note": "units 1/hr Charge rate limit is the division between charging current the remaining capacity. The constraint on charging current is for each module.",
                        "minimum": 0.0,
                        "default": 1.0
                    },
                    "battery_life_calculation": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "number_of_cycle_bins": {
                        "type": "number",
                        "minimum": 5.0,
                        "default": 10.0,
                        "note": "Only required when battery life calculation is activated"
                    },
                    "battery_life_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Determines the number of cycles to failure in relation to cycle range. Only required when battery life calculation is activated."
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ElecStorageList"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "radiative_fraction": {
                    "field_name": "Radiative Fraction",
                    "field_type": "n"
                },
                "number_of_battery_modules_in_parallel": {
                    "field_name": "Number of Battery Modules in Parallel",
                    "field_type": "n"
                },
                "number_of_battery_modules_in_series": {
                    "field_name": "Number of Battery Modules in Series",
                    "field_type": "n"
                },
                "maximum_module_capacity": {
                    "field_name": "Maximum Module Capacity",
                    "field_type": "n"
                },
                "initial_fractional_state_of_charge": {
                    "field_name": "Initial Fractional State of Charge",
                    "field_type": "n"
                },
                "fraction_of_available_charge_capacity": {
                    "field_name": "Fraction of Available Charge Capacity",
                    "field_type": "n"
                },
                "change_rate_from_bound_charge_to_available_charge": {
                    "field_name": "Change Rate from Bound Charge to Available Charge",
                    "field_type": "n"
                },
                "fully_charged_module_open_circuit_voltage": {
                    "field_name": "Fully Charged Module Open Circuit Voltage",
                    "field_type": "n"
                },
                "fully_discharged_module_open_circuit_voltage": {
                    "field_name": "Fully Discharged Module Open Circuit Voltage",
                    "field_type": "n"
                },
                "voltage_change_curve_name_for_charging": {
                    "field_name": "Voltage Change Curve Name for Charging",
                    "field_type": "a"
                },
                "voltage_change_curve_name_for_discharging": {
                    "field_name": "Voltage Change Curve Name for Discharging",
                    "field_type": "a"
                },
                "module_internal_electrical_resistance": {
                    "field_name": "Module Internal Electrical Resistance",
                    "field_type": "n"
                },
                "maximum_module_discharging_current": {
                    "field_name": "Maximum Module Discharging Current",
                    "field_type": "n"
                },
                "module_cut_off_voltage": {
                    "field_name": "Module Cut-off Voltage",
                    "field_type": "n"
                },
                "module_charge_rate_limit": {
                    "field_name": "Module Charge Rate Limit",
                    "field_type": "n"
                },
                "battery_life_calculation": {
                    "field_name": "Battery Life Calculation",
                    "field_type": "a"
                },
                "number_of_cycle_bins": {
                    "field_name": "Number of Cycle Bins",
                    "field_type": "n"
                },
                "battery_life_curve_name": {
                    "field_name": "Battery Life Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "radiative_fraction",
                "number_of_battery_modules_in_parallel",
                "number_of_battery_modules_in_series",
                "maximum_module_capacity",
                "initial_fractional_state_of_charge",
                "fraction_of_available_charge_capacity",
                "change_rate_from_bound_charge_to_available_charge",
                "fully_charged_module_open_circuit_voltage",
                "fully_discharged_module_open_circuit_voltage",
                "voltage_change_curve_name_for_charging",
                "voltage_change_curve_name_for_discharging",
                "module_internal_electrical_resistance",
                "maximum_module_discharging_current",
                "module_cut_off_voltage",
                "module_charge_rate_limit",
                "battery_life_calculation",
                "number_of_cycle_bins",
                "battery_life_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "zone_name",
                    "voltage_change_curve_name_for_charging",
                    "voltage_change_curve_name_for_discharging",
                    "battery_life_calculation",
                    "battery_life_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "radiative_fraction",
                    "number_of_battery_modules_in_parallel",
                    "number_of_battery_modules_in_series",
                    "maximum_module_capacity",
                    "initial_fractional_state_of_charge",
                    "fraction_of_available_charge_capacity",
                    "change_rate_from_bound_charge_to_available_charge",
                    "fully_charged_module_open_circuit_voltage",
                    "fully_discharged_module_open_circuit_voltage",
                    "module_internal_electrical_resistance",
                    "maximum_module_discharging_current",
                    "module_cut_off_voltage",
                    "module_charge_rate_limit",
                    "number_of_cycle_bins"
                ]
            }
        },
        "type": "object",
        "memo": "Uses the kinetic battery model (KiBaM) to simulate rechargeable battery banks in an electrical load center. The battery bank is a collection of one or more individual battery modules. Given the surplus or deficit power from the electrical system and the state of charge from the previous time step, this object can model the voltage, current, and energy losses with charging and discharging during each time step. The cumulative battery damage can be also modeled and reported at the end of each simulation run."
    }
}
```
