```
{
    "ComponentCost:Adjustments": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "miscellaneous_cost_per_conditioned_area": {
                        "type": "number",
                        "note": "based on conditioned floor area for cost not accounted for in current line item cost model",
                        "units": "$/m2"
                    },
                    "design_and_engineering_fees": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "contractor_fee": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "contingency": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "permits_bonding_and_insurance": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "commissioning_fee": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "regional_adjustment_factor": {
                        "type": "number",
                        "units": "dimensionless",
                        "note": "for use with average data in line item and Misc cost models"
                    }
                }
            }
        },
        "group": "Economics",
        "legacy_idd": {
            "field_info": {
                "miscellaneous_cost_per_conditioned_area": {
                    "field_name": "Miscellaneous Cost per Conditioned Area",
                    "field_type": "n"
                },
                "design_and_engineering_fees": {
                    "field_name": "Design and Engineering Fees",
                    "field_type": "n"
                },
                "contractor_fee": {
                    "field_name": "Contractor Fee",
                    "field_type": "n"
                },
                "contingency": {
                    "field_name": "Contingency",
                    "field_type": "n"
                },
                "permits_bonding_and_insurance": {
                    "field_name": "Permits, Bonding and Insurance",
                    "field_type": "n"
                },
                "commissioning_fee": {
                    "field_name": "Commissioning Fee",
                    "field_type": "n"
                },
                "regional_adjustment_factor": {
                    "field_name": "Regional Adjustment Factor",
                    "field_type": "n"
                }
            },
            "fields": [
                "miscellaneous_cost_per_conditioned_area",
                "design_and_engineering_fees",
                "contractor_fee",
                "contingency",
                "permits_bonding_and_insurance",
                "commissioning_fee",
                "regional_adjustment_factor"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "miscellaneous_cost_per_conditioned_area",
                    "design_and_engineering_fees",
                    "contractor_fee",
                    "contingency",
                    "permits_bonding_and_insurance",
                    "commissioning_fee",
                    "regional_adjustment_factor"
                ]
            }
        },
        "type": "object",
        "memo": "Used to perform various modifications to the construction costs to arrive at an estimate for total project costs. This object allows extending the line item model so that the overall costs of the project will reflect various profit and fees."
    }
}
```
