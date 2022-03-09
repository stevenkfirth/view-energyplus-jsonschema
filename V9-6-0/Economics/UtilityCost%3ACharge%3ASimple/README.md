```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "utility_cost_charge_simple_name": {
                    "type": "string",
                    "note": "Charge Variable Name This is the name associated with the UtilityCost:Charge:Simple object and will appear in the report. In addition the results of the UtilityCost:Charge:Simple calculation are stored in a variable with the same name. That way the results may be used for further calculation. Spaces are not significant in Charge variable names. They are removed during the utility bill calculation process."
                },
                "tariff_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UtilityCostTariffs"
                    ],
                    "note": "The name of the UtilityCost:Tariff that is associated with this UtilityCost:Charge:Simple."
                },
                "source_variable": {
                    "type": "string",
                    "note": "The name of the source used by the UtilityCost:Charge:Simple. This is usually the name of the variable holding the energy or demand but may also be the name of any variable including the subtotal or basis if other charges are based on those. Typical values include totalEnergy totalDemand EnergyCharges DemandCharges ServiceCharges Basis Adjustments Surcharges Subtotal Taxes and Total. If it is a time-of-use rate then peakEnergy peakDemand shoulderEnergy shoulderDemand offPeakEnergy offPeakDemand midPeakEnergy and midPeakDemand. In addition see the Tariff Report to see other native variables that may be available. Also you can create additional user defined variables to model complex tariffs."
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
                    "note": "If this is set to annual the calculations are performed for the UtilityCost:Charge:Simple for the entire year (all months) otherwise it is calculated only for those months in the season defined."
                },
                "category_variable_name": {
                    "type": "string",
                    "enum": [
                        "Adjustment",
                        "Basis",
                        "DemandCharges",
                        "EnergyCharges",
                        "NotIncluded",
                        "ServiceCharges",
                        "Subtotal",
                        "Surcharge",
                        "Taxes",
                        "Total"
                    ],
                    "note": "This field shows where the charge should be added. The reason to enter this field appropriately is so that the charge gets reported in a reasonable category. The charge automatically gets added to the variable that is the category."
                },
                "cost_per_unit_value_or_variable_name": {
                    "note": "This field contains either a single number or the name of a variable. The number is multiplied with all of the energy or demand or other source that is specified in the source field. If a variable is used then the monthly values of the variable are multiplied against the variable specified in the source field. This field makes it easy to include a simple charge without specifying block sizes. This is a good way to include a tax or cost adjustment.",
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
                "utility_cost_charge_simple_name",
                "tariff_name",
                "source_variable",
                "category_variable_name",
                "cost_per_unit_value_or_variable_name"
            ]
        }
    },
    "group": "Economics",
    "legacy_idd": {
        "field_info": {
            "utility_cost_charge_simple_name": {
                "field_name": "Utility Cost Charge Simple Name",
                "field_type": "a"
            },
            "tariff_name": {
                "field_name": "Tariff Name",
                "field_type": "a"
            },
            "source_variable": {
                "field_name": "Source Variable",
                "field_type": "a"
            },
            "season": {
                "field_name": "Season",
                "field_type": "a"
            },
            "category_variable_name": {
                "field_name": "Category Variable Name",
                "field_type": "a"
            },
            "cost_per_unit_value_or_variable_name": {
                "field_name": "Cost per Unit Value or Variable Name",
                "field_type": "a"
            }
        },
        "fields": [
            "utility_cost_charge_simple_name",
            "tariff_name",
            "source_variable",
            "season",
            "category_variable_name",
            "cost_per_unit_value_or_variable_name"
        ],
        "alphas": {
            "fields": [
                "utility_cost_charge_simple_name",
                "tariff_name",
                "source_variable",
                "season",
                "category_variable_name",
                "cost_per_unit_value_or_variable_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "UtilityCost:Charge:Simple is one of the most often used objects for tariff calculation. It is used to compute energy and demand charges that are very simple. It may also be used for taxes, surcharges and any other charges that occur on a utility bill. Multiple UtilityCost:Charge:Simple objects may be defined for a single tariff and they will be added together."
}
```
