```
{
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
                    "type": "number"
                },
                "efficiency_function_of_power_curve_name": {
                    "type": "string",
                    "note": "curve describes efficiency as a function of power curve is normalized relative to rated power in next field",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "rated_maximum_continuous_input_power": {
                    "type": "number",
                    "units": "W"
                },
                "minimum_efficiency": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "maximum_efficiency": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "minimum_power_output": {
                    "type": "number",
                    "units": "W"
                },
                "maximum_power_output": {
                    "type": "number",
                    "units": "W"
                },
                "ancillary_power_consumed_in_standby": {
                    "type": "number",
                    "units": "W"
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
            "efficiency_function_of_power_curve_name": {
                "field_name": "Efficiency Function of Power Curve Name",
                "field_type": "a"
            },
            "rated_maximum_continuous_input_power": {
                "field_name": "Rated Maximum Continuous Input Power",
                "field_type": "n"
            },
            "minimum_efficiency": {
                "field_name": "Minimum Efficiency",
                "field_type": "n"
            },
            "maximum_efficiency": {
                "field_name": "Maximum Efficiency",
                "field_type": "n"
            },
            "minimum_power_output": {
                "field_name": "Minimum Power Output",
                "field_type": "n"
            },
            "maximum_power_output": {
                "field_name": "Maximum Power Output",
                "field_type": "n"
            },
            "ancillary_power_consumed_in_standby": {
                "field_name": "Ancillary Power Consumed In Standby",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "zone_name",
            "radiative_fraction",
            "efficiency_function_of_power_curve_name",
            "rated_maximum_continuous_input_power",
            "minimum_efficiency",
            "maximum_efficiency",
            "minimum_power_output",
            "maximum_power_output",
            "ancillary_power_consumed_in_standby"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "efficiency_function_of_power_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "radiative_fraction",
                "rated_maximum_continuous_input_power",
                "minimum_efficiency",
                "maximum_efficiency",
                "minimum_power_output",
                "maximum_power_output",
                "ancillary_power_consumed_in_standby"
            ]
        }
    },
    "type": "object",
    "memo": "Electric power inverter to convert from direct current (DC) to alternating current (AC) in an electric load center that contains photovoltaic modules. This input object is for an inverter model where efficiency is a function of normalized power."
}
```
