```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "tolerance_for_time_heating_setpoint_not_met": {
                    "type": "number",
                    "note": "If the zone temperature is below the heating setpoint by more than this value, the following output variables will increment as appropriate Zone Heating Setpoint Not Met Time Zone Heating Setpoint Not Met While Occupied Time This also impacts table report \"Annual Building Utility Performance Summary\" subtable \"Comfort and Setpoint Not Met Summary\"",
                    "units": "deltaC",
                    "default": 0.2,
                    "minimum": 0.0,
                    "maximum": 10.0
                },
                "tolerance_for_time_cooling_setpoint_not_met": {
                    "type": "number",
                    "note": "If the zone temperature is above the cooling setpoint by more than this value, the following output variables will increment as appropriate Zone Cooling Setpoint Not Met Time Zone Cooling Setpoint Not Met While Occupied Time This also impacts table report \"Annual Building Utility Performance Summary\" subtable \"Comfort and Setpoint Not Met Summary\"",
                    "units": "deltaC",
                    "default": 0.2,
                    "minimum": 0.0,
                    "maximum": 10.0
                }
            }
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "tolerance_for_time_heating_setpoint_not_met": {
                "field_name": "Tolerance for Time Heating Setpoint Not Met",
                "field_type": "n"
            },
            "tolerance_for_time_cooling_setpoint_not_met": {
                "field_name": "Tolerance for Time Cooling Setpoint Not Met",
                "field_type": "n"
            }
        },
        "fields": [
            "tolerance_for_time_heating_setpoint_not_met",
            "tolerance_for_time_cooling_setpoint_not_met"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "tolerance_for_time_heating_setpoint_not_met",
                "tolerance_for_time_cooling_setpoint_not_met"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Calculations of the time that setpoints are not met use a tolerance of 0.2C. This object allows changing the tolerance used to determine when setpoints are being met."
}
```
