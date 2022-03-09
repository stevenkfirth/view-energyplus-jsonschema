```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "minimum_opening_time": {
                    "type": "number",
                    "units": "minutes",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "minimum_closing_time": {
                    "type": "number",
                    "units": "minutes",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "thermal_comfort_low_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Enter a curve name that represents thermal comfort temperature as a function of outdoor dry-bulb temperature. Up to two curves are allowed if the performance cannot be represented by a single curve. The following two fields are used if two curves are required."
                },
                "thermal_comfort_temperature_boundary_point": {
                    "type": "number",
                    "units": "C",
                    "minimum": 0.0,
                    "default": 10.0,
                    "note": "This point is used to allow separate low and high thermal comfort temperature curves. If a single performance curve is used, leave this field blank."
                },
                "thermal_comfort_high_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Enter a curve name that represents thermal comfort temperature as a function of outdoor dry-bulb temperature. Up to two curves are allowed if the performance cannot be represented by a single curve. If a single performance curve is used, leave this field blank."
                },
                "maximum_threshold_for_persons_dissatisfied_ppd": {
                    "type": "number",
                    "units": "percent",
                    "minimum": 0.0,
                    "maximum": 100.0,
                    "default": 10.0
                },
                "occupancy_check": {
                    "type": "string",
                    "note": "If Yes, occupancy check will be performed as part of the opening probability check.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "opening_probability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "If this field is blank, the opening probability check is bypassed and opening is true."
                },
                "closing_probability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "If this field is blank, the closing probability check is bypassed and closing is true."
                }
            }
        }
    },
    "group": "AirflowNetwork",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AirflowNetworkOccupantVentilationControlNames"
        ],
        "note": "Enter the name where the advanced thermal comfort control is required."
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "minimum_opening_time": {
                "field_name": "Minimum Opening Time",
                "field_type": "n"
            },
            "minimum_closing_time": {
                "field_name": "Minimum Closing Time",
                "field_type": "n"
            },
            "thermal_comfort_low_temperature_curve_name": {
                "field_name": "Thermal Comfort Low Temperature Curve Name",
                "field_type": "a"
            },
            "thermal_comfort_temperature_boundary_point": {
                "field_name": "Thermal Comfort Temperature Boundary Point",
                "field_type": "n"
            },
            "thermal_comfort_high_temperature_curve_name": {
                "field_name": "Thermal Comfort High Temperature Curve Name",
                "field_type": "a"
            },
            "maximum_threshold_for_persons_dissatisfied_ppd": {
                "field_name": "Maximum Threshold for Persons Dissatisfied PPD",
                "field_type": "n"
            },
            "occupancy_check": {
                "field_name": "Occupancy Check",
                "field_type": "a"
            },
            "opening_probability_schedule_name": {
                "field_name": "Opening Probability Schedule Name",
                "field_type": "a"
            },
            "closing_probability_schedule_name": {
                "field_name": "Closing Probability Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "minimum_opening_time",
            "minimum_closing_time",
            "thermal_comfort_low_temperature_curve_name",
            "thermal_comfort_temperature_boundary_point",
            "thermal_comfort_high_temperature_curve_name",
            "maximum_threshold_for_persons_dissatisfied_ppd",
            "occupancy_check",
            "opening_probability_schedule_name",
            "closing_probability_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "thermal_comfort_low_temperature_curve_name",
                "thermal_comfort_high_temperature_curve_name",
                "occupancy_check",
                "opening_probability_schedule_name",
                "closing_probability_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_opening_time",
                "minimum_closing_time",
                "thermal_comfort_temperature_boundary_point",
                "maximum_threshold_for_persons_dissatisfied_ppd"
            ]
        }
    },
    "type": "object",
    "memo": "This object is used to provide advanced thermal comfort control of window opening and closing for both exterior and interior windows."
}
```
