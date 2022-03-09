```
{
    "ComponentCost:Reference": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "reference_building_line_item_costs": {
                        "type": "number",
                        "units": "$",
                        "note": "should be comparable to the components in current line item cost model"
                    },
                    "reference_building_miscellaneous_cost_per_conditioned_area": {
                        "type": "number",
                        "units": "$/m2",
                        "note": "based on conditioned floor area for cost not accounted for in reference line item costs"
                    },
                    "reference_building_design_and_engineering_fees": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "reference_building_contractor_fee": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "reference_building_contingency": {
                        "type": "number"
                    },
                    "reference_building_permits_bonding_and_insurance": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "reference_building_commissioning_fee": {
                        "type": "number",
                        "units": "dimensionless"
                    },
                    "reference_building_regional_adjustment_factor": {
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
                "reference_building_line_item_costs": {
                    "field_name": "Reference Building Line Item Costs",
                    "field_type": "n"
                },
                "reference_building_miscellaneous_cost_per_conditioned_area": {
                    "field_name": "Reference Building Miscellaneous Cost per Conditioned Area",
                    "field_type": "n"
                },
                "reference_building_design_and_engineering_fees": {
                    "field_name": "Reference Building Design and Engineering Fees",
                    "field_type": "n"
                },
                "reference_building_contractor_fee": {
                    "field_name": "Reference Building Contractor Fee",
                    "field_type": "n"
                },
                "reference_building_contingency": {
                    "field_name": "Reference Building Contingency",
                    "field_type": "n"
                },
                "reference_building_permits_bonding_and_insurance": {
                    "field_name": "Reference Building Permits, Bonding and Insurance",
                    "field_type": "n"
                },
                "reference_building_commissioning_fee": {
                    "field_name": "Reference Building Commissioning Fee",
                    "field_type": "n"
                },
                "reference_building_regional_adjustment_factor": {
                    "field_name": "Reference Building Regional Adjustment Factor",
                    "field_type": "n"
                }
            },
            "fields": [
                "reference_building_line_item_costs",
                "reference_building_miscellaneous_cost_per_conditioned_area",
                "reference_building_design_and_engineering_fees",
                "reference_building_contractor_fee",
                "reference_building_contingency",
                "reference_building_permits_bonding_and_insurance",
                "reference_building_commissioning_fee",
                "reference_building_regional_adjustment_factor"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "reference_building_line_item_costs",
                    "reference_building_miscellaneous_cost_per_conditioned_area",
                    "reference_building_design_and_engineering_fees",
                    "reference_building_contractor_fee",
                    "reference_building_contingency",
                    "reference_building_permits_bonding_and_insurance",
                    "reference_building_commissioning_fee",
                    "reference_building_regional_adjustment_factor"
                ]
            }
        },
        "type": "object",
        "memo": "Used to allow comparing the current cost estimate to the results of a previous estimate for a reference building. This object parallels the ComponentCost:Adjustments object but adds a field for entering the cost line item model result for the reference building. The factors entered in this object are applied to the reference building while the factors listed in the ComponentCost:Adjustments object are applied to the current building model cost estimate."
    }
}
```
