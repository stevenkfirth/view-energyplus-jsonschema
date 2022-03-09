```
{
    "PhotovoltaicPerformance:EquivalentOne-Diode": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "cell_type": {
                        "type": "string",
                        "enum": [
                            "AmorphousSilicon",
                            "CrystallineSilicon"
                        ]
                    },
                    "number_of_cells_in_series": {
                        "type": "number",
                        "default": 36.0,
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "active_area": {
                        "type": "number",
                        "note": "The total power output of the array is determined by the number of modules (see above). The Active Area is only used to calculate the PV Array Efficiency output variable.",
                        "default": 0.89,
                        "units": "m2",
                        "minimum": 0.1
                    },
                    "transmittance_absorptance_product": {
                        "type": "number",
                        "default": 0.95,
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "semiconductor_bandgap": {
                        "type": "number",
                        "default": 1.12,
                        "units": "eV",
                        "minimum": 0.0
                    },
                    "shunt_resistance": {
                        "type": "number",
                        "default": 1000000.0,
                        "units": "ohms",
                        "minimum": 0.0
                    },
                    "short_circuit_current": {
                        "type": "number",
                        "default": 6.5,
                        "units": "A",
                        "minimum": 0.0
                    },
                    "open_circuit_voltage": {
                        "type": "number",
                        "default": 21.6,
                        "units": "V",
                        "minimum": 0.0
                    },
                    "reference_temperature": {
                        "type": "number",
                        "default": 25.0,
                        "units": "C",
                        "minimum": 0.0
                    },
                    "reference_insolation": {
                        "type": "number",
                        "default": 1000.0,
                        "units": "W/m2",
                        "minimum": 0.0
                    },
                    "module_current_at_maximum_power": {
                        "type": "number",
                        "note": "Single module current at the maximum power point and reference conditions. Module Current, Module Voltage, Number of Modules in Parallel and Number of Modules in Series determine the maximum power output of the array.",
                        "default": 5.9,
                        "units": "A",
                        "minimum": 0.0
                    },
                    "module_voltage_at_maximum_power": {
                        "type": "number",
                        "note": "Single module voltage at the maximum power point and reference conditions. Module Current, Module Voltage, Number of Modules in Parallel and Number of Modules in Series determine the maximum power output of the array.",
                        "default": 17.0,
                        "units": "V",
                        "minimum": 0.0
                    },
                    "temperature_coefficient_of_short_circuit_current": {
                        "type": "number",
                        "default": 0.02,
                        "units": "A/K"
                    },
                    "temperature_coefficient_of_open_circuit_voltage": {
                        "type": "number",
                        "default": -0.079,
                        "units": "V/K"
                    },
                    "nominal_operating_cell_temperature_test_ambient_temperature": {
                        "type": "number",
                        "default": 20.0,
                        "units": "C",
                        "minimum": 0.0
                    },
                    "nominal_operating_cell_temperature_test_cell_temperature": {
                        "type": "number",
                        "default": 40.0,
                        "units": "C",
                        "minimum": 0.0
                    },
                    "nominal_operating_cell_temperature_test_insolation": {
                        "type": "number",
                        "default": 800.0,
                        "units": "W/m2",
                        "minimum": 0.0
                    },
                    "module_heat_loss_coefficient": {
                        "type": "number",
                        "default": 30.0,
                        "units": "W/m2-K",
                        "minimum": 0.0
                    },
                    "total_heat_capacity": {
                        "type": "number",
                        "default": 50000.0,
                        "units": "J/m2-K",
                        "minimum": 0.0
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "reference": [
                "PVModules"
            ]
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "cell_type": {
                    "field_name": "Cell type",
                    "field_type": "a"
                },
                "number_of_cells_in_series": {
                    "field_name": "Number of Cells in Series",
                    "field_type": "n"
                },
                "active_area": {
                    "field_name": "Active Area",
                    "field_type": "n"
                },
                "transmittance_absorptance_product": {
                    "field_name": "Transmittance Absorptance Product",
                    "field_type": "n"
                },
                "semiconductor_bandgap": {
                    "field_name": "Semiconductor Bandgap",
                    "field_type": "n"
                },
                "shunt_resistance": {
                    "field_name": "Shunt Resistance",
                    "field_type": "n"
                },
                "short_circuit_current": {
                    "field_name": "Short Circuit Current",
                    "field_type": "n"
                },
                "open_circuit_voltage": {
                    "field_name": "Open Circuit Voltage",
                    "field_type": "n"
                },
                "reference_temperature": {
                    "field_name": "Reference Temperature",
                    "field_type": "n"
                },
                "reference_insolation": {
                    "field_name": "Reference Insolation",
                    "field_type": "n"
                },
                "module_current_at_maximum_power": {
                    "field_name": "Module Current at Maximum Power",
                    "field_type": "n"
                },
                "module_voltage_at_maximum_power": {
                    "field_name": "Module Voltage at Maximum Power",
                    "field_type": "n"
                },
                "temperature_coefficient_of_short_circuit_current": {
                    "field_name": "Temperature Coefficient of Short Circuit Current",
                    "field_type": "n"
                },
                "temperature_coefficient_of_open_circuit_voltage": {
                    "field_name": "Temperature Coefficient of Open Circuit Voltage",
                    "field_type": "n"
                },
                "nominal_operating_cell_temperature_test_ambient_temperature": {
                    "field_name": "Nominal Operating Cell Temperature Test Ambient Temperature",
                    "field_type": "n"
                },
                "nominal_operating_cell_temperature_test_cell_temperature": {
                    "field_name": "Nominal Operating Cell Temperature Test Cell Temperature",
                    "field_type": "n"
                },
                "nominal_operating_cell_temperature_test_insolation": {
                    "field_name": "Nominal Operating Cell Temperature Test Insolation",
                    "field_type": "n"
                },
                "module_heat_loss_coefficient": {
                    "field_name": "Module Heat Loss Coefficient",
                    "field_type": "n"
                },
                "total_heat_capacity": {
                    "field_name": "Total Heat Capacity",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "cell_type",
                "number_of_cells_in_series",
                "active_area",
                "transmittance_absorptance_product",
                "semiconductor_bandgap",
                "shunt_resistance",
                "short_circuit_current",
                "open_circuit_voltage",
                "reference_temperature",
                "reference_insolation",
                "module_current_at_maximum_power",
                "module_voltage_at_maximum_power",
                "temperature_coefficient_of_short_circuit_current",
                "temperature_coefficient_of_open_circuit_voltage",
                "nominal_operating_cell_temperature_test_ambient_temperature",
                "nominal_operating_cell_temperature_test_cell_temperature",
                "nominal_operating_cell_temperature_test_insolation",
                "module_heat_loss_coefficient",
                "total_heat_capacity"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "cell_type"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_cells_in_series",
                    "active_area",
                    "transmittance_absorptance_product",
                    "semiconductor_bandgap",
                    "shunt_resistance",
                    "short_circuit_current",
                    "open_circuit_voltage",
                    "reference_temperature",
                    "reference_insolation",
                    "module_current_at_maximum_power",
                    "module_voltage_at_maximum_power",
                    "temperature_coefficient_of_short_circuit_current",
                    "temperature_coefficient_of_open_circuit_voltage",
                    "nominal_operating_cell_temperature_test_ambient_temperature",
                    "nominal_operating_cell_temperature_test_cell_temperature",
                    "nominal_operating_cell_temperature_test_insolation",
                    "module_heat_loss_coefficient",
                    "total_heat_capacity"
                ]
            }
        },
        "type": "object",
        "memo": "Describes the performance characteristics of Photovoltaic (PV) modules to be modeled using an equivalent one-diode circuit. This model is also known as the 4- or 5-parameter TRNSYS model for photovoltaics."
    }
}
```
