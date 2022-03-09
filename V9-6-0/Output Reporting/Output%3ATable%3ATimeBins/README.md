```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "key_value": {
                    "type": "string",
                    "default": "*",
                    "note": "use '*' (without quotes) to apply this variable to all keys"
                },
                "variable_name": {
                    "type": "string",
                    "data_type": "external_list",
                    "external_list": [
                        "autoRDDvariableMeter"
                    ]
                },
                "interval_start": {
                    "type": "number",
                    "note": "The lowest value for the intervals being binned into.",
                    "unitsBasedOnField": "variable_type"
                },
                "interval_size": {
                    "type": "number",
                    "note": "The size of the bins starting with Interval start.",
                    "unitsBasedOnField": "variable_type"
                },
                "interval_count": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 20.0,
                    "note": "The number of bins used. The number of hours below the start of the Lowest bin and above the value of the last bin are also shown."
                },
                "schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Optional schedule name. Binning is performed for non-zero hours. Binning always performed if left blank."
                },
                "variable_type": {
                    "type": "string",
                    "enum": [
                        "Energy",
                        "Power",
                        "Temperature",
                        "VolumetricFlow"
                    ],
                    "note": "Optional input on the type of units for the variable used by other fields in the object."
                }
            },
            "required": [
                "variable_name"
            ]
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "key_value": {
                "field_name": "Key Value",
                "field_type": "a"
            },
            "variable_name": {
                "field_name": "Variable Name",
                "field_type": "a"
            },
            "interval_start": {
                "field_name": "Interval Start",
                "field_type": "n"
            },
            "interval_size": {
                "field_name": "Interval Size",
                "field_type": "n"
            },
            "interval_count": {
                "field_name": "Interval Count",
                "field_type": "n"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "variable_type": {
                "field_name": "Variable Type",
                "field_type": "a"
            }
        },
        "fields": [
            "key_value",
            "variable_name",
            "interval_start",
            "interval_size",
            "interval_count",
            "schedule_name",
            "variable_type"
        ],
        "alphas": {
            "fields": [
                "key_value",
                "variable_name",
                "schedule_name",
                "variable_type"
            ]
        },
        "numerics": {
            "fields": [
                "interval_start",
                "interval_size",
                "interval_count"
            ]
        }
    },
    "type": "object",
    "memo": "Produces a bin report in the table output file which shows the amount of time in hours that occurs in different bins for a single specific output variable or meter. Two different types of binning are reported: by month and by hour of the day.",
    "min_fields": 5.0
}
```
