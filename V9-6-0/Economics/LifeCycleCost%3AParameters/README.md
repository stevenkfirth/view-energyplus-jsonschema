```
{
    "LifeCycleCost:Parameters": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "discounting_convention": {
                        "type": "string",
                        "enum": [
                            "",
                            "BeginningOfYear",
                            "EndOfYear",
                            "MidYear"
                        ],
                        "default": "EndOfYear",
                        "note": "The field specifies if the discounting of future costs should be computed as occurring at the end of each year or the middle of each year or the beginning of each year. The most common discounting convention uses the end of each year."
                    },
                    "inflation_approach": {
                        "type": "string",
                        "enum": [
                            "",
                            "ConstantDollar",
                            "CurrentDollar"
                        ],
                        "default": "ConstantDollar",
                        "note": "This field is used to determine if the analysis should use constant dollars or current dollars which is related to how inflation is treated. If ConstantDollar is selected then the Real Discount Rate input is used and it excludes the rate of inflation. If CurrentDollar is selected then the Nominal Discount Rate input is used and it includes the rate of inflation."
                    },
                    "real_discount_rate": {
                        "type": "number",
                        "note": "Enter the real discount rate as a decimal. For a 3% rate enter the value 0.03. This input is used when the Inflation Approach is ConstantDollar. The real discount rate reflects the interest rates needed to make current and future expenditures have comparable equivalent values when general inflation is ignored. When Inflation Approach is set to CurrentDollar this input is ignored."
                    },
                    "nominal_discount_rate": {
                        "type": "number",
                        "note": "Enter the nominal discount rate as a decimal. For a 5% rate enter the value 0.05. This input is used when the Inflation Approach is CurrentDollar. The real discount rate reflects the interest rates needed to make current and future expenditures have comparable equivalent values when general inflation is included. When Inflation Approach is set to ConstantDollar this input is ignored."
                    },
                    "inflation": {
                        "type": "number",
                        "note": "Enter the rate of inflation for general goods and services as a decimal. For a 2% rate enter the value 0.02."
                    },
                    "base_date_month": {
                        "type": "string",
                        "enum": [
                            "",
                            "April",
                            "August",
                            "December",
                            "February",
                            "January",
                            "July",
                            "June",
                            "March",
                            "May",
                            "November",
                            "October",
                            "September"
                        ],
                        "default": "January",
                        "note": "Enter the month that is the beginning of study period also known as the beginning of the base period."
                    },
                    "base_date_year": {
                        "type": "number",
                        "minimum": 1900.0,
                        "maximum": 2100.0,
                        "note": "Enter the four digit year that is the beginning of study period such as 2010. The study period is also known as the base period."
                    },
                    "service_date_month": {
                        "type": "string",
                        "enum": [
                            "",
                            "April",
                            "August",
                            "December",
                            "February",
                            "January",
                            "July",
                            "June",
                            "March",
                            "May",
                            "November",
                            "October",
                            "September"
                        ],
                        "default": "January",
                        "note": "Enter the month that is the beginning of building occupancy. Energy costs computed by EnergyPlus are assumed to occur during the year following the service date. The service date must be the same or later than the Base Date. This field could also be referred to as part of beneficial occupancy date."
                    },
                    "service_date_year": {
                        "type": "number",
                        "minimum": 1900.0,
                        "maximum": 2100.0,
                        "note": "Enter the four digit year that is the beginning of occupancy such as 2010."
                    },
                    "length_of_study_period_in_years": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 100.0,
                        "note": "Enter the number of years of the study period. It is the number of years that the study continues based on the start at the base date. The default value is 25 years. Only integers may be used indicating whole years."
                    },
                    "tax_rate": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the overall marginal tax rate for the project costs. This does not include energy or water taxes. The tax rate entered should be based on the marginal tax rate for the entity and not the average tax rate. Enter the tax rate results in present value calculations after taxes. Most analyses do not factor in the impact of taxes and assume that all options under consideration have roughly the same tax impact. Due to this many times the tax rate can be left to default to zero and the present value results before taxes are used to make decisions. The value should be entered as a decimal value. For 15% enter 0.15. For an analysis that does not include tax impacts enter 0.0."
                    },
                    "depreciation_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "ModifiedAcceleratedCostRecoverySystem-10year",
                            "ModifiedAcceleratedCostRecoverySystem-15year",
                            "ModifiedAcceleratedCostRecoverySystem-20year",
                            "ModifiedAcceleratedCostRecoverySystem-3year",
                            "ModifiedAcceleratedCostRecoverySystem-5year",
                            "ModifiedAcceleratedCostRecoverySystem-7year",
                            "None",
                            "StraightLine-27year",
                            "StraightLine-31year",
                            "StraightLine-39year",
                            "StraightLine-40year"
                        ],
                        "default": "None",
                        "note": "For an analysis that includes income tax impacts this entry describes how capital costs are depreciated. Only one depreciation method may be used for an analysis and is applied to all capital expenditures."
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
                "discounting_convention": {
                    "field_name": "Discounting Convention",
                    "field_type": "a"
                },
                "inflation_approach": {
                    "field_name": "Inflation Approach",
                    "field_type": "a"
                },
                "real_discount_rate": {
                    "field_name": "Real Discount Rate",
                    "field_type": "n"
                },
                "nominal_discount_rate": {
                    "field_name": "Nominal Discount Rate",
                    "field_type": "n"
                },
                "inflation": {
                    "field_name": "Inflation",
                    "field_type": "n"
                },
                "base_date_month": {
                    "field_name": "Base Date Month",
                    "field_type": "a"
                },
                "base_date_year": {
                    "field_name": "Base Date Year",
                    "field_type": "n"
                },
                "service_date_month": {
                    "field_name": "Service Date Month",
                    "field_type": "a"
                },
                "service_date_year": {
                    "field_name": "Service Date Year",
                    "field_type": "n"
                },
                "length_of_study_period_in_years": {
                    "field_name": "Length of Study Period in Years",
                    "field_type": "n"
                },
                "tax_rate": {
                    "field_name": "Tax rate",
                    "field_type": "n"
                },
                "depreciation_method": {
                    "field_name": "Depreciation Method",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "discounting_convention",
                "inflation_approach",
                "real_discount_rate",
                "nominal_discount_rate",
                "inflation",
                "base_date_month",
                "base_date_year",
                "service_date_month",
                "service_date_year",
                "length_of_study_period_in_years",
                "tax_rate",
                "depreciation_method"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "discounting_convention",
                    "inflation_approach",
                    "base_date_month",
                    "service_date_month",
                    "depreciation_method"
                ]
            },
            "numerics": {
                "fields": [
                    "real_discount_rate",
                    "nominal_discount_rate",
                    "inflation",
                    "base_date_year",
                    "service_date_year",
                    "length_of_study_period_in_years",
                    "tax_rate"
                ]
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Provides inputs related to the overall life-cycle analysis. It establishes many of the assumptions used in computing the present value. It is important that when comparing the results of multiple simulations that the fields in the LifeCycleCost:Parameters objects are the same for all the simulations. When this object is present the tabular report file will contain the Life-Cycle Cost Report.",
        "min_fields": 11.0
    }
}
```
