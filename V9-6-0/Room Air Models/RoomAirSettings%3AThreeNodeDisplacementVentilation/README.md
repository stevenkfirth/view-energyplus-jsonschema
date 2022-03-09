```
{
    "RoomAirSettings:ThreeNodeDisplacementVentilation": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "note": "Name of Zone being described. Any existing zone name",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "gain_distribution_schedule_name": {
                        "type": "string",
                        "note": "Distribution of the convective heat gains between the occupied and mixed zones. 0<= Accepted Value <= 1. In the DV model 1 means all convective gains in the lower layer.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "number_of_plumes_per_occupant": {
                        "type": "number",
                        "note": "Used only in the UCSD displacement ventilation model. Effective number of separate plumes per occupant in the occupied zone. Plumes that merge together in the occupied zone count as one.",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "thermostat_height": {
                        "type": "number",
                        "note": "Height of thermostat/temperature control sensor above floor",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 1.1
                    },
                    "comfort_height": {
                        "type": "number",
                        "note": "Height at which air temperature is calculated for comfort purposes",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 1.1
                    },
                    "temperature_difference_threshold_for_reporting": {
                        "type": "number",
                        "note": "Minimum temperature difference between predicted upper and lower layer temperatures above which DV auxiliary outputs are calculated. These outputs are 'DV Transition Height', 'DV Fraction Min Recommended Flow Rate' 'DV Average Temp Gradient' and 'DV Maximum Temp Gradient'. They are set to negative values when the temperature difference is less than the threshold and the output 'DV Zone Is Mixed' is set to 1",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 0.4
                    }
                },
                "required": [
                    "zone_name",
                    "gain_distribution_schedule_name"
                ]
            }
        },
        "group": "Room Air Models",
        "legacy_idd": {
            "field_info": {
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "gain_distribution_schedule_name": {
                    "field_name": "Gain Distribution Schedule Name",
                    "field_type": "a"
                },
                "number_of_plumes_per_occupant": {
                    "field_name": "Number of Plumes per Occupant",
                    "field_type": "n"
                },
                "thermostat_height": {
                    "field_name": "Thermostat Height",
                    "field_type": "n"
                },
                "comfort_height": {
                    "field_name": "Comfort Height",
                    "field_type": "n"
                },
                "temperature_difference_threshold_for_reporting": {
                    "field_name": "Temperature Difference Threshold for Reporting",
                    "field_type": "n"
                }
            },
            "fields": [
                "zone_name",
                "gain_distribution_schedule_name",
                "number_of_plumes_per_occupant",
                "thermostat_height",
                "comfort_height",
                "temperature_difference_threshold_for_reporting"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "gain_distribution_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_plumes_per_occupant",
                    "thermostat_height",
                    "comfort_height",
                    "temperature_difference_threshold_for_reporting"
                ]
            }
        },
        "type": "object",
        "memo": "The UCSD model for Displacement Ventilation",
        "min_fields": 6.0
    }
}
```
