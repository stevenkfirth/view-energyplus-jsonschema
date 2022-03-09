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
                "flow_arrangement_type": {
                    "type": "string",
                    "enum": [
                        "CounterFlow",
                        "CrossFlowBothUnmixed",
                        "ParallelFlow"
                    ]
                },
                "economizer_lockout": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes",
                    "note": "Yes means that the heat exchanger will be locked out (off) when the economizer is operating or high humidity control is active"
                },
                "ratio_of_supply_to_secondary_ha_values": {
                    "type": "number",
                    "note": "Ratio of h*A for supply side to h*A for exhaust side",
                    "minimum": 0.0
                },
                "nominal_supply_air_flow_rate": {
                    "units": "m3/s",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
                },
                "nominal_supply_air_inlet_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "nominal_supply_air_outlet_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "nominal_secondary_air_flow_rate": {
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
                "nominal_secondary_air_inlet_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "nominal_electric_power": {
                    "type": "number",
                    "units": "W",
                    "ip-units": "W"
                },
                "supply_air_inlet_node_name": {
                    "type": "string"
                },
                "supply_air_outlet_node_name": {
                    "type": "string"
                },
                "secondary_air_inlet_node_name": {
                    "type": "string"
                },
                "secondary_air_outlet_node_name": {
                    "type": "string"
                }
            },
            "required": [
                "nominal_supply_air_inlet_temperature",
                "nominal_supply_air_outlet_temperature",
                "nominal_secondary_air_flow_rate",
                "nominal_secondary_air_inlet_temperature",
                "supply_air_inlet_node_name",
                "supply_air_outlet_node_name",
                "secondary_air_inlet_node_name",
                "secondary_air_outlet_node_name"
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
            "ZoneEquipmentNames",
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
            "flow_arrangement_type": {
                "field_name": "Flow Arrangement Type",
                "field_type": "a"
            },
            "economizer_lockout": {
                "field_name": "Economizer Lockout",
                "field_type": "a"
            },
            "ratio_of_supply_to_secondary_ha_values": {
                "field_name": "Ratio of Supply to Secondary hA Values",
                "field_type": "n"
            },
            "nominal_supply_air_flow_rate": {
                "field_name": "Nominal Supply Air Flow Rate",
                "field_type": "n"
            },
            "nominal_supply_air_inlet_temperature": {
                "field_name": "Nominal Supply Air Inlet Temperature",
                "field_type": "n"
            },
            "nominal_supply_air_outlet_temperature": {
                "field_name": "Nominal Supply Air Outlet Temperature",
                "field_type": "n"
            },
            "nominal_secondary_air_flow_rate": {
                "field_name": "Nominal Secondary Air Flow Rate",
                "field_type": "n"
            },
            "nominal_secondary_air_inlet_temperature": {
                "field_name": "Nominal Secondary Air Inlet Temperature",
                "field_type": "n"
            },
            "nominal_electric_power": {
                "field_name": "Nominal Electric Power",
                "field_type": "n"
            },
            "supply_air_inlet_node_name": {
                "field_name": "Supply Air Inlet Node Name",
                "field_type": "a"
            },
            "supply_air_outlet_node_name": {
                "field_name": "Supply Air Outlet Node Name",
                "field_type": "a"
            },
            "secondary_air_inlet_node_name": {
                "field_name": "Secondary Air Inlet Node Name",
                "field_type": "a"
            },
            "secondary_air_outlet_node_name": {
                "field_name": "Secondary Air Outlet Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "flow_arrangement_type",
            "economizer_lockout",
            "ratio_of_supply_to_secondary_ha_values",
            "nominal_supply_air_flow_rate",
            "nominal_supply_air_inlet_temperature",
            "nominal_supply_air_outlet_temperature",
            "nominal_secondary_air_flow_rate",
            "nominal_secondary_air_inlet_temperature",
            "nominal_electric_power",
            "supply_air_inlet_node_name",
            "supply_air_outlet_node_name",
            "secondary_air_inlet_node_name",
            "secondary_air_outlet_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "flow_arrangement_type",
                "economizer_lockout",
                "supply_air_inlet_node_name",
                "supply_air_outlet_node_name",
                "secondary_air_inlet_node_name",
                "secondary_air_outlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "ratio_of_supply_to_secondary_ha_values",
                "nominal_supply_air_flow_rate",
                "nominal_supply_air_inlet_temperature",
                "nominal_supply_air_outlet_temperature",
                "nominal_secondary_air_flow_rate",
                "nominal_secondary_air_inlet_temperature",
                "nominal_electric_power"
            ]
        }
    },
    "type": "object",
    "memo": "Flat plate air-to-air heat exchanger, typically used for exhaust or relief air heat recovery.",
    "min_fields": 15.0
}
```
