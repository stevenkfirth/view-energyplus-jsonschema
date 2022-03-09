```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "utility_cost_qualify_name": {
                    "type": "string",
                    "note": "Displayed in the report if the tariff does not qualify"
                },
                "tariff_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UtilityCostTariffs"
                    ],
                    "note": "The name of the UtilityCost:Tariff that is associated with this UtilityCost:Qualify."
                },
                "variable_name": {
                    "type": "string",
                    "note": "The name of the variable used. For energy and demand the automatically created variables totalEnergy and totalDemand should be used respectively."
                },
                "qualify_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Maximum",
                        "Minimum"
                    ],
                    "default": "Maximum"
                },
                "threshold_value_or_variable_name": {
                    "note": "The minimum or maximum value for the qualify. If the variable has values that are less than this value when the qualify type is minimum then the tariff may be disqualified. If the variable has values that are greater than this value when the qualify type is maximum then the tariff may be disqualified.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "season": {
                    "type": "string",
                    "enum": [
                        "Annual",
                        "Fall",
                        "Spring",
                        "Summer",
                        "Winter"
                    ],
                    "note": "If the UtilityCost:Qualify only applies to a season enter the season name. If this field is left blank it defaults to Annual."
                },
                "threshold_test": {
                    "type": "string",
                    "enum": [
                        "",
                        "Consecutive",
                        "Count"
                    ],
                    "default": "Consecutive",
                    "note": "Uses the number in Number of Months in one of two different ways depending on the Threshold  Test. If the Threshold Test is set to Count then the qualification is based on the count of the total number of months per year. If the Threshold Test is set to consecutive then the qualification is based on a consecutive number of months."
                },
                "number_of_months": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 12.0,
                    "note": "A number from 1 to 12. If no value entered 12 is assumed when the qualify type is minimum and 1 when the qualify type is maximum. This is the number of months that the threshold test applies to determine if the rate qualifies or not. If the season is less than 12 months (if it is not annual) then the value is automatically reduced to the number of months of the season."
                }
            },
            "required": [
                "utility_cost_qualify_name",
                "tariff_name",
                "variable_name",
                "threshold_value_or_variable_name"
            ]
        }
    },
    "group": "Economics",
    "legacy_idd": {
        "field_info": {
            "utility_cost_qualify_name": {
                "field_name": "Utility Cost Qualify Name",
                "field_type": "a"
            },
            "tariff_name": {
                "field_name": "Tariff Name",
                "field_type": "a"
            },
            "variable_name": {
                "field_name": "Variable Name",
                "field_type": "a"
            },
            "qualify_type": {
                "field_name": "Qualify Type",
                "field_type": "a"
            },
            "threshold_value_or_variable_name": {
                "field_name": "Threshold Value or Variable Name",
                "field_type": "a"
            },
            "season": {
                "field_name": "Season",
                "field_type": "a"
            },
            "threshold_test": {
                "field_name": "Threshold Test",
                "field_type": "a"
            },
            "number_of_months": {
                "field_name": "Number of Months",
                "field_type": "n"
            }
        },
        "fields": [
            "utility_cost_qualify_name",
            "tariff_name",
            "variable_name",
            "qualify_type",
            "threshold_value_or_variable_name",
            "season",
            "threshold_test",
            "number_of_months"
        ],
        "alphas": {
            "fields": [
                "utility_cost_qualify_name",
                "tariff_name",
                "variable_name",
                "qualify_type",
                "threshold_value_or_variable_name",
                "season",
                "threshold_test"
            ]
        },
        "numerics": {
            "fields": [
                "number_of_months"
            ]
        }
    },
    "type": "object",
    "memo": "The qualify object allows only tariffs to be selected based on limits which may apply such as maximum or minimum demand requirements. If the results of the simulation fall outside of the range of qualifications, that tariff is still calculated but the \"Qualified\" entry will say \"No\" and the UtilityCost:Qualify that caused its exclusion is shown. Multiple UtilityCost:Qualify objects can appear for the same tariff and they can be based on any variable."
}
```
