```
{
    "ElectricLoadCenter:Storage:LiIonNMCBattery": {
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
                    "lifetime_model": {
                        "type": "string",
                        "enum": [
                            "",
                            "KandlerSmith",
                            "None"
                        ],
                        "default": "KandlerSmith"
                    },
                    "number_of_cells_in_series": {
                        "type": "number",
                        "minimum": 1.0,
                        "note": "Battery voltage is calculated by multiplying this field by the nominal cell voltage (N13, default 3.342V)"
                    },
                    "number_of_strings_in_parallel": {
                        "type": "number",
                        "minimum": 1.0,
                        "note": "Capacity (Ah) is determined by multiplying this field by the cell capacity (N14, default 3.2 Ah)"
                    },
                    "initial_fractional_state_of_charge": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.5,
                        "note": "The state of charge is evaluated based on the maximum capacity defined in the next field."
                    },
                    "dc_to_dc_charging_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.95
                    },
                    "battery_mass": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "kg"
                    },
                    "battery_surface_area": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m2"
                    },
                    "battery_specific_heat_capacity": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "J/kg-K",
                        "default": 1500.0
                    },
                    "heat_transfer_coefficient_between_battery_and_ambient": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m2-K",
                        "default": 7.5
                    },
                    "fully_charged_cell_voltage": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "V",
                        "default": 4.2,
                        "note": "Most users should not need to change this value."
                    },
                    "cell_voltage_at_end_of_exponential_zone": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "V",
                        "default": 3.53,
                        "note": "Most users should not need to change this value."
                    },
                    "cell_voltage_at_end_of_nominal_zone": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "V",
                        "default": 3.342,
                        "note": "Most users should not need to change this value."
                    },
                    "default_nominal_cell_voltage": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "V",
                        "default": 3.342,
                        "note": "Most users should not need to change this value."
                    },
                    "fully_charged_cell_capacity": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "Ah",
                        "default": 3.2,
                        "note": "Most users should not need to change this value."
                    },
                    "fraction_of_cell_capacity_removed_at_the_end_of_exponential_zone": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 1.0,
                        "default": 0.8075,
                        "note": "Most users should not need to change this value."
                    },
                    "fraction_of_cell_capacity_removed_at_the_end_of_nominal_zone": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 1.0,
                        "default": 0.976875,
                        "note": "Most users should not need to change this value."
                    },
                    "charge_rate_at_which_voltage_vs_capacity_curve_was_generated": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0,
                        "note": "Most users should not need to change this value."
                    },
                    "battery_cell_internal_electrical_resistance": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "ohms",
                        "default": 0.09,
                        "note": "for a single cell Most users should not need to change this value."
                    }
                },
                "required": [
                    "number_of_cells_in_series",
                    "number_of_strings_in_parallel",
                    "battery_mass",
                    "battery_surface_area"
                ]
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
                "lifetime_model": {
                    "field_name": "Lifetime Model",
                    "field_type": "a"
                },
                "number_of_cells_in_series": {
                    "field_name": "Number of Cells in Series",
                    "field_type": "n"
                },
                "number_of_strings_in_parallel": {
                    "field_name": "Number of Strings in Parallel",
                    "field_type": "n"
                },
                "initial_fractional_state_of_charge": {
                    "field_name": "Initial Fractional State of Charge",
                    "field_type": "n"
                },
                "dc_to_dc_charging_efficiency": {
                    "field_name": "DC to DC Charging Efficiency",
                    "field_type": "n"
                },
                "battery_mass": {
                    "field_name": "Battery Mass",
                    "field_type": "n"
                },
                "battery_surface_area": {
                    "field_name": "Battery Surface Area",
                    "field_type": "n"
                },
                "battery_specific_heat_capacity": {
                    "field_name": "Battery Specific Heat Capacity",
                    "field_type": "n"
                },
                "heat_transfer_coefficient_between_battery_and_ambient": {
                    "field_name": "Heat Transfer Coefficient Between Battery and Ambient",
                    "field_type": "n"
                },
                "fully_charged_cell_voltage": {
                    "field_name": "Fully Charged Cell Voltage",
                    "field_type": "n"
                },
                "cell_voltage_at_end_of_exponential_zone": {
                    "field_name": "Cell Voltage at End of Exponential Zone",
                    "field_type": "n"
                },
                "cell_voltage_at_end_of_nominal_zone": {
                    "field_name": "Cell Voltage at End of Nominal Zone",
                    "field_type": "n"
                },
                "default_nominal_cell_voltage": {
                    "field_name": "Default Nominal Cell Voltage",
                    "field_type": "n"
                },
                "fully_charged_cell_capacity": {
                    "field_name": "Fully Charged Cell Capacity",
                    "field_type": "n"
                },
                "fraction_of_cell_capacity_removed_at_the_end_of_exponential_zone": {
                    "field_name": "Fraction of Cell Capacity Removed at the End of Exponential Zone",
                    "field_type": "n"
                },
                "fraction_of_cell_capacity_removed_at_the_end_of_nominal_zone": {
                    "field_name": "Fraction of Cell Capacity Removed at the End of Nominal Zone",
                    "field_type": "n"
                },
                "charge_rate_at_which_voltage_vs_capacity_curve_was_generated": {
                    "field_name": "Charge Rate at Which Voltage vs Capacity Curve Was Generated",
                    "field_type": "n"
                },
                "battery_cell_internal_electrical_resistance": {
                    "field_name": "Battery Cell Internal Electrical Resistance",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "radiative_fraction",
                "lifetime_model",
                "number_of_cells_in_series",
                "number_of_strings_in_parallel",
                "initial_fractional_state_of_charge",
                "dc_to_dc_charging_efficiency",
                "battery_mass",
                "battery_surface_area",
                "battery_specific_heat_capacity",
                "heat_transfer_coefficient_between_battery_and_ambient",
                "fully_charged_cell_voltage",
                "cell_voltage_at_end_of_exponential_zone",
                "cell_voltage_at_end_of_nominal_zone",
                "default_nominal_cell_voltage",
                "fully_charged_cell_capacity",
                "fraction_of_cell_capacity_removed_at_the_end_of_exponential_zone",
                "fraction_of_cell_capacity_removed_at_the_end_of_nominal_zone",
                "charge_rate_at_which_voltage_vs_capacity_curve_was_generated",
                "battery_cell_internal_electrical_resistance"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "zone_name",
                    "lifetime_model"
                ]
            },
            "numerics": {
                "fields": [
                    "radiative_fraction",
                    "number_of_cells_in_series",
                    "number_of_strings_in_parallel",
                    "initial_fractional_state_of_charge",
                    "dc_to_dc_charging_efficiency",
                    "battery_mass",
                    "battery_surface_area",
                    "battery_specific_heat_capacity",
                    "heat_transfer_coefficient_between_battery_and_ambient",
                    "fully_charged_cell_voltage",
                    "cell_voltage_at_end_of_exponential_zone",
                    "cell_voltage_at_end_of_nominal_zone",
                    "default_nominal_cell_voltage",
                    "fully_charged_cell_capacity",
                    "fraction_of_cell_capacity_removed_at_the_end_of_exponential_zone",
                    "fraction_of_cell_capacity_removed_at_the_end_of_nominal_zone",
                    "charge_rate_at_which_voltage_vs_capacity_curve_was_generated",
                    "battery_cell_internal_electrical_resistance"
                ]
            }
        },
        "type": "object",
        "memo": "Uses Lithium Ion NMC model to simulate rechargeable battery banks in an electrical load center. The battery bank is a collection of one or more individual battery modules. Given the surplus or deficit power from the electrical system and the state of charge from the previous time step, this object can model the voltage, current, and energy losses with charging and discharging during each time step. The cumulative battery damage can be also modeled and reported at the end of each simulation run.",
        "min_fields": 11.0
    }
}
```
