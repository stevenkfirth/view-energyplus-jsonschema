```
{
    "PhotovoltaicPerformance:Sandia": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "active_area": {
                        "type": "number",
                        "note": "(m2, single module)",
                        "default": 1.0,
                        "units": "m2",
                        "minimum": 0.0
                    },
                    "number_of_cells_in_series": {
                        "type": "number",
                        "default": 1.0,
                        "units": "dimensionless",
                        "minimum": 1.0
                    },
                    "number_of_cells_in_parallel": {
                        "type": "number",
                        "default": 1.0,
                        "units": "dimensionless",
                        "minimum": 1.0
                    },
                    "short_circuit_current": {
                        "type": "number",
                        "note": "(Amps)",
                        "units": "A"
                    },
                    "open_circuit_voltage": {
                        "type": "number",
                        "note": "(Volts)",
                        "units": "V"
                    },
                    "current_at_maximum_power_point": {
                        "type": "number",
                        "note": "(Amps)",
                        "units": "A"
                    },
                    "voltage_at_maximum_power_point": {
                        "type": "number",
                        "note": "(Volts)",
                        "units": "V"
                    },
                    "sandia_database_parameter_aisc": {
                        "type": "number",
                        "note": "(1/degC)",
                        "units": "1/K"
                    },
                    "sandia_database_parameter_aimp": {
                        "type": "number",
                        "note": "(1/degC)",
                        "units": "1/K"
                    },
                    "sandia_database_parameter_c0": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_c1": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_bvoc0": {
                        "type": "number",
                        "note": "(Volts/degC)",
                        "units": "V/K"
                    },
                    "sandia_database_parameter_mbvoc": {
                        "type": "number",
                        "note": "(Volts/degC)",
                        "units": "V/K"
                    },
                    "sandia_database_parameter_bvmp0": {
                        "type": "number",
                        "note": "(Volts/degC)",
                        "units": "V/K"
                    },
                    "sandia_database_parameter_mbvmp": {
                        "type": "number",
                        "note": "(Volts/degC)",
                        "units": "V/K"
                    },
                    "diode_factor": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_c2": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_c3": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_a0": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_a1": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_a2": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_a3": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_a4": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_b0": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_b1": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_b2": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_b3": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_b4": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_b5": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_delta_tc_": {
                        "type": "number",
                        "note": "(deg C)",
                        "units": "deltaC"
                    },
                    "sandia_database_parameter_fd": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_a": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_b": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_c4": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_c5": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_ix0": {
                        "type": "number",
                        "note": "(Amps)"
                    },
                    "sandia_database_parameter_ixx0": {
                        "type": "number",
                        "note": "(Amps)"
                    },
                    "sandia_database_parameter_c6": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "sandia_database_parameter_c7": {
                        "type": "number",
                        "note": "(non-dimensional)",
                        "units": "dimensionless"
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
                "active_area": {
                    "field_name": "Active Area",
                    "field_type": "n"
                },
                "number_of_cells_in_series": {
                    "field_name": "Number of Cells in Series",
                    "field_type": "n"
                },
                "number_of_cells_in_parallel": {
                    "field_name": "Number of Cells in Parallel",
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
                "current_at_maximum_power_point": {
                    "field_name": "Current at Maximum Power Point",
                    "field_type": "n"
                },
                "voltage_at_maximum_power_point": {
                    "field_name": "Voltage at Maximum Power Point",
                    "field_type": "n"
                },
                "sandia_database_parameter_aisc": {
                    "field_name": "Sandia Database Parameter aIsc",
                    "field_type": "n"
                },
                "sandia_database_parameter_aimp": {
                    "field_name": "Sandia Database Parameter aImp",
                    "field_type": "n"
                },
                "sandia_database_parameter_c0": {
                    "field_name": "Sandia Database Parameter c0",
                    "field_type": "n"
                },
                "sandia_database_parameter_c1": {
                    "field_name": "Sandia Database Parameter c1",
                    "field_type": "n"
                },
                "sandia_database_parameter_bvoc0": {
                    "field_name": "Sandia Database Parameter BVoc0",
                    "field_type": "n"
                },
                "sandia_database_parameter_mbvoc": {
                    "field_name": "Sandia Database Parameter mBVoc",
                    "field_type": "n"
                },
                "sandia_database_parameter_bvmp0": {
                    "field_name": "Sandia Database Parameter BVmp0",
                    "field_type": "n"
                },
                "sandia_database_parameter_mbvmp": {
                    "field_name": "Sandia Database Parameter mBVmp",
                    "field_type": "n"
                },
                "diode_factor": {
                    "field_name": "Diode Factor",
                    "field_type": "n"
                },
                "sandia_database_parameter_c2": {
                    "field_name": "Sandia Database Parameter c2",
                    "field_type": "n"
                },
                "sandia_database_parameter_c3": {
                    "field_name": "Sandia Database Parameter c3",
                    "field_type": "n"
                },
                "sandia_database_parameter_a0": {
                    "field_name": "Sandia Database Parameter a0",
                    "field_type": "n"
                },
                "sandia_database_parameter_a1": {
                    "field_name": "Sandia Database Parameter a1",
                    "field_type": "n"
                },
                "sandia_database_parameter_a2": {
                    "field_name": "Sandia Database Parameter a2",
                    "field_type": "n"
                },
                "sandia_database_parameter_a3": {
                    "field_name": "Sandia Database Parameter a3",
                    "field_type": "n"
                },
                "sandia_database_parameter_a4": {
                    "field_name": "Sandia Database Parameter a4",
                    "field_type": "n"
                },
                "sandia_database_parameter_b0": {
                    "field_name": "Sandia Database Parameter b0",
                    "field_type": "n"
                },
                "sandia_database_parameter_b1": {
                    "field_name": "Sandia Database Parameter b1",
                    "field_type": "n"
                },
                "sandia_database_parameter_b2": {
                    "field_name": "Sandia Database Parameter b2",
                    "field_type": "n"
                },
                "sandia_database_parameter_b3": {
                    "field_name": "Sandia Database Parameter b3",
                    "field_type": "n"
                },
                "sandia_database_parameter_b4": {
                    "field_name": "Sandia Database Parameter b4",
                    "field_type": "n"
                },
                "sandia_database_parameter_b5": {
                    "field_name": "Sandia Database Parameter b5",
                    "field_type": "n"
                },
                "sandia_database_parameter_delta_tc_": {
                    "field_name": "Sandia Database Parameter Delta(Tc)",
                    "field_type": "n"
                },
                "sandia_database_parameter_fd": {
                    "field_name": "Sandia Database Parameter fd",
                    "field_type": "n"
                },
                "sandia_database_parameter_a": {
                    "field_name": "Sandia Database Parameter a",
                    "field_type": "n"
                },
                "sandia_database_parameter_b": {
                    "field_name": "Sandia Database Parameter b",
                    "field_type": "n"
                },
                "sandia_database_parameter_c4": {
                    "field_name": "Sandia Database Parameter c4",
                    "field_type": "n"
                },
                "sandia_database_parameter_c5": {
                    "field_name": "Sandia Database Parameter c5",
                    "field_type": "n"
                },
                "sandia_database_parameter_ix0": {
                    "field_name": "Sandia Database Parameter Ix0",
                    "field_type": "n"
                },
                "sandia_database_parameter_ixx0": {
                    "field_name": "Sandia Database Parameter Ixx0",
                    "field_type": "n"
                },
                "sandia_database_parameter_c6": {
                    "field_name": "Sandia Database Parameter c6",
                    "field_type": "n"
                },
                "sandia_database_parameter_c7": {
                    "field_name": "Sandia Database Parameter c7",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "active_area",
                "number_of_cells_in_series",
                "number_of_cells_in_parallel",
                "short_circuit_current",
                "open_circuit_voltage",
                "current_at_maximum_power_point",
                "voltage_at_maximum_power_point",
                "sandia_database_parameter_aisc",
                "sandia_database_parameter_aimp",
                "sandia_database_parameter_c0",
                "sandia_database_parameter_c1",
                "sandia_database_parameter_bvoc0",
                "sandia_database_parameter_mbvoc",
                "sandia_database_parameter_bvmp0",
                "sandia_database_parameter_mbvmp",
                "diode_factor",
                "sandia_database_parameter_c2",
                "sandia_database_parameter_c3",
                "sandia_database_parameter_a0",
                "sandia_database_parameter_a1",
                "sandia_database_parameter_a2",
                "sandia_database_parameter_a3",
                "sandia_database_parameter_a4",
                "sandia_database_parameter_b0",
                "sandia_database_parameter_b1",
                "sandia_database_parameter_b2",
                "sandia_database_parameter_b3",
                "sandia_database_parameter_b4",
                "sandia_database_parameter_b5",
                "sandia_database_parameter_delta_tc_",
                "sandia_database_parameter_fd",
                "sandia_database_parameter_a",
                "sandia_database_parameter_b",
                "sandia_database_parameter_c4",
                "sandia_database_parameter_c5",
                "sandia_database_parameter_ix0",
                "sandia_database_parameter_ixx0",
                "sandia_database_parameter_c6",
                "sandia_database_parameter_c7"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "active_area",
                    "number_of_cells_in_series",
                    "number_of_cells_in_parallel",
                    "short_circuit_current",
                    "open_circuit_voltage",
                    "current_at_maximum_power_point",
                    "voltage_at_maximum_power_point",
                    "sandia_database_parameter_aisc",
                    "sandia_database_parameter_aimp",
                    "sandia_database_parameter_c0",
                    "sandia_database_parameter_c1",
                    "sandia_database_parameter_bvoc0",
                    "sandia_database_parameter_mbvoc",
                    "sandia_database_parameter_bvmp0",
                    "sandia_database_parameter_mbvmp",
                    "diode_factor",
                    "sandia_database_parameter_c2",
                    "sandia_database_parameter_c3",
                    "sandia_database_parameter_a0",
                    "sandia_database_parameter_a1",
                    "sandia_database_parameter_a2",
                    "sandia_database_parameter_a3",
                    "sandia_database_parameter_a4",
                    "sandia_database_parameter_b0",
                    "sandia_database_parameter_b1",
                    "sandia_database_parameter_b2",
                    "sandia_database_parameter_b3",
                    "sandia_database_parameter_b4",
                    "sandia_database_parameter_b5",
                    "sandia_database_parameter_delta_tc_",
                    "sandia_database_parameter_fd",
                    "sandia_database_parameter_a",
                    "sandia_database_parameter_b",
                    "sandia_database_parameter_c4",
                    "sandia_database_parameter_c5",
                    "sandia_database_parameter_ix0",
                    "sandia_database_parameter_ixx0",
                    "sandia_database_parameter_c6",
                    "sandia_database_parameter_c7"
                ]
            }
        },
        "type": "object",
        "memo": "Describes performance input data needed for specific makes and models of production PV panels using the empirical coefficients assembled by Sandia National Laboratory."
    }
}
```
