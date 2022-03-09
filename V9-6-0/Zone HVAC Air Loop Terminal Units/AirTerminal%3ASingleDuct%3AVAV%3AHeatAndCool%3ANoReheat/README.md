```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "air_outlet_node_name": {
                    "type": "string",
                    "note": "The outlet node of the terminal unit. This is also the zone inlet node."
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "maximum_air_flow_rate": {
                    "units": "m3/s",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "zone_minimum_air_flow_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "note": "fraction of maximum air flow"
                },
                "minimum_air_flow_turndown_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This field adjusts the design minimum flow rate by multiplying it using this schedule of fraction values. This field is used with \"Zone Minimum Air Flow Fraction\". Schedule values are fractions 0.0 to 1.0. This field adjusts the minimum airflow turndown below the design minimum air flow and is intended for use with ASHRAE Standard 170. If this field is left blank, then the turndown minimum air flow fraction value is set to 1 and the model uses the fixed fraction specified in in the field \"Zone Minimum Air Flow Fraction\"."
                }
            },
            "required": [
                "air_outlet_node_name",
                "air_inlet_node_name",
                "maximum_air_flow_rate",
                "zone_minimum_air_flow_fraction"
            ]
        }
    },
    "group": "Zone HVAC Air Loop Terminal Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AirTerminalUnitNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "maximum_air_flow_rate": {
                "field_name": "Maximum Air Flow Rate",
                "field_type": "n"
            },
            "zone_minimum_air_flow_fraction": {
                "field_name": "Zone Minimum Air Flow Fraction",
                "field_type": "n"
            },
            "minimum_air_flow_turndown_schedule_name": {
                "field_name": "Minimum Air Flow Turndown Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "air_outlet_node_name",
            "air_inlet_node_name",
            "maximum_air_flow_rate",
            "zone_minimum_air_flow_fraction",
            "minimum_air_flow_turndown_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_outlet_node_name",
                "air_inlet_node_name",
                "minimum_air_flow_turndown_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_air_flow_rate",
                "zone_minimum_air_flow_fraction"
            ]
        }
    },
    "type": "object",
    "memo": "Central air system terminal unit, single duct, variable volume for both cooling and heating, with no reheat coil.",
    "min_fields": 6.0
}
```
