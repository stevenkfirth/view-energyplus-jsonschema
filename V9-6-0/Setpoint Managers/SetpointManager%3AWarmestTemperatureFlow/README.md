```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "control_variable": {
                    "type": "string",
                    "enum": [
                        "Temperature"
                    ]
                },
                "hvac_air_loop_name": {
                    "type": "string",
                    "note": "Enter the name of an AirLoopHVAC object.",
                    "data_type": "object_list",
                    "object_list": [
                        "AirPrimaryLoops"
                    ]
                },
                "minimum_setpoint_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "default": 12.0
                },
                "maximum_setpoint_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "default": 18.0
                },
                "strategy": {
                    "type": "string",
                    "note": "For TemperatureFirst the manager tries to find the highest setpoint temperature that will satisfy all the zone cooling loads at minimum supply air flow rate. If this setpoint temperature is less than the minimum, the setpoint temperature is set to the minimum, and the supply air flow rate is increased to meet the loads. For FlowFirst the manager tries to find the lowest supply air flow rate that will satisfy all the zone cooling loads at the maximum setpoint temperature. If this flow is greater than the maximum, the flow is set to the maximum and the setpoint temperature is reduced to satisfy the cooling loads.",
                    "enum": [
                        "",
                        "FlowFirst",
                        "TemperatureFirst"
                    ],
                    "default": "TemperatureFirst"
                },
                "setpoint_node_or_nodelist_name": {
                    "type": "string",
                    "note": "Node(s) at which the temperature will be set"
                },
                "minimum_turndown_ratio": {
                    "type": "number",
                    "note": "Fraction of the maximum supply air flow rate. Used to define the minimum supply flow for the TemperatureFirst strategy.",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "default": 0.2
                }
            },
            "required": [
                "hvac_air_loop_name",
                "setpoint_node_or_nodelist_name"
            ]
        }
    },
    "group": "Setpoint Managers",
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
            "control_variable": {
                "field_name": "Control Variable",
                "field_type": "a"
            },
            "hvac_air_loop_name": {
                "field_name": "HVAC Air Loop Name",
                "field_type": "a"
            },
            "minimum_setpoint_temperature": {
                "field_name": "Minimum Setpoint Temperature",
                "field_type": "n"
            },
            "maximum_setpoint_temperature": {
                "field_name": "Maximum Setpoint Temperature",
                "field_type": "n"
            },
            "strategy": {
                "field_name": "Strategy",
                "field_type": "a"
            },
            "setpoint_node_or_nodelist_name": {
                "field_name": "Setpoint Node or NodeList Name",
                "field_type": "a"
            },
            "minimum_turndown_ratio": {
                "field_name": "Minimum Turndown Ratio",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "control_variable",
            "hvac_air_loop_name",
            "minimum_setpoint_temperature",
            "maximum_setpoint_temperature",
            "strategy",
            "setpoint_node_or_nodelist_name",
            "minimum_turndown_ratio"
        ],
        "alphas": {
            "fields": [
                "name",
                "control_variable",
                "hvac_air_loop_name",
                "strategy",
                "setpoint_node_or_nodelist_name"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_setpoint_temperature",
                "maximum_setpoint_temperature",
                "minimum_turndown_ratio"
            ]
        }
    },
    "type": "object",
    "memo": "This setpoint manager sets both the supply air temperature and the supply air flow rate.",
    "min_fields": 8.0
}
```
