```
{
    "LoadProfile:Plant": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "inlet_node_name": {
                        "type": "string"
                    },
                    "outlet_node_name": {
                        "type": "string"
                    },
                    "load_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values are load in [W]"
                    },
                    "peak_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min"
                    },
                    "flow_rate_fraction_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "inlet_node_name",
                    "outlet_node_name",
                    "load_schedule_name",
                    "peak_flow_rate",
                    "flow_rate_fraction_schedule_name"
                ]
            }
        },
        "group": "Non-Zone Equipment",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "inlet_node_name": {
                    "field_name": "Inlet Node Name",
                    "field_type": "a"
                },
                "outlet_node_name": {
                    "field_name": "Outlet Node Name",
                    "field_type": "a"
                },
                "load_schedule_name": {
                    "field_name": "Load Schedule Name",
                    "field_type": "a"
                },
                "peak_flow_rate": {
                    "field_name": "Peak Flow Rate",
                    "field_type": "n"
                },
                "flow_rate_fraction_schedule_name": {
                    "field_name": "Flow Rate Fraction Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "inlet_node_name",
                "outlet_node_name",
                "load_schedule_name",
                "peak_flow_rate",
                "flow_rate_fraction_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "inlet_node_name",
                    "outlet_node_name",
                    "load_schedule_name",
                    "flow_rate_fraction_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "peak_flow_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Used to simulate a scheduled plant loop demand profile. Load and flow rate are specified using schedules. Positive values are heating loads, and negative values are cooling loads. The actual load met is dependent on the performance of the supply loop components."
    }
}
```
