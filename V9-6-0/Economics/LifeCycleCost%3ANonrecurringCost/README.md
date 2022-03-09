```
{
    "LifeCycleCost:NonrecurringCost": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "category": {
                        "type": "string",
                        "enum": [
                            "",
                            "Construction",
                            "OtherCapital",
                            "Salvage"
                        ],
                        "default": "Construction"
                    },
                    "cost": {
                        "type": "number",
                        "note": "Enter the non-recurring cost value. For construction and other capital costs the value entered is typically a positive value. For salvage costs the value entered is typically a negative value which represents the money paid to the investor for the equipment at the end of the study period."
                    },
                    "start_of_costs": {
                        "type": "string",
                        "enum": [
                            "",
                            "BasePeriod",
                            "ServicePeriod"
                        ],
                        "default": "ServicePeriod",
                        "note": "Enter when the costs start. The First Year of Cost is based on the number of years past the Start of Costs. For most non-recurring costs the Start of Costs should be Base Period which begins at the base month and year."
                    },
                    "years_from_start": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 100.0,
                        "note": "This field and the Months From Start field together represent the time from either the start of the Service Period on the service month and year or start of the Base Period on the base month and year (depending on the Start of Cost field) that the costs start to occur. Only integers should be entered representing whole years."
                    },
                    "months_from_start": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1200.0,
                        "note": "This field and the Years From Start field together represent the time from either the start of the Service Period on the service month and year or start of the Base Period on the base month and year (depending on the Start of Cost field) that the costs start to occur. Only integers should be entered representing whole months. The Years From Start (times 12) and Months From Start are added together."
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
                }
            },
            "fields": [
                "name",
                "category",
                "cost",
                "start_of_costs",
                "years_from_start",
                "months_from_start"
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
                    "months_from_start"
                ]
            }
        },
        "type": "object",
        "memo": "A non-recurring cost happens only once during the study period. For costs that occur more than once during the study period on a regular schedule, use the LifeCycleCost:RecurringCost object."
    }
}
```
