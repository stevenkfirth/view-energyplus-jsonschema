```
{
    "ZoneHVAC:EquipmentConnections": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "zone_conditioning_equipment_list_name": {
                        "type": "string",
                        "note": "Enter the name of a ZoneHVAC:EquipmentList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneEquipmentLists"
                        ]
                    },
                    "zone_air_inlet_node_or_nodelist_name": {
                        "type": "string"
                    },
                    "zone_air_exhaust_node_or_nodelist_name": {
                        "type": "string"
                    },
                    "zone_air_node_name": {
                        "type": "string"
                    },
                    "zone_return_air_node_or_nodelist_name": {
                        "type": "string"
                    },
                    "zone_return_air_node_1_flow_rate_fraction_schedule_name": {
                        "type": "string",
                        "note": "This schedule is multiplied times the base return air flow rate. If this field is left blank, the schedule defaults to 1.0 at all times.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "zone_return_air_node_1_flow_rate_basis_node_or_nodelist_name": {
                        "type": "string",
                        "note": "The optional basis node(s) used to calculate the base return air flow rate for the first return air node in this zone. The return air flow rate is the sum of the flow rates at the basis node(s) multiplied by the Zone Return Air Flow Rate Fraction Schedule. If this  field is blank, then the base return air flow rate is the total supply inlet flow rate to the zone less the total exhaust node flow rate from the zone."
                    }
                },
                "required": [
                    "zone_name",
                    "zone_conditioning_equipment_list_name",
                    "zone_air_node_name"
                ]
            }
        },
        "group": "Zone HVAC Equipment Connections",
        "legacy_idd": {
            "field_info": {
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "zone_conditioning_equipment_list_name": {
                    "field_name": "Zone Conditioning Equipment List Name",
                    "field_type": "a"
                },
                "zone_air_inlet_node_or_nodelist_name": {
                    "field_name": "Zone Air Inlet Node or NodeList Name",
                    "field_type": "a"
                },
                "zone_air_exhaust_node_or_nodelist_name": {
                    "field_name": "Zone Air Exhaust Node or NodeList Name",
                    "field_type": "a"
                },
                "zone_air_node_name": {
                    "field_name": "Zone Air Node Name",
                    "field_type": "a"
                },
                "zone_return_air_node_or_nodelist_name": {
                    "field_name": "Zone Return Air Node or NodeList Name",
                    "field_type": "a"
                },
                "zone_return_air_node_1_flow_rate_fraction_schedule_name": {
                    "field_name": "Zone Return Air Node 1 Flow Rate Fraction Schedule Name",
                    "field_type": "a"
                },
                "zone_return_air_node_1_flow_rate_basis_node_or_nodelist_name": {
                    "field_name": "Zone Return Air Node 1 Flow Rate Basis Node or NodeList Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "zone_name",
                "zone_conditioning_equipment_list_name",
                "zone_air_inlet_node_or_nodelist_name",
                "zone_air_exhaust_node_or_nodelist_name",
                "zone_air_node_name",
                "zone_return_air_node_or_nodelist_name",
                "zone_return_air_node_1_flow_rate_fraction_schedule_name",
                "zone_return_air_node_1_flow_rate_basis_node_or_nodelist_name"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "zone_conditioning_equipment_list_name",
                    "zone_air_inlet_node_or_nodelist_name",
                    "zone_air_exhaust_node_or_nodelist_name",
                    "zone_air_node_name",
                    "zone_return_air_node_or_nodelist_name",
                    "zone_return_air_node_1_flow_rate_fraction_schedule_name",
                    "zone_return_air_node_1_flow_rate_basis_node_or_nodelist_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Specifies the HVAC equipment connections for a zone. Node names are specified for the zone air node, air inlet nodes, air exhaust nodes, and the air return node. A zone equipment list is referenced which lists all HVAC equipment connected to the zone."
    }
}
```
