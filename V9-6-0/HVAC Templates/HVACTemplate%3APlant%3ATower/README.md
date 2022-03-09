```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "tower_type": {
                    "type": "string",
                    "enum": [
                        "SingleSpeed",
                        "TwoSpeed"
                    ]
                },
                "high_speed_nominal_capacity": {
                    "note": "Applicable for tower type SingleSpeed and TwoSpeed Nominal tower capacity with entering water at 35C (95F), leaving water at 29.44C (85F), entering air at 25.56C (78F) wet-bulb temperature and 35C (95F) dry-bulb temperature, with the tower fan operating at high speed. Design water flow rate assumed to be 5.382E-8 m3/s per watt(3 gpm/ton). Nominal tower capacity times (1.25) gives the actual tower heat rejection at these operating conditions.",
                    "default": "Autosize",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "high_speed_fan_power": {
                    "note": "Applicable for tower type SingleSpeed and TwoSpeed",
                    "default": "Autosize",
                    "units": "W",
                    "ip-units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "low_speed_nominal_capacity": {
                    "note": "Applicable only for Tower Type TwoSpeed Nominal tower capacity with entering water at 35C (95F), leaving water at 29.44C (85F), entering air at 25.56C (78F) wet-bulb temperature and 35C (95F) dry-bulb temperature, with the tower fan operating at low speed. Design water flow rate assumed to be 5.382E-8 m3/s per watt of tower high-speed nominal capacity (3 gpm/ton). Nominal tower capacity times (1.25) gives the actual tower heat rejection at these operating conditions.",
                    "default": "Autosize",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "low_speed_fan_power": {
                    "note": "Applicable only for Tower Type TwoSpeed",
                    "default": "Autosize",
                    "units": "W",
                    "ip-units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "free_convection_capacity": {
                    "note": "Applicable for Tower Type SingleSpeed and TwoSpeed Tower capacity in free convection regime with entering water at 35C (95F), leaving water at 29.44C (85F), entering air at 25.56C (78F) wet-bulb temperature and 35C (95F) dry-bulb temperature. Design water flow rate assumed to be 5.382E-8 m3/s per watt of tower high-speed nominal capacity (3 gpm/ton). Tower free convection capacity times (1.25) gives the actual tower heat rejection at these operating conditions.",
                    "default": "Autosize",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "priority": {
                    "type": "string",
                    "note": "Applicable for all Tower Types If Condenser Plant Operation Scheme Type=Default in HVACTemplate:Plant:ChilledWaterLoop, then equipment operates in Priority order, 1, 2, 3, etc."
                },
                "sizing_factor": {
                    "type": "number",
                    "note": "Multiplies the autosized capacity and flow rates",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "template_plant_loop_type": {
                    "type": "string",
                    "note": "Specifies if this tower serves a template chilled water loop or mixed water loop If left blank, will serve a chilled water loop if present, or a mixed water loop (if no chilled water loop is present).",
                    "enum": [
                        "ChilledWater",
                        "MixedWater"
                    ]
                }
            },
            "required": [
                "tower_type"
            ]
        }
    },
    "group": "HVAC Templates",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "tower_type": {
                "field_name": "Tower Type",
                "field_type": "a"
            },
            "high_speed_nominal_capacity": {
                "field_name": "High Speed Nominal Capacity",
                "field_type": "n"
            },
            "high_speed_fan_power": {
                "field_name": "High Speed Fan Power",
                "field_type": "n"
            },
            "low_speed_nominal_capacity": {
                "field_name": "Low Speed Nominal Capacity",
                "field_type": "n"
            },
            "low_speed_fan_power": {
                "field_name": "Low Speed Fan Power",
                "field_type": "n"
            },
            "free_convection_capacity": {
                "field_name": "Free Convection Capacity",
                "field_type": "n"
            },
            "priority": {
                "field_name": "Priority",
                "field_type": "a"
            },
            "sizing_factor": {
                "field_name": "Sizing Factor",
                "field_type": "n"
            },
            "template_plant_loop_type": {
                "field_name": "Template Plant Loop Type",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "tower_type",
            "high_speed_nominal_capacity",
            "high_speed_fan_power",
            "low_speed_nominal_capacity",
            "low_speed_fan_power",
            "free_convection_capacity",
            "priority",
            "sizing_factor",
            "template_plant_loop_type"
        ],
        "alphas": {
            "fields": [
                "name",
                "tower_type",
                "priority",
                "template_plant_loop_type"
            ]
        },
        "numerics": {
            "fields": [
                "high_speed_nominal_capacity",
                "high_speed_fan_power",
                "low_speed_nominal_capacity",
                "low_speed_fan_power",
                "free_convection_capacity",
                "sizing_factor"
            ]
        }
    },
    "type": "object",
    "memo": "This object adds a cooling tower to an HVACTemplate:Plant:ChilledWaterLoop or MixedWaterLoop.",
    "min_fields": 9.0
}
```
