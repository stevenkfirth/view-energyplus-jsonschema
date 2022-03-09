```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "temperature_high_limit": {
                    "type": "number",
                    "units": "C",
                    "note": "Enter the maximum outdoor dry-bulb temperature limit for economizer operation. No input or blank input means this limit is not operative"
                },
                "temperature_low_limit": {
                    "type": "number",
                    "units": "C",
                    "note": "Enter the minimum outdoor dry-bulb temperature limit for economizer operation. No input or blank input means this limit is not operative"
                },
                "enthalpy_high_limit": {
                    "type": "number",
                    "units": "J/kg",
                    "note": "Enter the maximum outdoor enthalpy limit for economizer operation. No input or blank input means this limit is not operative"
                },
                "dewpoint_temperature_limit": {
                    "type": "number",
                    "units": "C",
                    "note": "Enter the maximum outdoor dew point temperature limit for economizer operation. No input or blank input means this limit is not operative"
                },
                "electronic_enthalpy_limit_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Enter the name of a quadratic or cubic curve which defines the maximum outdoor humidity ratio (function of outdoor dry-bulb temperature) for economizer operation. No input or blank input means this limit is not operative"
                },
                "exhaust_air_temperature_limit": {
                    "type": "string",
                    "enum": [
                        "",
                        "ExhaustAirTemperatureLimit",
                        "NoExhaustAirTemperatureLimit"
                    ],
                    "default": "NoExhaustAirTemperatureLimit"
                },
                "exhaust_air_enthalpy_limit": {
                    "type": "string",
                    "enum": [
                        "",
                        "ExhaustAirEnthalpyLimit",
                        "NoExhaustAirEnthalpyLimit"
                    ],
                    "default": "NoExhaustAirEnthalpyLimit"
                },
                "time_of_day_economizer_flow_control_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Schedule values greater than 0 indicate economizer operation is active. This schedule may be used with or without the High Humidity Control option. When used together, high humidity control has priority over economizer control."
                },
                "high_humidity_control_flag": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "Select Yes to modify air flow rates based on a zone humidistat. Select No to disable this feature."
                },
                "humidistat_control_zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ],
                    "note": "Enter the name of the zone where the humidistat is located."
                },
                "high_humidity_outdoor_air_flow_ratio": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0,
                    "note": "Enter the ratio of supply (outdoor) air to the maximum supply air flow rate when modified air flow rates are active based on high indoor humidity."
                },
                "control_high_indoor_humidity_based_on_outdoor_humidity_ratio": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes",
                    "note": "If NO is selected, the air flow rate is modified any time indoor relative humidity is above humidistat setpoint. If YES is selected, outdoor air flow rate is modified any time indoor relative humidity is above the humidistat setpoint AND the outdoor humidity ratio is less than the indoor humidity ratio."
                }
            }
        }
    },
    "group": "Zone HVAC Forced Air Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ControllerStandAloneEnergyRecoveryVentilator"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "temperature_high_limit": {
                "field_name": "Temperature High Limit",
                "field_type": "n"
            },
            "temperature_low_limit": {
                "field_name": "Temperature Low Limit",
                "field_type": "n"
            },
            "enthalpy_high_limit": {
                "field_name": "Enthalpy High Limit",
                "field_type": "n"
            },
            "dewpoint_temperature_limit": {
                "field_name": "Dewpoint Temperature Limit",
                "field_type": "n"
            },
            "electronic_enthalpy_limit_curve_name": {
                "field_name": "Electronic Enthalpy Limit Curve Name",
                "field_type": "a"
            },
            "exhaust_air_temperature_limit": {
                "field_name": "Exhaust Air Temperature Limit",
                "field_type": "a"
            },
            "exhaust_air_enthalpy_limit": {
                "field_name": "Exhaust Air Enthalpy Limit",
                "field_type": "a"
            },
            "time_of_day_economizer_flow_control_schedule_name": {
                "field_name": "Time of Day Economizer Flow Control Schedule Name",
                "field_type": "a"
            },
            "high_humidity_control_flag": {
                "field_name": "High Humidity Control Flag",
                "field_type": "a"
            },
            "humidistat_control_zone_name": {
                "field_name": "Humidistat Control Zone Name",
                "field_type": "a"
            },
            "high_humidity_outdoor_air_flow_ratio": {
                "field_name": "High Humidity Outdoor Air Flow Ratio",
                "field_type": "n"
            },
            "control_high_indoor_humidity_based_on_outdoor_humidity_ratio": {
                "field_name": "Control High Indoor Humidity Based on Outdoor Humidity Ratio",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "temperature_high_limit",
            "temperature_low_limit",
            "enthalpy_high_limit",
            "dewpoint_temperature_limit",
            "electronic_enthalpy_limit_curve_name",
            "exhaust_air_temperature_limit",
            "exhaust_air_enthalpy_limit",
            "time_of_day_economizer_flow_control_schedule_name",
            "high_humidity_control_flag",
            "humidistat_control_zone_name",
            "high_humidity_outdoor_air_flow_ratio",
            "control_high_indoor_humidity_based_on_outdoor_humidity_ratio"
        ],
        "alphas": {
            "fields": [
                "name",
                "electronic_enthalpy_limit_curve_name",
                "exhaust_air_temperature_limit",
                "exhaust_air_enthalpy_limit",
                "time_of_day_economizer_flow_control_schedule_name",
                "high_humidity_control_flag",
                "humidistat_control_zone_name",
                "control_high_indoor_humidity_based_on_outdoor_humidity_ratio"
            ]
        },
        "numerics": {
            "fields": [
                "temperature_high_limit",
                "temperature_low_limit",
                "enthalpy_high_limit",
                "dewpoint_temperature_limit",
                "high_humidity_outdoor_air_flow_ratio"
            ]
        }
    },
    "type": "object",
    "memo": "This controller is used exclusively by the ZoneHVAC:EnergyRecoveryVentilator object to allow economizer (free cooling) operation when possible.",
    "min_fields": 3.0
}
```
