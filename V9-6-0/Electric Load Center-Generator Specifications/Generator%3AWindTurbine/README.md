```
{
    "Generator:WindTurbine": {
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
                    "rotor_type": {
                        "type": "string",
                        "note": "allowed values are: Horizontal Axis Wind Turbine or Vertical Axis Wind Turbine",
                        "enum": [
                            "",
                            "HorizontalAxisWindTurbine",
                            "VerticalAxisWindTurbine"
                        ],
                        "default": "HorizontalAxisWindTurbine"
                    },
                    "power_control": {
                        "type": "string",
                        "note": "Constant power output is obtained in the last three control types when the wind speed exceeds the rated wind speed. allowed values are: Fixed Speed Fixed Pitch, Fixed Speed Variable Pitch, Variable Speed Fixed Pitch or Variable Speed Variable Pitch",
                        "enum": [
                            "",
                            "FixedSpeedFixedPitch",
                            "FixedSpeedVariablePitch",
                            "VariableSpeedFixedPitch",
                            "VariableSpeedVariablePitch"
                        ],
                        "default": "VariableSpeedVariablePitch"
                    },
                    "rated_rotor_speed": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "rev/min"
                    },
                    "rotor_diameter": {
                        "type": "number",
                        "note": "This field is the diameter of the perpendicular circle of the Vertical Axis Wind Turbine system from the upright pole on the ground.",
                        "exclusiveMinimum": 0.0,
                        "units": "m"
                    },
                    "overall_height": {
                        "type": "number",
                        "note": "This field is the height of the hub for the Horizontal Axis Wind Turbines and of the pole for the Vertical Axis Wind Turbines.",
                        "exclusiveMinimum": 0.0,
                        "units": "m"
                    },
                    "number_of_blades": {
                        "type": "number",
                        "minimum": 2.0,
                        "default": 3.0
                    },
                    "rated_power": {
                        "type": "number",
                        "note": "This field is the nominal power at the rated wind speed. Users should input maximum power in case of Fixed Speed Fixed Pitch control type.",
                        "exclusiveMinimum": 0.0,
                        "units": "W"
                    },
                    "rated_wind_speed": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m/s"
                    },
                    "cut_in_wind_speed": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m/s"
                    },
                    "cut_out_wind_speed": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "m/s"
                    },
                    "fraction_system_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.835
                    },
                    "maximum_tip_speed_ratio": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 12.0,
                        "default": 5.0
                    },
                    "maximum_power_coefficient": {
                        "type": "number",
                        "note": "This field should be input if the rotor type is Horizontal Axis Wind Turbine",
                        "exclusiveMinimum": 0.0,
                        "maximum": 0.59,
                        "default": 0.25
                    },
                    "annual_local_average_wind_speed": {
                        "type": "number",
                        "units": "m/s",
                        "exclusiveMinimum": 0.0
                    },
                    "height_for_local_average_wind_speed": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 50.0
                    },
                    "blade_chord_area": {
                        "type": "number",
                        "units": "m2"
                    },
                    "blade_drag_coefficient": {
                        "type": "number",
                        "note": "This field is only for Vertical Axis Wind Turbine.. The user must input this field if the rotor type is Vertical Axis Wind Turbine.",
                        "default": 0.9
                    },
                    "blade_lift_coefficient": {
                        "type": "number",
                        "note": "This field is only for Vertical Axis Wind Turbine.. The user must input this field if the rotor type is Vertical Axis Wind Turbine.",
                        "default": 0.05
                    },
                    "power_coefficient_c1": {
                        "type": "number",
                        "note": "This field is only available for Horizontal Axis Wind Turbine. The user should input all six parameters so that the analytic approximation is assumed. The simple approximation will be assumed, if any field C1 through C6 is not input. Leave this field blank, if the manufacturer's data is unavailable so that the simple approximation will be assumed.",
                        "exclusiveMinimum": 0.0,
                        "default": 0.5176
                    },
                    "power_coefficient_c2": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 116.0
                    },
                    "power_coefficient_c3": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.4
                    },
                    "power_coefficient_c4": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "power_coefficient_c5": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 5.0
                    },
                    "power_coefficient_c6": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 21.0
                    }
                },
                "required": [
                    "rated_rotor_speed",
                    "rotor_diameter",
                    "overall_height",
                    "rated_power",
                    "rated_wind_speed",
                    "cut_in_wind_speed",
                    "cut_out_wind_speed"
                ]
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "GeneratorNames"
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
                "rotor_type": {
                    "field_name": "Rotor Type",
                    "field_type": "a"
                },
                "power_control": {
                    "field_name": "Power Control",
                    "field_type": "a"
                },
                "rated_rotor_speed": {
                    "field_name": "Rated Rotor Speed",
                    "field_type": "n"
                },
                "rotor_diameter": {
                    "field_name": "Rotor Diameter",
                    "field_type": "n"
                },
                "overall_height": {
                    "field_name": "Overall Height",
                    "field_type": "n"
                },
                "number_of_blades": {
                    "field_name": "Number of Blades",
                    "field_type": "n"
                },
                "rated_power": {
                    "field_name": "Rated Power",
                    "field_type": "n"
                },
                "rated_wind_speed": {
                    "field_name": "Rated Wind Speed",
                    "field_type": "n"
                },
                "cut_in_wind_speed": {
                    "field_name": "Cut In Wind Speed",
                    "field_type": "n"
                },
                "cut_out_wind_speed": {
                    "field_name": "Cut Out Wind Speed",
                    "field_type": "n"
                },
                "fraction_system_efficiency": {
                    "field_name": "Fraction system Efficiency",
                    "field_type": "n"
                },
                "maximum_tip_speed_ratio": {
                    "field_name": "Maximum Tip Speed Ratio",
                    "field_type": "n"
                },
                "maximum_power_coefficient": {
                    "field_name": "Maximum Power Coefficient",
                    "field_type": "n"
                },
                "annual_local_average_wind_speed": {
                    "field_name": "Annual Local Average Wind Speed",
                    "field_type": "n"
                },
                "height_for_local_average_wind_speed": {
                    "field_name": "Height for Local Average Wind Speed",
                    "field_type": "n"
                },
                "blade_chord_area": {
                    "field_name": "Blade Chord Area",
                    "field_type": "n"
                },
                "blade_drag_coefficient": {
                    "field_name": "Blade Drag Coefficient",
                    "field_type": "n"
                },
                "blade_lift_coefficient": {
                    "field_name": "Blade Lift Coefficient",
                    "field_type": "n"
                },
                "power_coefficient_c1": {
                    "field_name": "Power Coefficient C1",
                    "field_type": "n"
                },
                "power_coefficient_c2": {
                    "field_name": "Power Coefficient C2",
                    "field_type": "n"
                },
                "power_coefficient_c3": {
                    "field_name": "Power Coefficient C3",
                    "field_type": "n"
                },
                "power_coefficient_c4": {
                    "field_name": "Power Coefficient C4",
                    "field_type": "n"
                },
                "power_coefficient_c5": {
                    "field_name": "Power Coefficient C5",
                    "field_type": "n"
                },
                "power_coefficient_c6": {
                    "field_name": "Power Coefficient C6",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "rotor_type",
                "power_control",
                "rated_rotor_speed",
                "rotor_diameter",
                "overall_height",
                "number_of_blades",
                "rated_power",
                "rated_wind_speed",
                "cut_in_wind_speed",
                "cut_out_wind_speed",
                "fraction_system_efficiency",
                "maximum_tip_speed_ratio",
                "maximum_power_coefficient",
                "annual_local_average_wind_speed",
                "height_for_local_average_wind_speed",
                "blade_chord_area",
                "blade_drag_coefficient",
                "blade_lift_coefficient",
                "power_coefficient_c1",
                "power_coefficient_c2",
                "power_coefficient_c3",
                "power_coefficient_c4",
                "power_coefficient_c5",
                "power_coefficient_c6"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "rotor_type",
                    "power_control"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_rotor_speed",
                    "rotor_diameter",
                    "overall_height",
                    "number_of_blades",
                    "rated_power",
                    "rated_wind_speed",
                    "cut_in_wind_speed",
                    "cut_out_wind_speed",
                    "fraction_system_efficiency",
                    "maximum_tip_speed_ratio",
                    "maximum_power_coefficient",
                    "annual_local_average_wind_speed",
                    "height_for_local_average_wind_speed",
                    "blade_chord_area",
                    "blade_drag_coefficient",
                    "blade_lift_coefficient",
                    "power_coefficient_c1",
                    "power_coefficient_c2",
                    "power_coefficient_c3",
                    "power_coefficient_c4",
                    "power_coefficient_c5",
                    "power_coefficient_c6"
                ]
            }
        },
        "type": "object",
        "memo": "Wind turbine generator.",
        "min_fields": 26.0
    }
}
```
