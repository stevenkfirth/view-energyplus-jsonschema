```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "digits_after_decimal": {
                    "type": "number",
                    "default": 2.0,
                    "minimum": 0.0,
                    "maximum": 10.0
                },
                "variable_details": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "variable_or_meter_name": {
                                "type": "string",
                                "data_type": "external_list",
                                "external_list": [
                                    "autoRDDvariableMeter"
                                ],
                                "note": "The name of an output variable or  meter that is available in the RDD file."
                            },
                            "aggregation_type_for_variable_or_meter": {
                                "type": "string",
                                "enum": [
                                    "HoursNegative",
                                    "HoursNonNegative",
                                    "HoursNonPositive",
                                    "HoursNonZero",
                                    "HoursPositive",
                                    "HoursZero",
                                    "Maximum",
                                    "MaximumDuringHoursShown",
                                    "Minimum",
                                    "MinimumDuringHoursShown",
                                    "SumOrAverage",
                                    "SumOrAverageDuringHoursShown",
                                    "ValueWhenMaximumOrMinimum"
                                ],
                                "note": "The method of aggregation for the selected variable or meter. SumOrAverage adds up the values for every timestep in the month if the variable is a sum variable. If the variable is an average variable it reports the average value. This is probably the most common Aggregation Type option to choose. Maximum and Minimum find the maximum and minimum value for the month and report it along with the time that it first occurred. When Maximum or Minimum are selected a column is automatically shown in the output report for the time that it occurred. When Maximum or Minimum are used with an average variable the value is divided by the length of the timestep. ValueWhenMaxMin looks at the previous variable in the report that sets a maximum or minimum and displays the value of the current variable at that same timestep. Order of the variables in the report is important when using ValueWhenMaxMin. This can be used when an outdoor temperature should be reported for the time of the maximum cooling load. HoursNonZero adds up the elapsed time during the month that this variable is non-zero and would be appropriate to determine the number of hour that a fan operates. HoursZero - The HoursZero option adds up the elapsed time during the month that this variable has a zero value and would be appropriate to determine the number of hour that a fan does not operate. HoursPositive - The HoursPositive option adds up the elapsed time during the month that this variable has a positive value. Hours with a zero value are not included. HoursNonPositive - The HoursNonPositive option adds up the elapsed time during the month that this variable has non-positive value. Hours with a negative value and hours with a zero value are all included. HoursNegative - The HoursNegative option adds up the elapsed time during the month that this variable has a negative value. Hours with a zero value are not included. HoursNonNegative - The HoursNonNegative option adds up the elapsed time during the month that this variable has non-negative value. Hours with a positive value and hours with a zero value are all included. SumOrAverageDuringHoursShown - Provides the sum or average of the named variable when during the hours that the previous variable displayed with any of the Aggregation Types starting with \"Hours\". For \"sum\" type variables adds up the values for each timestep and reports the sum of the value monthly during the hours reported on the previous variable. For \"average\" type variables, the value shown will be the average for the month during the hours reported on the previous variable. Order of the variables in the report is important when using this Aggregation Type. MaximumDuringHoursShown - Reports the maximum value and the time that the maximum value occurred but only during the hours reported with the previous \"hours-\" Aggregation Type. When the Maximum option is used with an average variable the value is divided by the length of the timestep. Order of the variables in the report is important when using this Aggregation Type. MinimumDuringHoursShown - Reports the minimum value and the time that the minimum value occurred but only during the hours reported with the previous \"hours-\" Aggregation Type. When the Minimum option is used with an average variable the value is divided by the length of the timestep. Order of the variables in the report is important when using this Aggregation Type."
                            }
                        },
                        "type": "object"
                    }
                }
            }
        }
    },
    "group": "Output Reporting",
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
            "digits_after_decimal": {
                "field_name": "Digits After Decimal",
                "field_type": "n"
            },
            "variable_or_meter_name": {
                "field_name": "Variable or Meter Name",
                "field_type": "a"
            },
            "aggregation_type_for_variable_or_meter": {
                "field_name": "Aggregation Type for Variable or Meter",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "digits_after_decimal"
        ],
        "alphas": {
            "fields": [
                "name"
            ],
            "extensions": [
                "variable_or_meter_name",
                "aggregation_type_for_variable_or_meter"
            ]
        },
        "numerics": {
            "fields": [
                "digits_after_decimal"
            ]
        },
        "extensibles": [
            "variable_or_meter_name",
            "aggregation_type_for_variable_or_meter"
        ],
        "extension": "variable_details"
    },
    "type": "object",
    "memo": "Provides a generic method of setting up tables of monthly results. The report has multiple columns that are each defined using a repeated group of fields for any number of columns. A single Output:Table:Monthly object often produces multiple tables in the output. A table is produced for every instance of a particular output variable. For example, a table defined with zone variables will be produced once for every zone.",
    "extensible_size": 2.0
}
```
