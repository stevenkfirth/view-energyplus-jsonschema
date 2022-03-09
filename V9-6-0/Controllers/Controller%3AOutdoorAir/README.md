```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "relief_air_outlet_node_name": {
                    "type": "string"
                },
                "return_air_node_name": {
                    "type": "string"
                },
                "mixed_air_node_name": {
                    "type": "string"
                },
                "actuator_node_name": {
                    "type": "string",
                    "note": "Outdoor air inlet node entering the first pre-treat component if any"
                },
                "minimum_outdoor_air_flow_rate": {
                    "note": "If there is a Mechanical Ventilation Controller (Controller:MechanicalVentilation), note that this value times the Minimum Outdoor Air Schedule is a hard minimum that may override DCV or other advanced OA controls.",
                    "units": "m3/s",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "maximum_outdoor_air_flow_rate": {
                    "units": "m3/s",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "economizer_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "DifferentialDryBulb",
                        "DifferentialDryBulbAndEnthalpy",
                        "DifferentialEnthalpy",
                        "ElectronicEnthalpy",
                        "FixedDewPointAndDryBulb",
                        "FixedDryBulb",
                        "FixedEnthalpy",
                        "NoEconomizer"
                    ],
                    "default": "NoEconomizer"
                },
                "economizer_control_action_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "MinimumFlowWithBypass",
                        "ModulateFlow"
                    ],
                    "default": "ModulateFlow"
                },
                "economizer_maximum_limit_dry_bulb_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "Enter the maximum outdoor dry-bulb temperature limit for FixedDryBulb economizer control type. No input or blank input means this limit is not operative. Limit is applied regardless of economizer control type."
                },
                "economizer_maximum_limit_enthalpy": {
                    "type": "number",
                    "units": "J/kg",
                    "note": "Enter the maximum outdoor enthalpy limit for FixedEnthalpy economizer control type. No input or blank input means this limit is not operative Limit is applied regardless of economizer control type."
                },
                "economizer_maximum_limit_dewpoint_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "Enter the maximum outdoor dewpoint temperature limit for FixedDewPointAndDryBulb economizer control type. No input or blank input means this limit is not operative. Limit is applied regardless of economizer control type."
                },
                "electronic_enthalpy_limit_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Enter the name of a quadratic or cubic curve which defines the maximum outdoor humidity ratio (function of outdoor dry-bulb temperature) for ElectronicEnthalpy economizer control type. No input or blank input means this limit is not operative Limit is applied regardless of economizer control type."
                },
                "economizer_minimum_limit_dry_bulb_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "Enter the minimum outdoor dry-bulb temperature limit for economizer control. No input or blank input means this limit is not operative Limit is applied regardless of economizer control type."
                },
                "lockout_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "LockoutWithCompressor",
                        "LockoutWithHeating",
                        "NoLockout"
                    ],
                    "default": "NoLockout"
                },
                "minimum_limit_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "FixedMinimum",
                        "ProportionalMinimum"
                    ],
                    "default": "ProportionalMinimum"
                },
                "minimum_outdoor_air_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Schedule values multiply the minimum outdoor air flow rate"
                },
                "minimum_fraction_of_outdoor_air_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "schedule values multiply the design/mixed air flow rate"
                },
                "maximum_fraction_of_outdoor_air_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "schedule values multiply the design/mixed air flow rate"
                },
                "mechanical_ventilation_controller_name": {
                    "type": "string",
                    "note": "Enter the name of a Controller:MechanicalVentilation object. Optional field for defining outdoor ventilation air based on flow rate per unit floor area and flow rate per person. Simplified method of demand-controlled ventilation.",
                    "data_type": "object_list",
                    "object_list": [
                        "ControllerMechanicalVentNames"
                    ]
                },
                "time_of_day_economizer_control_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Optional schedule to simulate \"push-button\" type economizer control. Schedule values greater than 0 indicate time-of-day economizer control is enabled. Economizer control may be used with or without the high humidity control option. When used together, high humidity control has priority over economizer control. If the field Economizer Control Type = NoEconomizer, then this option is disabled."
                },
                "high_humidity_control": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "Optional field to enable modified outdoor air flow rates based on zone relative humidity. Select Yes to modify outdoor air flow rate based on a zone humidistat. Select No to disable this feature. If the field Economizer Control Type = NoEconomizer, then this option is disabled."
                },
                "humidistat_control_zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ],
                    "note": "Enter the name of the zone where the humidistat is located. This field is only used when the field High Humidity Control = Yes."
                },
                "high_humidity_outdoor_air_flow_ratio": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0,
                    "note": "Enter the ratio of outdoor air to the maximum outdoor air flow rate when modified air flow rates are active based on high indoor humidity. The minimum value must be greater than 0. This field is only used when the field High Humidity Control = Yes."
                },
                "control_high_indoor_humidity_based_on_outdoor_humidity_ratio": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes",
                    "note": "If No is selected, the outdoor air flow rate is modified any time indoor relative humidity is above the humidistat setpoint. If Yes is selected, the outdoor air flow rate is modified any time the indoor relative humidity is above the humidistat setpoint and the outdoor humidity ratio is less than the indoor humidity ratio. This field is only used when the field High Humidity Control = Yes."
                },
                "heat_recovery_bypass_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "BypassWhenOAFlowGreaterThanMinimum",
                        "BypassWhenWithinEconomizerLimits"
                    ],
                    "default": "BypassWhenWithinEconomizerLimits",
                    "note": "BypassWhenWithinEconomizerLimits specifies that heat recovery is active only when the economizer is off because conditions are outside the economizer control limits BypassWhenOAFlowGreaterThanMinimum specifies enhanced economizer controls to allow heat recovery when economizer is active (within limits) but the outdoor air flow rate is at the minimum."
                }
            },
            "required": [
                "relief_air_outlet_node_name",
                "return_air_node_name",
                "mixed_air_node_name",
                "actuator_node_name",
                "minimum_outdoor_air_flow_rate",
                "maximum_outdoor_air_flow_rate"
            ]
        }
    },
    "group": "Controllers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AirLoopControllers",
            "OAControllerNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "relief_air_outlet_node_name": {
                "field_name": "Relief Air Outlet Node Name",
                "field_type": "a"
            },
            "return_air_node_name": {
                "field_name": "Return Air Node Name",
                "field_type": "a"
            },
            "mixed_air_node_name": {
                "field_name": "Mixed Air Node Name",
                "field_type": "a"
            },
            "actuator_node_name": {
                "field_name": "Actuator Node Name",
                "field_type": "a"
            },
            "minimum_outdoor_air_flow_rate": {
                "field_name": "Minimum Outdoor Air Flow Rate",
                "field_type": "n"
            },
            "maximum_outdoor_air_flow_rate": {
                "field_name": "Maximum Outdoor Air Flow Rate",
                "field_type": "n"
            },
            "economizer_control_type": {
                "field_name": "Economizer Control Type",
                "field_type": "a"
            },
            "economizer_control_action_type": {
                "field_name": "Economizer Control Action Type",
                "field_type": "a"
            },
            "economizer_maximum_limit_dry_bulb_temperature": {
                "field_name": "Economizer Maximum Limit Dry-Bulb Temperature",
                "field_type": "n"
            },
            "economizer_maximum_limit_enthalpy": {
                "field_name": "Economizer Maximum Limit Enthalpy",
                "field_type": "n"
            },
            "economizer_maximum_limit_dewpoint_temperature": {
                "field_name": "Economizer Maximum Limit Dewpoint Temperature",
                "field_type": "n"
            },
            "electronic_enthalpy_limit_curve_name": {
                "field_name": "Electronic Enthalpy Limit Curve Name",
                "field_type": "a"
            },
            "economizer_minimum_limit_dry_bulb_temperature": {
                "field_name": "Economizer Minimum Limit Dry-Bulb Temperature",
                "field_type": "n"
            },
            "lockout_type": {
                "field_name": "Lockout Type",
                "field_type": "a"
            },
            "minimum_limit_type": {
                "field_name": "Minimum Limit Type",
                "field_type": "a"
            },
            "minimum_outdoor_air_schedule_name": {
                "field_name": "Minimum Outdoor Air Schedule Name",
                "field_type": "a"
            },
            "minimum_fraction_of_outdoor_air_schedule_name": {
                "field_name": "Minimum Fraction of Outdoor Air Schedule Name",
                "field_type": "a"
            },
            "maximum_fraction_of_outdoor_air_schedule_name": {
                "field_name": "Maximum Fraction of Outdoor Air Schedule Name",
                "field_type": "a"
            },
            "mechanical_ventilation_controller_name": {
                "field_name": "Mechanical Ventilation Controller Name",
                "field_type": "a"
            },
            "time_of_day_economizer_control_schedule_name": {
                "field_name": "Time of Day Economizer Control Schedule Name",
                "field_type": "a"
            },
            "high_humidity_control": {
                "field_name": "High Humidity Control",
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
            },
            "heat_recovery_bypass_control_type": {
                "field_name": "Heat Recovery Bypass Control Type",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "relief_air_outlet_node_name",
            "return_air_node_name",
            "mixed_air_node_name",
            "actuator_node_name",
            "minimum_outdoor_air_flow_rate",
            "maximum_outdoor_air_flow_rate",
            "economizer_control_type",
            "economizer_control_action_type",
            "economizer_maximum_limit_dry_bulb_temperature",
            "economizer_maximum_limit_enthalpy",
            "economizer_maximum_limit_dewpoint_temperature",
            "electronic_enthalpy_limit_curve_name",
            "economizer_minimum_limit_dry_bulb_temperature",
            "lockout_type",
            "minimum_limit_type",
            "minimum_outdoor_air_schedule_name",
            "minimum_fraction_of_outdoor_air_schedule_name",
            "maximum_fraction_of_outdoor_air_schedule_name",
            "mechanical_ventilation_controller_name",
            "time_of_day_economizer_control_schedule_name",
            "high_humidity_control",
            "humidistat_control_zone_name",
            "high_humidity_outdoor_air_flow_ratio",
            "control_high_indoor_humidity_based_on_outdoor_humidity_ratio",
            "heat_recovery_bypass_control_type"
        ],
        "alphas": {
            "fields": [
                "name",
                "relief_air_outlet_node_name",
                "return_air_node_name",
                "mixed_air_node_name",
                "actuator_node_name",
                "economizer_control_type",
                "economizer_control_action_type",
                "electronic_enthalpy_limit_curve_name",
                "lockout_type",
                "minimum_limit_type",
                "minimum_outdoor_air_schedule_name",
                "minimum_fraction_of_outdoor_air_schedule_name",
                "maximum_fraction_of_outdoor_air_schedule_name",
                "mechanical_ventilation_controller_name",
                "time_of_day_economizer_control_schedule_name",
                "high_humidity_control",
                "humidistat_control_zone_name",
                "control_high_indoor_humidity_based_on_outdoor_humidity_ratio",
                "heat_recovery_bypass_control_type"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_outdoor_air_flow_rate",
                "maximum_outdoor_air_flow_rate",
                "economizer_maximum_limit_dry_bulb_temperature",
                "economizer_maximum_limit_enthalpy",
                "economizer_maximum_limit_dewpoint_temperature",
                "economizer_minimum_limit_dry_bulb_temperature",
                "high_humidity_outdoor_air_flow_ratio"
            ]
        }
    },
    "type": "object",
    "memo": "Controller to set the outdoor air flow rate for an air loop. Control options include fixed, proportional, scheduled, economizer, and demand-controlled ventilation.",
    "min_fields": 16.0
}
```
