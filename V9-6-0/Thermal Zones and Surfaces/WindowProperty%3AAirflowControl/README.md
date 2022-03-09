```
{
    "WindowProperty:AirflowControl": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "airflow_source": {
                        "type": "string",
                        "enum": [
                            "",
                            "IndoorAir",
                            "OutdoorAir"
                        ],
                        "default": "IndoorAir"
                    },
                    "airflow_destination": {
                        "type": "string",
                        "note": "If ReturnAir is selected, the name of the Return Air Node may be specified below.",
                        "enum": [
                            "",
                            "IndoorAir",
                            "OutdoorAir",
                            "ReturnAir"
                        ],
                        "default": "OutdoorAir"
                    },
                    "maximum_flow_rate": {
                        "type": "number",
                        "units": "m3/s-m",
                        "note": "Above is m3/s per m of glazing width",
                        "ip-units": "ft3/min-ft",
                        "default": 0.0,
                        "minimum": 0.0
                    },
                    "airflow_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "AlwaysOff",
                            "AlwaysOnAtMaximumFlow",
                            "ScheduledOnly"
                        ],
                        "note": "ScheduledOnly requires that Airflow Has Multiplier Schedule Name = Yes and that Airflow Multiplier Schedule Name is specified.",
                        "default": "AlwaysOnAtMaximumFlow"
                    },
                    "airflow_is_scheduled": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "If Yes, then Airflow Multiplier Schedule Name must be specified"
                    },
                    "airflow_multiplier_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Required if Airflow Is Scheduled = Yes. Schedule values are 0.0 or 1.0 and multiply Maximum Air Flow."
                    },
                    "airflow_return_air_node_name": {
                        "type": "string",
                        "note": "Name of the return air node for this airflow window if the Airflow Destination is ReturnAir. If left blank, defaults to the first return air node for the zone of the window surface."
                    }
                }
            }
        },
        "group": "Thermal Zones and Surfaces",
        "name": {
            "type": "string",
            "is_required": true,
            "data_type": "object_list",
            "object_list": [
                "SubSurfNames"
            ],
            "note": "Name must be that of an exterior window with two or three glass layers."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "airflow_source": {
                    "field_name": "Airflow Source",
                    "field_type": "a"
                },
                "airflow_destination": {
                    "field_name": "Airflow Destination",
                    "field_type": "a"
                },
                "maximum_flow_rate": {
                    "field_name": "Maximum Flow Rate",
                    "field_type": "n"
                },
                "airflow_control_type": {
                    "field_name": "Airflow Control Type",
                    "field_type": "a"
                },
                "airflow_is_scheduled": {
                    "field_name": "Airflow Is Scheduled",
                    "field_type": "a"
                },
                "airflow_multiplier_schedule_name": {
                    "field_name": "Airflow Multiplier Schedule Name",
                    "field_type": "a"
                },
                "airflow_return_air_node_name": {
                    "field_name": "Airflow Return Air Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "airflow_source",
                "airflow_destination",
                "maximum_flow_rate",
                "airflow_control_type",
                "airflow_is_scheduled",
                "airflow_multiplier_schedule_name",
                "airflow_return_air_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "airflow_source",
                    "airflow_destination",
                    "airflow_control_type",
                    "airflow_is_scheduled",
                    "airflow_multiplier_schedule_name",
                    "airflow_return_air_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_flow_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Used to control forced airflow through a gap between glass layers",
        "min_fields": 7.0
    }
}
```
