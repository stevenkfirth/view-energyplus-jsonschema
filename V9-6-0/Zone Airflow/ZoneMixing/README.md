```
{
    "ZoneMixing": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "design_flow_rate_calculation_method": {
                        "type": "string",
                        "note": "The entered calculation method is used to create the maximum amount of ventilation for this set of attributes Choices: Flow/Zone => Design Flow Rate -- simply enter Design Flow Rate Flow/Area => Flow Rate per Zone Floor Area - Value * Floor Area (zone) = Design Flow Rate Flow/Person => Flow Rate per Person - Value * #people = Design Flow Rate AirChanges/Hour => Air Changes per Hour - Value * Floor Volume (zone) adjusted for m3/s = Design Volume Flow Rate \"Vdesign\" in Equation is the result.",
                        "enum": [
                            "",
                            "AirChanges/Hour",
                            "Flow/Area",
                            "Flow/Person",
                            "Flow/Zone"
                        ],
                        "default": "Flow/Zone"
                    },
                    "design_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "flow_rate_per_zone_floor_area": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m3/s-m2"
                    },
                    "flow_rate_per_person": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m3/s-person"
                    },
                    "air_changes_per_hour": {
                        "type": "number",
                        "units": "1/hr",
                        "minimum": 0.0
                    },
                    "source_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "delta_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "default": 0.0,
                        "note": "This field contains the constant temperature differential between source and receiving zones below which mixing is shutoff."
                    },
                    "delta_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the temperature differential between source and receiving zones versus time below which mixing is shutoff."
                    },
                    "minimum_zone_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the zone dry-bulb temperature versus time below which mixing is shutoff."
                    },
                    "maximum_zone_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the zone dry-bulb temperature versus time above which mixing is shutoff."
                    },
                    "minimum_source_zone_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the source zone dry-bulb temperature versus time below which mixing is shutoff."
                    },
                    "maximum_source_zone_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the source zone dry-bulb temperature versus time above which mixing is shutoff."
                    },
                    "minimum_outdoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the outdoor temperature versus time below which mixing is shutoff."
                    },
                    "maximum_outdoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the outdoor temperature versus time above which mixing is shutoff."
                    }
                },
                "required": [
                    "zone_name",
                    "schedule_name",
                    "source_zone_name"
                ]
            }
        },
        "group": "Zone Airflow",
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
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                },
                "design_flow_rate_calculation_method": {
                    "field_name": "Design Flow Rate Calculation Method",
                    "field_type": "a"
                },
                "design_flow_rate": {
                    "field_name": "Design Flow Rate",
                    "field_type": "n"
                },
                "flow_rate_per_zone_floor_area": {
                    "field_name": "Flow Rate per Zone Floor Area",
                    "field_type": "n"
                },
                "flow_rate_per_person": {
                    "field_name": "Flow Rate per Person",
                    "field_type": "n"
                },
                "air_changes_per_hour": {
                    "field_name": "Air Changes per Hour",
                    "field_type": "n"
                },
                "source_zone_name": {
                    "field_name": "Source Zone Name",
                    "field_type": "a"
                },
                "delta_temperature": {
                    "field_name": "Delta Temperature",
                    "field_type": "n"
                },
                "delta_temperature_schedule_name": {
                    "field_name": "Delta Temperature Schedule Name",
                    "field_type": "a"
                },
                "minimum_zone_temperature_schedule_name": {
                    "field_name": "Minimum Zone Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_zone_temperature_schedule_name": {
                    "field_name": "Maximum Zone Temperature Schedule Name",
                    "field_type": "a"
                },
                "minimum_source_zone_temperature_schedule_name": {
                    "field_name": "Minimum Source Zone Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_source_zone_temperature_schedule_name": {
                    "field_name": "Maximum Source Zone Temperature Schedule Name",
                    "field_type": "a"
                },
                "minimum_outdoor_temperature_schedule_name": {
                    "field_name": "Minimum Outdoor Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_outdoor_temperature_schedule_name": {
                    "field_name": "Maximum Outdoor Temperature Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "schedule_name",
                "design_flow_rate_calculation_method",
                "design_flow_rate",
                "flow_rate_per_zone_floor_area",
                "flow_rate_per_person",
                "air_changes_per_hour",
                "source_zone_name",
                "delta_temperature",
                "delta_temperature_schedule_name",
                "minimum_zone_temperature_schedule_name",
                "maximum_zone_temperature_schedule_name",
                "minimum_source_zone_temperature_schedule_name",
                "maximum_source_zone_temperature_schedule_name",
                "minimum_outdoor_temperature_schedule_name",
                "maximum_outdoor_temperature_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "schedule_name",
                    "design_flow_rate_calculation_method",
                    "source_zone_name",
                    "delta_temperature_schedule_name",
                    "minimum_zone_temperature_schedule_name",
                    "maximum_zone_temperature_schedule_name",
                    "minimum_source_zone_temperature_schedule_name",
                    "maximum_source_zone_temperature_schedule_name",
                    "minimum_outdoor_temperature_schedule_name",
                    "maximum_outdoor_temperature_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "design_flow_rate",
                    "flow_rate_per_zone_floor_area",
                    "flow_rate_per_person",
                    "air_changes_per_hour",
                    "delta_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "ZoneMixing is a simple air exchange from one zone to another. Note that this statement only affects the energy balance of the \"receiving\" zone and will not produce any effect on the \"source\" zone. Mixing statements can be complementary and include multiple zones, but the balancing of flows between zones is left to the user's discretion.",
        "min_fields": 9.0
    }
}
```
