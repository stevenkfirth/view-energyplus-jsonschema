```
{
    "HeatExchanger:Desiccant:BalancedFlow": {
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
                    "regeneration_air_inlet_node_name": {
                        "type": "string"
                    },
                    "regeneration_air_outlet_node_name": {
                        "type": "string"
                    },
                    "process_air_inlet_node_name": {
                        "type": "string"
                    },
                    "process_air_outlet_node_name": {
                        "type": "string"
                    },
                    "heat_exchanger_performance_object_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "HeatExchanger:Desiccant:BalancedFlow:PerformanceDataType1"
                        ],
                        "default": "HeatExchanger:Desiccant:BalancedFlow:PerformanceDataType1"
                    },
                    "heat_exchanger_performance_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DesiccantHXPerfData"
                        ]
                    },
                    "economizer_lockout": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "Yes means that the heat exchanger will be locked out (off) when the economizer is operating or high humidity control is active"
                    }
                },
                "required": [
                    "regeneration_air_inlet_node_name",
                    "regeneration_air_outlet_node_name",
                    "process_air_inlet_node_name",
                    "process_air_outlet_node_name",
                    "heat_exchanger_performance_name"
                ]
            }
        },
        "group": "Heat Recovery",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AFNHeatExchangerNames",
                "HXAirToAirNames",
                "HXDesiccantBalanced",
                "validBranchEquipmentNames",
                "validOASysEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validOASysEquipmentTypes"
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
                "regeneration_air_inlet_node_name": {
                    "field_name": "Regeneration Air Inlet Node Name",
                    "field_type": "a"
                },
                "regeneration_air_outlet_node_name": {
                    "field_name": "Regeneration Air Outlet Node Name",
                    "field_type": "a"
                },
                "process_air_inlet_node_name": {
                    "field_name": "Process Air Inlet Node Name",
                    "field_type": "a"
                },
                "process_air_outlet_node_name": {
                    "field_name": "Process Air Outlet Node Name",
                    "field_type": "a"
                },
                "heat_exchanger_performance_object_type": {
                    "field_name": "Heat Exchanger Performance Object Type",
                    "field_type": "a"
                },
                "heat_exchanger_performance_name": {
                    "field_name": "Heat Exchanger Performance Name",
                    "field_type": "a"
                },
                "economizer_lockout": {
                    "field_name": "Economizer Lockout",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "regeneration_air_inlet_node_name",
                "regeneration_air_outlet_node_name",
                "process_air_inlet_node_name",
                "process_air_outlet_node_name",
                "heat_exchanger_performance_object_type",
                "heat_exchanger_performance_name",
                "economizer_lockout"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "regeneration_air_inlet_node_name",
                    "regeneration_air_outlet_node_name",
                    "process_air_inlet_node_name",
                    "process_air_outlet_node_name",
                    "heat_exchanger_performance_object_type",
                    "heat_exchanger_performance_name",
                    "economizer_lockout"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object models a balanced desiccant heat exchanger. The heat exchanger transfers both sensible and latent energy between the process and regeneration air streams. The air flow rate and face velocity are assumed to be the same on both the process and regeneration sides of the heat exchanger.",
        "min_fields": 8.0
    }
}
```
