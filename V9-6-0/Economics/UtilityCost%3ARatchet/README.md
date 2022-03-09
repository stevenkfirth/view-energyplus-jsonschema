```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "tariff_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UtilityCostTariffs"
                    ],
                    "note": "The name of the UtilityCost:Tariff that is associated with this UtilityCost:Ratchet."
                },
                "baseline_source_variable": {
                    "type": "string",
                    "note": "When the ratcheted value exceeds the baseline value for a month the ratcheted value is used but when the baseline value is greater then the ratcheted value the baseline value is used. Usually the electric demand charge is used. The baseline source variable can be the results of another ratchet object. This allows utility tariffs that have multiple ratchets to be modeled."
                },
                "adjustment_source_variable": {
                    "type": "string",
                    "note": "The variable that the ratchet is calculated from. It is often but not always the same as the baseline source variable. The ratcheting calculations using offset and multiplier are using the values from the adjustment source variable. If left blank the adjustment source variable is the same as the baseline source variable."
                },
                "season_from": {
                    "type": "string",
                    "enum": [
                        "Annual",
                        "Fall",
                        "Monthly",
                        "Spring",
                        "Summer",
                        "Winter"
                    ],
                    "note": "The name of the season that is being examined. The maximum value for all of the months in the named season is what is used with the multiplier and offset. This is most commonly Summer or Annual. When Monthly is used the adjustment source variable is used directly for all months."
                },
                "season_to": {
                    "type": "string",
                    "enum": [
                        "Annual",
                        "Fall",
                        "Spring",
                        "Summer",
                        "Winter"
                    ],
                    "note": "The name of the season when the ratchet would be calculated. This is most commonly Winter. The ratchet only is applied to the months in the named season. The resulting variable for months not in the Season To selection will contain the values as appear in the baseline source variable."
                },
                "multiplier_value_or_variable_name": {
                    "note": "Often the ratchet has a clause such as \"the current month demand or 90% of the summer month demand\". For this case a value of 0.9 would be entered here as the multiplier. This value may be left blank if no multiplier is needed and a value of one will be used as a default.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "offset_value_or_variable_name": {
                    "note": "A less common strategy is to say that the ratchet must be all demand greater than a value in this case an offset that is added to the demand may be entered here. If entered it is common for the offset value to be negative representing that the demand be reduced. If no value is entered it is assumed to be zero and not affect the ratchet.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                }
            },
            "required": [
                "tariff_name",
                "baseline_source_variable",
                "adjustment_source_variable"
            ]
        }
    },
    "group": "Economics",
    "name": {
        "type": "string",
        "is_required": true,
        "note": "Ratchet Variable Name The name of the ratchet and the name of the result of this single ratchet."
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "tariff_name": {
                "field_name": "Tariff Name",
                "field_type": "a"
            },
            "baseline_source_variable": {
                "field_name": "Baseline Source Variable",
                "field_type": "a"
            },
            "adjustment_source_variable": {
                "field_name": "Adjustment Source Variable",
                "field_type": "a"
            },
            "season_from": {
                "field_name": "Season From",
                "field_type": "a"
            },
            "season_to": {
                "field_name": "Season To",
                "field_type": "a"
            },
            "multiplier_value_or_variable_name": {
                "field_name": "Multiplier Value or Variable Name",
                "field_type": "a"
            },
            "offset_value_or_variable_name": {
                "field_name": "Offset Value or Variable Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "tariff_name",
            "baseline_source_variable",
            "adjustment_source_variable",
            "season_from",
            "season_to",
            "multiplier_value_or_variable_name",
            "offset_value_or_variable_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "tariff_name",
                "baseline_source_variable",
                "adjustment_source_variable",
                "season_from",
                "season_to",
                "multiplier_value_or_variable_name",
                "offset_value_or_variable_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Allows the modeling of tariffs that include some type of seasonal ratcheting. Ratchets are most common when used with electric demand charges. A ratchet is when a utility requires that the demand charge for a month with a low demand may be increased to be more consistent with a month that set a higher demand charge."
}
```
