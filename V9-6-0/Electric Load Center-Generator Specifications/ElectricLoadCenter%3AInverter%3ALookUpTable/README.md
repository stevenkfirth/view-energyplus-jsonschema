```
{
    "ElectricLoadCenter:Inverter:LookUpTable": {
        "patternProperties": {
            ".*": {
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
                        "note": "Enter name of zone to receive inverter losses as heat if blank then inverter is assumed to be outdoors",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "radiative_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "rated_maximum_continuous_output_power": {
                        "type": "number",
                        "units": "W"
                    },
                    "night_tare_loss_power": {
                        "type": "number",
                        "units": "W"
                    },
                    "nominal_voltage_input": {
                        "type": "number",
                        "units": "V"
                    },
                    "efficiency_at_10_power_and_nominal_voltage": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "efficiency_at_20_power_and_nominal_voltage": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "efficiency_at_30_power_and_nominal_voltage": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "efficiency_at_50_power_and_nominal_voltage": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "efficiency_at_75_power_and_nominal_voltage": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "efficiency_at_100_power_and_nominal_voltage": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "reference": [
                "InverterList"
            ]
        },
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
                "rated_maximum_continuous_output_power": {
                    "field_name": "Rated Maximum Continuous Output Power",
                    "field_type": "n"
                },
                "night_tare_loss_power": {
                    "field_name": "Night Tare Loss Power",
                    "field_type": "n"
                },
                "nominal_voltage_input": {
                    "field_name": "Nominal Voltage Input",
                    "field_type": "n"
                },
                "efficiency_at_10_power_and_nominal_voltage": {
                    "field_name": "Efficiency at 10% Power and Nominal Voltage",
                    "field_type": "n"
                },
                "efficiency_at_20_power_and_nominal_voltage": {
                    "field_name": "Efficiency at 20% Power and Nominal Voltage",
                    "field_type": "n"
                },
                "efficiency_at_30_power_and_nominal_voltage": {
                    "field_name": "Efficiency at 30% Power and Nominal Voltage",
                    "field_type": "n"
                },
                "efficiency_at_50_power_and_nominal_voltage": {
                    "field_name": "Efficiency at 50% Power and Nominal Voltage",
                    "field_type": "n"
                },
                "efficiency_at_75_power_and_nominal_voltage": {
                    "field_name": "Efficiency at 75% Power and Nominal Voltage",
                    "field_type": "n"
                },
                "efficiency_at_100_power_and_nominal_voltage": {
                    "field_name": "Efficiency at 100% Power and Nominal Voltage",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "radiative_fraction",
                "rated_maximum_continuous_output_power",
                "night_tare_loss_power",
                "nominal_voltage_input",
                "efficiency_at_10_power_and_nominal_voltage",
                "efficiency_at_20_power_and_nominal_voltage",
                "efficiency_at_30_power_and_nominal_voltage",
                "efficiency_at_50_power_and_nominal_voltage",
                "efficiency_at_75_power_and_nominal_voltage",
                "efficiency_at_100_power_and_nominal_voltage"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "zone_name"
                ]
            },
            "numerics": {
                "fields": [
                    "radiative_fraction",
                    "rated_maximum_continuous_output_power",
                    "night_tare_loss_power",
                    "nominal_voltage_input",
                    "efficiency_at_10_power_and_nominal_voltage",
                    "efficiency_at_20_power_and_nominal_voltage",
                    "efficiency_at_30_power_and_nominal_voltage",
                    "efficiency_at_50_power_and_nominal_voltage",
                    "efficiency_at_75_power_and_nominal_voltage",
                    "efficiency_at_100_power_and_nominal_voltage"
                ]
            }
        },
        "type": "object",
        "memo": "California Energy Commission tests and publishes data on inverters This inverter model interpolates using CEC test data Input data are at http://www.gosolarcalifornia.org/equipment/inverter_tests/summaries"
    }
}
```
