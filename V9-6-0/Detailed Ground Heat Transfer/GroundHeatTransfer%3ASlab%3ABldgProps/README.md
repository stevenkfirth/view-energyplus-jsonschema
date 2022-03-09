```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "iyrs_number_of_years_to_iterate": {
                    "type": "number",
                    "note": "This field specifies the number of years to iterate. Either the ground heat transfer calculations come to an an annual steady periodic condition by converging to a tolerance (see ConvTol field) or it runs for this number of years. A ten year maximum is usually sufficient.",
                    "default": 10.0,
                    "minimum": 1.0
                },
                "shape_slab_shape": {
                    "type": "number",
                    "note": "Use only the value 0 here. Only a rectangular shape is implemented.",
                    "minimum": 0.0,
                    "maximum": 0.0
                },
                "hbldg_building_height": {
                    "type": "number",
                    "note": "This field supplies the building height. This is used to calculate the building shadowing on the ground. typical value= 0-20",
                    "minimum": 0.0,
                    "units": "m"
                },
                "tin1_january_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin2_february_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin3_march_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin4_april_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin5_may_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin6_june_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin7_july_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin8_august_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin9_september_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin10_october_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin11_november_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tin12_december_indoor_average_temperature_setpoint": {
                    "type": "number",
                    "note": "see memo on object for more information",
                    "default": 22.0,
                    "units": "C"
                },
                "tinamp_daily_indoor_sine_wave_variation_amplitude": {
                    "type": "number",
                    "note": "This field permits imposing a daily sinusoidal variation in the indoor setpoint temperature to simulate the effect of a setback profile. The value specified is the amplitude of the sine wave.",
                    "default": 0.0,
                    "units": "deltaC"
                },
                "convtol_convergence_tolerance": {
                    "type": "number",
                    "note": "This field specifies the convergence tolerance used to control the iteration. When the temperature change of all nodes is less than the convergence value, iteration ceases.",
                    "default": 0.1
                }
            }
        }
    },
    "group": "Detailed Ground Heat Transfer",
    "legacy_idd": {
        "field_info": {
            "iyrs_number_of_years_to_iterate": {
                "field_name": "IYRS: Number of years to iterate",
                "field_type": "n"
            },
            "shape_slab_shape": {
                "field_name": "Shape: Slab shape",
                "field_type": "n"
            },
            "hbldg_building_height": {
                "field_name": "HBLDG: Building height",
                "field_type": "n"
            },
            "tin1_january_indoor_average_temperature_setpoint": {
                "field_name": "TIN1: January Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin2_february_indoor_average_temperature_setpoint": {
                "field_name": "TIN2: February Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin3_march_indoor_average_temperature_setpoint": {
                "field_name": "TIN3: March Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin4_april_indoor_average_temperature_setpoint": {
                "field_name": "TIN4: April Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin5_may_indoor_average_temperature_setpoint": {
                "field_name": "TIN5: May Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin6_june_indoor_average_temperature_setpoint": {
                "field_name": "TIN6: June Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin7_july_indoor_average_temperature_setpoint": {
                "field_name": "TIN7: July Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin8_august_indoor_average_temperature_setpoint": {
                "field_name": "TIN8: August Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin9_september_indoor_average_temperature_setpoint": {
                "field_name": "TIN9: September Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin10_october_indoor_average_temperature_setpoint": {
                "field_name": "TIN10: October Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin11_november_indoor_average_temperature_setpoint": {
                "field_name": "TIN11: November Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tin12_december_indoor_average_temperature_setpoint": {
                "field_name": "TIN12: December Indoor Average Temperature Setpoint",
                "field_type": "n"
            },
            "tinamp_daily_indoor_sine_wave_variation_amplitude": {
                "field_name": "TINAmp: Daily Indoor sine wave variation amplitude",
                "field_type": "n"
            },
            "convtol_convergence_tolerance": {
                "field_name": "ConvTol: Convergence Tolerance",
                "field_type": "n"
            }
        },
        "fields": [
            "iyrs_number_of_years_to_iterate",
            "shape_slab_shape",
            "hbldg_building_height",
            "tin1_january_indoor_average_temperature_setpoint",
            "tin2_february_indoor_average_temperature_setpoint",
            "tin3_march_indoor_average_temperature_setpoint",
            "tin4_april_indoor_average_temperature_setpoint",
            "tin5_may_indoor_average_temperature_setpoint",
            "tin6_june_indoor_average_temperature_setpoint",
            "tin7_july_indoor_average_temperature_setpoint",
            "tin8_august_indoor_average_temperature_setpoint",
            "tin9_september_indoor_average_temperature_setpoint",
            "tin10_october_indoor_average_temperature_setpoint",
            "tin11_november_indoor_average_temperature_setpoint",
            "tin12_december_indoor_average_temperature_setpoint",
            "tinamp_daily_indoor_sine_wave_variation_amplitude",
            "convtol_convergence_tolerance"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "iyrs_number_of_years_to_iterate",
                "shape_slab_shape",
                "hbldg_building_height",
                "tin1_january_indoor_average_temperature_setpoint",
                "tin2_february_indoor_average_temperature_setpoint",
                "tin3_march_indoor_average_temperature_setpoint",
                "tin4_april_indoor_average_temperature_setpoint",
                "tin5_may_indoor_average_temperature_setpoint",
                "tin6_june_indoor_average_temperature_setpoint",
                "tin7_july_indoor_average_temperature_setpoint",
                "tin8_august_indoor_average_temperature_setpoint",
                "tin9_september_indoor_average_temperature_setpoint",
                "tin10_october_indoor_average_temperature_setpoint",
                "tin11_november_indoor_average_temperature_setpoint",
                "tin12_december_indoor_average_temperature_setpoint",
                "tinamp_daily_indoor_sine_wave_variation_amplitude",
                "convtol_convergence_tolerance"
            ]
        }
    },
    "type": "object",
    "memo": "Object provides information about the building and its operating conditions Monthly Average Temperature SetPoint fields specify the average indoor building set point temperatures for each month of the year. These fields are useful for simulating a building that is not temperature controlled for some of the year. In such a case, the average indoor set point temperatures can be obtained by first running the model in EnergyPlus with an insulated floor boundary condition, and then using the resulting monthly average zone temperatures in these fields."
}
```
