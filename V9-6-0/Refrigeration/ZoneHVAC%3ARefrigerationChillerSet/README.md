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
                "zone_name": {
                    "type": "string",
                    "note": "This must be a controlled zone and appear in a ZoneHVAC:EquipmentConnections object.",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "air_inlet_node_name": {
                    "type": "string",
                    "note": "Not used - reserved for future use Name of the zone exhaust node (see Node) from which the refrigeration chiller draws its indoor air. This should be one of the zone exhaust nodes for the zone cooled by the chiller set."
                },
                "air_outlet_node_name": {
                    "type": "string",
                    "note": "Not used - reserved for future use The name of the node where the chiller coil sends its outlet air, which must be one of the inlet air nodes for the zone which is being cooled."
                },
                "chillers": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "air_chiller_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "note": "This is the first chiller turned on to meet the zone load",
                                "object_list": [
                                    "RefrigerationAirChillerNames"
                                ]
                            }
                        },
                        "type": "object"
                    }
                }
            }
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ZoneEquipmentNames"
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "air_chiller_name": {
                "field_name": "Air Chiller Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "zone_name",
            "air_inlet_node_name",
            "air_outlet_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "air_inlet_node_name",
                "air_outlet_node_name"
            ],
            "extensions": [
                "air_chiller_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "air_chiller_name"
        ],
        "extension": "chillers"
    },
    "type": "object",
    "memo": "Works in conjunction with one or multiple air chillers, compressor racks, refrigeration systems, or refrigeration secondary system objects to simulate the performance of a group of air chillers cooling a single zone. The chiller set model passes information about the zone conditions to determine the performance of individual chiller coils within the set, thus providing the sensible and latent heat exchange with the zone environment.",
    "min_fields": 6.0,
    "extensible_size": 1.0
}
```
