```
{
    "ElectricLoadCenter:Storage:Converter": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the converter is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "power_conversion_efficiency_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "FunctionOfPower",
                            "SimpleFixed"
                        ],
                        "default": "SimpleFixed",
                        "note": "SimpleFixed indicates power conversion losses are based on Simple Fixed Efficiency FunctionOfPower indicates power conversion losses are a function of normalized power using a curve or table."
                    },
                    "simple_fixed_efficiency": {
                        "type": "number",
                        "note": "Constant efficiency for conversion of AC to DC at all power levels. Field is only used when Power Conversion Efficiency Method is set to SimpleFixed.",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.95
                    },
                    "design_maximum_continuous_input_power": {
                        "type": "number",
                        "note": "Required field when Power Conversion Efficiency Method is set to FunctionOfPower.",
                        "units": "W"
                    },
                    "efficiency_function_of_power_curve_name": {
                        "type": "string",
                        "note": "Curve or table with a single independent variable that describes efficiency as a function of normalized power. The \"x\" input for curve or table is the ratio of current input power divided by design power in the previous field Required field when Power Conversion Efficiency Method is set to FunctionOfPower.",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "ancillary_power_consumed_in_standby": {
                        "type": "number",
                        "note": "Optional standby power consumed when converter is available but no power is being conditioned.",
                        "units": "W"
                    },
                    "zone_name": {
                        "type": "string",
                        "note": "enter name of zone to receive converter losses as heat if blank then converter is assumed to be outdoors",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "radiative_fraction": {
                        "type": "number",
                        "note": "fraction of zone heat gains treated as thermal radiation",
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
                "ConverterList"
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
                "power_conversion_efficiency_method": {
                    "field_name": "Power Conversion Efficiency Method",
                    "field_type": "a"
                },
                "simple_fixed_efficiency": {
                    "field_name": "Simple Fixed Efficiency",
                    "field_type": "n"
                },
                "design_maximum_continuous_input_power": {
                    "field_name": "Design Maximum Continuous Input Power",
                    "field_type": "n"
                },
                "efficiency_function_of_power_curve_name": {
                    "field_name": "Efficiency Function of Power Curve Name",
                    "field_type": "a"
                },
                "ancillary_power_consumed_in_standby": {
                    "field_name": "Ancillary Power Consumed In Standby",
                    "field_type": "n"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "radiative_fraction": {
                    "field_name": "Radiative Fraction",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "power_conversion_efficiency_method",
                "simple_fixed_efficiency",
                "design_maximum_continuous_input_power",
                "efficiency_function_of_power_curve_name",
                "ancillary_power_consumed_in_standby",
                "zone_name",
                "radiative_fraction"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "power_conversion_efficiency_method",
                    "efficiency_function_of_power_curve_name",
                    "zone_name"
                ]
            },
            "numerics": {
                "fields": [
                    "simple_fixed_efficiency",
                    "design_maximum_continuous_input_power",
                    "ancillary_power_consumed_in_standby",
                    "radiative_fraction"
                ]
            }
        },
        "type": "object",
        "memo": "This model is for converting AC to DC for grid-supplied charging of DC storage",
        "min_fields": 4.0
    }
}
```
