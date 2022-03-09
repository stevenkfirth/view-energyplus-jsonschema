```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "utility_cost_charge_block_name": {
                    "type": "string",
                    "note": "Charge Variable Name This is the name associated with the UtilityCost:Charge:Block object and will appear in the report. In addition the results of the UtilityCost:Charge:Block are stored in a variable with the same name. That way the results may be used for further calculation."
                },
                "tariff_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UtilityCostTariffs"
                    ],
                    "note": "The name of the UtilityCost:Tariff that is associated with this UtilityCost:Charge:Block."
                },
                "source_variable": {
                    "type": "string",
                    "note": "The name of the source used by the UtilityCost:Charge:Block. This is usually the name of the variable holding the energy or demand but may also be the name of any variable including the subtotal or basis if other charges are based on those. Typical values include totalEnergy totalDemand EnergyCharges DemandCharges ServiceCharges Basis Adjustments Surcharges Subtotal Taxes and Total. If it is a time-of-use rate then peakEnergy peakDemand shoulderEnergy shoulderDemand offPeakEnergy offPeakDemand midPeakEnergy and midPeakDemand. In addition see the Tariff Report to see other native variables that may be available. Also you can create additional user defined variables to model complex tariffs."
                },
                "season": {
                    "type": "string",
                    "enum": [
                        "",
                        "Annual",
                        "Fall",
                        "Spring",
                        "Summer",
                        "Winter"
                    ],
                    "default": "Annual",
                    "note": "If this is set to annual the calculations are performed for the UtilityCost:Charge:Block for the entire year (all months) otherwise it is calculated only for those months in the season defined."
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
                "remaining_into_variable": {
                    "type": "string",
                    "note": "If the blocks do not use all of the energy or demand from the source some energy and demand remains then the remaining amount should be assigned to a variable. If no variable is assigned and some amount of energy or demand is not used in the block structure a warning will be issued."
                },
                "block_size_multiplier_value_or_variable_name": {
                    "note": "The sizes of the blocks are usually used directly but if a value or a variable is entered here the block sizes entered in the rest of the charge are first multiplied by the entered value prior to being used. This is common for rates that are kWh/kW rates and in that case the variable that holds the monthly total electric demand would be entered. If no value is entered a default value of one is assumed so that the block sizes remain exactly as entered. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_1_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_1_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_2_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_2_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_3_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_3_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_4_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_4_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_5_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_5_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_6_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_6_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_7_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_7_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_8_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_8_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_9_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_9_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_10_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_10_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_11_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_11_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_12_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_12_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_13_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_13_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_14_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_14_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_size_15_value_or_variable_name": {
                    "note": "The size of the block of the charges is entered here. For most rates that use multiple blocks this will be the value for the block size. Using remaining may be used when the remaining amount should be included in that block. This field is unusual because it can be either a number or a name of a variable.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string"
                        }
                    ]
                },
                "block_15_cost_per_unit_value_or_variable_name": {
                    "note": "The cost of the block. This field is unusual for the EnergyPlus syntax because it can be either a number or a name of a variable.",
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
                "utility_cost_charge_block_name",
                "tariff_name",
                "source_variable",
                "category_variable_name"
            ]
        }
    },
    "group": "Economics",
    "legacy_idd": {
        "field_info": {
            "utility_cost_charge_block_name": {
                "field_name": "Utility Cost Charge Block Name",
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
            "remaining_into_variable": {
                "field_name": "Remaining Into Variable",
                "field_type": "a"
            },
            "block_size_multiplier_value_or_variable_name": {
                "field_name": "Block Size Multiplier Value or Variable Name",
                "field_type": "a"
            },
            "block_size_1_value_or_variable_name": {
                "field_name": "Block Size 1 Value or Variable Name",
                "field_type": "a"
            },
            "block_1_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 1 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_2_value_or_variable_name": {
                "field_name": "Block Size 2 Value or Variable Name",
                "field_type": "a"
            },
            "block_2_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 2 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_3_value_or_variable_name": {
                "field_name": "Block Size 3 Value or Variable Name",
                "field_type": "a"
            },
            "block_3_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 3 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_4_value_or_variable_name": {
                "field_name": "Block Size 4 Value or Variable Name",
                "field_type": "a"
            },
            "block_4_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 4 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_5_value_or_variable_name": {
                "field_name": "Block Size 5 Value or Variable Name",
                "field_type": "a"
            },
            "block_5_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 5 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_6_value_or_variable_name": {
                "field_name": "Block Size 6 Value or Variable Name",
                "field_type": "a"
            },
            "block_6_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 6 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_7_value_or_variable_name": {
                "field_name": "Block Size 7 Value or Variable Name",
                "field_type": "a"
            },
            "block_7_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 7 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_8_value_or_variable_name": {
                "field_name": "Block Size 8 Value or Variable Name",
                "field_type": "a"
            },
            "block_8_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 8 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_9_value_or_variable_name": {
                "field_name": "Block Size 9 Value or Variable Name",
                "field_type": "a"
            },
            "block_9_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 9 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_10_value_or_variable_name": {
                "field_name": "Block Size 10 Value or Variable Name",
                "field_type": "a"
            },
            "block_10_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 10 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_11_value_or_variable_name": {
                "field_name": "Block Size 11 Value or Variable Name",
                "field_type": "a"
            },
            "block_11_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 11 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_12_value_or_variable_name": {
                "field_name": "Block Size 12 Value or Variable Name",
                "field_type": "a"
            },
            "block_12_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 12 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_13_value_or_variable_name": {
                "field_name": "Block Size 13 Value or Variable Name",
                "field_type": "a"
            },
            "block_13_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 13 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_14_value_or_variable_name": {
                "field_name": "Block Size 14 Value or Variable Name",
                "field_type": "a"
            },
            "block_14_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 14 Cost per Unit Value or Variable Name",
                "field_type": "a"
            },
            "block_size_15_value_or_variable_name": {
                "field_name": "Block Size 15 Value or Variable Name",
                "field_type": "a"
            },
            "block_15_cost_per_unit_value_or_variable_name": {
                "field_name": "Block 15 Cost per Unit Value or Variable Name",
                "field_type": "a"
            }
        },
        "fields": [
            "utility_cost_charge_block_name",
            "tariff_name",
            "source_variable",
            "season",
            "category_variable_name",
            "remaining_into_variable",
            "block_size_multiplier_value_or_variable_name",
            "block_size_1_value_or_variable_name",
            "block_1_cost_per_unit_value_or_variable_name",
            "block_size_2_value_or_variable_name",
            "block_2_cost_per_unit_value_or_variable_name",
            "block_size_3_value_or_variable_name",
            "block_3_cost_per_unit_value_or_variable_name",
            "block_size_4_value_or_variable_name",
            "block_4_cost_per_unit_value_or_variable_name",
            "block_size_5_value_or_variable_name",
            "block_5_cost_per_unit_value_or_variable_name",
            "block_size_6_value_or_variable_name",
            "block_6_cost_per_unit_value_or_variable_name",
            "block_size_7_value_or_variable_name",
            "block_7_cost_per_unit_value_or_variable_name",
            "block_size_8_value_or_variable_name",
            "block_8_cost_per_unit_value_or_variable_name",
            "block_size_9_value_or_variable_name",
            "block_9_cost_per_unit_value_or_variable_name",
            "block_size_10_value_or_variable_name",
            "block_10_cost_per_unit_value_or_variable_name",
            "block_size_11_value_or_variable_name",
            "block_11_cost_per_unit_value_or_variable_name",
            "block_size_12_value_or_variable_name",
            "block_12_cost_per_unit_value_or_variable_name",
            "block_size_13_value_or_variable_name",
            "block_13_cost_per_unit_value_or_variable_name",
            "block_size_14_value_or_variable_name",
            "block_14_cost_per_unit_value_or_variable_name",
            "block_size_15_value_or_variable_name",
            "block_15_cost_per_unit_value_or_variable_name"
        ],
        "alphas": {
            "fields": [
                "utility_cost_charge_block_name",
                "tariff_name",
                "source_variable",
                "season",
                "category_variable_name",
                "remaining_into_variable",
                "block_size_multiplier_value_or_variable_name",
                "block_size_1_value_or_variable_name",
                "block_1_cost_per_unit_value_or_variable_name",
                "block_size_2_value_or_variable_name",
                "block_2_cost_per_unit_value_or_variable_name",
                "block_size_3_value_or_variable_name",
                "block_3_cost_per_unit_value_or_variable_name",
                "block_size_4_value_or_variable_name",
                "block_4_cost_per_unit_value_or_variable_name",
                "block_size_5_value_or_variable_name",
                "block_5_cost_per_unit_value_or_variable_name",
                "block_size_6_value_or_variable_name",
                "block_6_cost_per_unit_value_or_variable_name",
                "block_size_7_value_or_variable_name",
                "block_7_cost_per_unit_value_or_variable_name",
                "block_size_8_value_or_variable_name",
                "block_8_cost_per_unit_value_or_variable_name",
                "block_size_9_value_or_variable_name",
                "block_9_cost_per_unit_value_or_variable_name",
                "block_size_10_value_or_variable_name",
                "block_10_cost_per_unit_value_or_variable_name",
                "block_size_11_value_or_variable_name",
                "block_11_cost_per_unit_value_or_variable_name",
                "block_size_12_value_or_variable_name",
                "block_12_cost_per_unit_value_or_variable_name",
                "block_size_13_value_or_variable_name",
                "block_13_cost_per_unit_value_or_variable_name",
                "block_size_14_value_or_variable_name",
                "block_14_cost_per_unit_value_or_variable_name",
                "block_size_15_value_or_variable_name",
                "block_15_cost_per_unit_value_or_variable_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Used to compute energy and demand charges (or any other charges) that are structured in blocks of charges. Multiple UtilityCost:Charge:Block objects may be defined for a single tariff and they will be added together."
}
```
