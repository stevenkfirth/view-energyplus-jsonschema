```
{
    "Coil:Cooling:DX": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "evaporator_inlet_node_name": {
                        "type": "string"
                    },
                    "evaporator_outlet_node_name": {
                        "type": "string"
                    },
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Schedule value > 0 means the coil is available. If this field is blank, the coil is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "condenser_zone_name": {
                        "type": "string",
                        "note": "This input field is name of a conditioned or unconditioned zone where the secondary coil (condenser) of a DX system or heat pump is to be placed. This is an optional input field specified only when the user desires to reject the condenser heat into a zone. The heat rejected is modeled as internal sensible heat gain of the zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "condenser_inlet_node_name": {
                        "type": "string",
                        "note": "This is the name of an air node in the simulation. This may be an explicitly defined outdoor air node, or it may be a separate air node."
                    },
                    "condenser_outlet_node_name": {
                        "type": "string",
                        "note": "This is the name of an air node in the simulation."
                    },
                    "performance_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingPerformanceNames"
                        ]
                    },
                    "condensate_collection_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    },
                    "evaporative_condenser_supply_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    }
                },
                "required": [
                    "evaporator_inlet_node_name",
                    "evaporator_outlet_node_name",
                    "condenser_inlet_node_name",
                    "condenser_outlet_node_name",
                    "performance_object_name"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AFNCoilNames",
                "CoilCoolingDX"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "evaporator_inlet_node_name": {
                    "field_name": "Evaporator Inlet Node Name",
                    "field_type": "a"
                },
                "evaporator_outlet_node_name": {
                    "field_name": "Evaporator Outlet Node Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "condenser_zone_name": {
                    "field_name": "Condenser Zone Name",
                    "field_type": "a"
                },
                "condenser_inlet_node_name": {
                    "field_name": "Condenser Inlet Node Name",
                    "field_type": "a"
                },
                "condenser_outlet_node_name": {
                    "field_name": "Condenser Outlet Node Name",
                    "field_type": "a"
                },
                "performance_object_name": {
                    "field_name": "Performance Object Name",
                    "field_type": "a"
                },
                "condensate_collection_water_storage_tank_name": {
                    "field_name": "Condensate Collection Water Storage Tank Name",
                    "field_type": "a"
                },
                "evaporative_condenser_supply_water_storage_tank_name": {
                    "field_name": "Evaporative Condenser Supply Water Storage Tank Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "evaporator_inlet_node_name",
                "evaporator_outlet_node_name",
                "availability_schedule_name",
                "condenser_zone_name",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name",
                "performance_object_name",
                "condensate_collection_water_storage_tank_name",
                "evaporative_condenser_supply_water_storage_tank_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "evaporator_inlet_node_name",
                    "evaporator_outlet_node_name",
                    "availability_schedule_name",
                    "condenser_zone_name",
                    "condenser_inlet_node_name",
                    "condenser_outlet_node_name",
                    "performance_object_name",
                    "condensate_collection_water_storage_tank_name",
                    "evaporative_condenser_supply_water_storage_tank_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "New general DX cooling coil supporting on or more speeds and one or or operating  modes. Includes DX evaporator coil, compressor, and condenser. Object is currently only supported by the AIRLOOPHVAC:UNITARYSYSTEM object. Remaining Coil:Cooling:DX* objects will be deprecated at a future date, after which, this object will replace all other Coil:Cooling:DX* objects.",
        "min_fields": 8.0
    }
}
```
