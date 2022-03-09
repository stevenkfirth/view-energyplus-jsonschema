```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "filter": {
                    "type": "string",
                    "note": "An optional text string that is compared to the names of the objects referenced by the variables and if they match are included in the table. A footnote will appear that indicates that the objects shown may not be all the objects that of that type that occur in the file."
                },
                "schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Optional schedule name. If left blank, aggregation is performed for all hours simulated. If a schedule is specified, aggregation is performed for non-zero hours in the schedule."
                },
                "variable_details": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "variable_or_meter_or_ems_variable_or_field_name": {
                                "type": "string",
                                "data_type": "external_list",
                                "external_list": [
                                    "autoRDDvariableMeter"
                                ],
                                "note": "contain the name of a variable (see Output:Variable and eplusout.rdd), meter (see Output:Meter and eplusout.mdd), or EMS Internal Variable Name or IDF Object Field name. This value is shown using the aggregation method specified."
                            },
                            "aggregation_type_for_variable_or_meter": {
                                "type": "string",
                                "enum": [
                                    "HourInTenBinsMinToMax",
                                    "HourInTenBinsMinToZero",
                                    "HourInTenBinsZeroToMax",
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
                                "note": "The method of aggregation for the selected variable or meter. SumOrAverage adds up the values for every timestep in the month if the variable is a sum variable. If the variable is an average variable it reports the average value. This is probably the most common Aggregation Type option to choose. Maximum and Minimum find the maximum and minimum value for the month and report it along with the time that it first occurred. When Maximum or Minimum are selected a column is automatically shown in the output report for the time that it occurred. When Maximum or Minimum are used with an average variable the value is divided by the length of the timestep. ValueWhenMaxMin looks at the previous variable in the report that sets a maximum or minimum and displays the value of the current variable at that same timestep. Order of the variables in the report is important when using ValueWhenMaxMin. This can be used when an outdoor temperature should be reported for the time of the maximum cooling load. HoursNonZero adds up the elapsed time during the month that this variable is non-zero and would be appropriate to determine the number of hour that a fan operates. HoursZero - The HoursZero option adds up the elapsed time during the month that this variable has a zero value and would be appropriate to determine the number of hour that a fan does not operate. HoursPositive - The HoursPositive option adds up the elapsed time during the month that this variable has a positive value. Hours with a zero value are not included. HoursNonPositive - The HoursNonPositive option adds up the elapsed time during the month that this variable has non-positive value. Hours with a negative value and hours with a zero value are all included. HoursNegative - The HoursNegative option adds up the elapsed time during the month that this variable has a negative value. Hours with a zero value are not included. HoursNonNegative - The HoursNonNegative option adds up the elapsed time during the month that this variable has non-negative value. Hours with a positive value and hours with a zero value are all included. HourInTenBinsMinToMax - Creates 10 columns for the specified variable and shows the number of hours in each of 10 bins based on the minimum and maximum value. The bin sizes will be rounded up to the next most signficant digit value. HourInTenBinsZeroToMax - Creates 11 columns for the specified variable and shows the number of hours in each of 10 bins from zero to the maximum value and a bin for hours below zero. The bin sizes will be rounded up to the next most significant digit value. HourInTenBinsMinToZero - Creates 11 columns for the specified variable and shows the number of hours in each of 10 bins from zero to the minimum value and a bin for hours above zero. The bin sizes will be rounded up to the next most significant digit value. SumOrAverageDuringHoursShown - Provides the sum or average of the named variable when during the hours that the previous variable displayed with any of the Aggregation Types starting with \"Hours\". For \"sum\" type variables adds up the values for each timestep and reports the sum of the value monthly during the hours reported on the previous variable. For \"average\" type variables, the value shown will be the average for the month during the hours reported on the previous variable. Order of the variables in the report is important when using this Aggregation Type. MaximumDuringHoursShown - Reports the maximum value and the time that the maximum value occurred but only during the hours reported with the previous \"hours-\" Aggregation Type. When the Maximum option is used with an average variable the value is divided by the length of the timestep. Order of the variables in the report is important when using this Aggregation Type. MinimumDuringHoursShown - Reports the minimum value and the time that the minimum value occurred but only during the hours reported with the previous \"hours-\" Aggregation Type. When the Minimum option is used with an average variable the value is divided by the length of the timestep. Order of the variables in the report is important when using this Aggregation Type."
                            },
                            "digits_after_decimal": {
                                "type": "number",
                                "default": 2.0,
                                "minimum": 0.0,
                                "maximum": 10.0
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
            "filter": {
                "field_name": "Filter",
                "field_type": "a"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "variable_or_meter_or_ems_variable_or_field_name": {
                "field_name": "Variable or Meter or EMS Variable or Field Name",
                "field_type": "a"
            },
            "aggregation_type_for_variable_or_meter": {
                "field_name": "Aggregation Type for Variable or Meter",
                "field_type": "a"
            },
            "digits_after_decimal": {
                "field_name": "Digits After Decimal",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "filter",
            "schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "filter",
                "schedule_name"
            ],
            "extensions": [
                "variable_or_meter_or_ems_variable_or_field_name",
                "aggregation_type_for_variable_or_meter"
            ]
        },
        "numerics": {
            "fields": [],
            "extensions": [
                "digits_after_decimal"
            ]
        },
        "extensibles": [
            "variable_or_meter_or_ems_variable_or_field_name",
            "aggregation_type_for_variable_or_meter",
            "digits_after_decimal"
        ],
        "extension": "variable_details"
    },
    "type": "object",
    "memo": "Provides a generic method of setting up tables of annual results with one row per object. The report has multiple columns that are each defined using a repeated group of fields for any number of columns. A single Output:Table:Annual produces a single table in the output.",
    "extensible_size": 3.0
}
```
