```
{
    "LifeCycleCost:RecurringCosts": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "category": {
                        "type": "string",
                        "enum": [
                            "",
                            "Maintenance",
                            "MajorOverhaul",
                            "MinorOverhaul",
                            "Operation",
                            "OtherOperational",
                            "Repair",
                            "Replacement"
                        ],
                        "default": "Maintenance"
                    },
                    "cost": {
                        "type": "number",
                        "note": "Enter the cost in dollars (or the appropriate monetary unit) for the recurring costs. Enter the cost for each time it occurs. For example if the annual maintenance cost is 500 dollars enter 500 here."
                    },
                    "start_of_costs": {
                        "type": "string",
                        "enum": [
                            "",
                            "BasePeriod",
                            "ServicePeriod"
                        ],
                        "default": "ServicePeriod",
                        "note": "Enter when the costs start. The First Year of Cost is based on the number of years past the Start of Costs. For most maintenance costs the Start of Costs should be Service Period."
                    },
                    "years_from_start": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 100.0,
                        "note": "This field and the Months From Start field together represent the time from either the start of the Service Period on the service month and year or start of the Base Period on the base month and year (depending on the Start of Costs field) that the costs start to occur. Only integers should be entered representing whole years."
                    },
                    "months_from_start": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1200.0,
                        "note": "This field and the Years From Start field together represent the time from either the start of the Service Period on the service month and year or start of the Base Period on the base month and year (depending on the Start of Costs field) that the costs start to occur. Only integers should be entered representing whole months. The Years From Start (times 12) and Months From Start are added together."
                    },
                    "repeat_period_years": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 100.0,
                        "default": 1.0,
                        "note": "This field and the Repeat Period Months field indicate how much time elapses between re-occurrences of the cost. For costs that occur every year such the Repeat Period Years should be 1 and Repeat Period Months should be 0. Only integers should be entered representing whole years."
                    },
                    "repeat_period_months": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1200.0,
                        "default": 0.0,
                        "note": "This field and the Repeat Period Years field indicate how much time elapses between re-occurrences of the cost. Only integers should be entered representing whole years. The Repeat Period Years (times 12) and Repeat Period Months are added together."
                    },
                    "annual_escalation_rate": {
                        "type": "number",
                        "minimum": -0.3,
                        "maximum": 0.3,
                        "note": "Enter the annual escalation rate as a decimal. For a 1% rate enter the value 0.01. This input is used when the Inflation Approach is CurrentDollar. When Inflation Approach is set to ConstantDollar this input is ignored."
                    }
                }
            }
        },
        "group": "Economics",
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
                "category": {
                    "field_name": "Category",
                    "field_type": "a"
                },
                "cost": {
                    "field_name": "Cost",
                    "field_type": "n"
                },
                "start_of_costs": {
                    "field_name": "Start of Costs",
                    "field_type": "a"
                },
                "years_from_start": {
                    "field_name": "Years from Start",
                    "field_type": "n"
                },
                "months_from_start": {
                    "field_name": "Months from Start",
                    "field_type": "n"
                },
                "repeat_period_years": {
                    "field_name": "Repeat Period Years",
                    "field_type": "n"
                },
                "repeat_period_months": {
                    "field_name": "Repeat Period Months",
                    "field_type": "n"
                },
                "annual_escalation_rate": {
                    "field_name": "Annual escalation rate",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "category",
                "cost",
                "start_of_costs",
                "years_from_start",
                "months_from_start",
                "repeat_period_years",
                "repeat_period_months",
                "annual_escalation_rate"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "category",
                    "start_of_costs"
                ]
            },
            "numerics": {
                "fields": [
                    "cost",
                    "years_from_start",
                    "months_from_start",
                    "repeat_period_years",
                    "repeat_period_months",
                    "annual_escalation_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Recurring costs are costs that repeat over time on a regular schedule during the study period. If costs associated with equipment do repeat but not on a regular schedule, use LifeCycleCost:NonrecurringCost objects instead.",
        "min_fields": 7.0
    }
}
```
