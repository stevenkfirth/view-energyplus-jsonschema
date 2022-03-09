```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "fan_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FansCVandVAV",
                        "FansComponentModel"
                    ]
                },
                "fan_total_efficiency": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0
                },
                "pressure_rise": {
                    "type": "number",
                    "units": "Pa",
                    "ip-units": "inH2O"
                },
                "maximum_flow_rate": {
                    "units": "m3/s",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "motor_efficiency": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0
                },
                "motor_in_airstream_fraction": {
                    "type": "number",
                    "default": 1.0,
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "note": "0.0 means fan motor outside of airstream 1.0 means fan motor inside of airstream"
                }
            },
            "required": [
                "fan_name",
                "fan_total_efficiency",
                "pressure_rise",
                "motor_efficiency"
            ]
        }
    },
    "group": "Fans",
    "legacy_idd": {
        "field_info": {
            "fan_name": {
                "field_name": "Fan Name",
                "field_type": "a"
            },
            "fan_total_efficiency": {
                "field_name": "Fan Total Efficiency",
                "field_type": "n"
            },
            "pressure_rise": {
                "field_name": "Pressure Rise",
                "field_type": "n"
            },
            "maximum_flow_rate": {
                "field_name": "Maximum Flow Rate",
                "field_type": "n"
            },
            "motor_efficiency": {
                "field_name": "Motor Efficiency",
                "field_type": "n"
            },
            "motor_in_airstream_fraction": {
                "field_name": "Motor in Airstream Fraction",
                "field_type": "n"
            }
        },
        "fields": [
            "fan_name",
            "fan_total_efficiency",
            "pressure_rise",
            "maximum_flow_rate",
            "motor_efficiency",
            "motor_in_airstream_fraction"
        ],
        "alphas": {
            "fields": [
                "fan_name"
            ]
        },
        "numerics": {
            "fields": [
                "fan_total_efficiency",
                "pressure_rise",
                "maximum_flow_rate",
                "motor_efficiency",
                "motor_in_airstream_fraction"
            ]
        }
    },
    "type": "object",
    "memo": "Specifies an alternate set of performance parameters for a fan. These alternate parameters are used when a system manager (such as AvailabilityManager:NightVentilation) sets a specified flow rate. May be used with Fan:ConstantVolume, Fan:VariableVolume and Fan:ComponentModel. If the fan model senses that a fixed flow rate has been set, it will use these alternate performance parameters. It is assumed that the fan will run at a fixed speed in the alternate mode."
}
```
