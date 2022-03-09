```
{
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
                "supply_water_storage_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ],
                    "note": "If blank, or tank is empty, defaults to fresh water from the mains"
                },
                "reclamation_water_storage_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
                },
                "hot_water_supply_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Defaults to cold water supply temperature"
                },
                "cold_water_supply_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Defaults to water temperatures calculated by Site:WaterMainsTemperature object"
                },
                "drain_water_heat_exchanger_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "CounterFlow",
                        "CrossFlow",
                        "Ideal",
                        "None"
                    ],
                    "default": "None"
                },
                "drain_water_heat_exchanger_destination": {
                    "type": "string",
                    "enum": [
                        "",
                        "Equipment",
                        "Plant",
                        "PlantAndEquipment"
                    ],
                    "default": "Plant"
                },
                "drain_water_heat_exchanger_u_factor_times_area": {
                    "type": "number",
                    "units": "W/K",
                    "minimum": 0.0
                },
                "connections": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "water_use_equipment_name": {
                                "type": "string",
                                "note": "Enter the name of a WaterUse:Equipment object.",
                                "data_type": "object_list",
                                "object_list": [
                                    "WaterUseEquipmentNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "water_use_equipment_name"
                        ]
                    }
                }
            }
        }
    },
    "group": "Water Systems",
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
            "supply_water_storage_tank_name": {
                "field_name": "Supply Water Storage Tank Name",
                "field_type": "a"
            },
            "reclamation_water_storage_tank_name": {
                "field_name": "Reclamation Water Storage Tank Name",
                "field_type": "a"
            },
            "hot_water_supply_temperature_schedule_name": {
                "field_name": "Hot Water Supply Temperature Schedule Name",
                "field_type": "a"
            },
            "cold_water_supply_temperature_schedule_name": {
                "field_name": "Cold Water Supply Temperature Schedule Name",
                "field_type": "a"
            },
            "drain_water_heat_exchanger_type": {
                "field_name": "Drain Water Heat Exchanger Type",
                "field_type": "a"
            },
            "drain_water_heat_exchanger_destination": {
                "field_name": "Drain Water Heat Exchanger Destination",
                "field_type": "a"
            },
            "drain_water_heat_exchanger_u_factor_times_area": {
                "field_name": "Drain Water Heat Exchanger U-Factor Times Area",
                "field_type": "n"
            },
            "water_use_equipment_name": {
                "field_name": "Water Use Equipment Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "inlet_node_name",
            "outlet_node_name",
            "supply_water_storage_tank_name",
            "reclamation_water_storage_tank_name",
            "hot_water_supply_temperature_schedule_name",
            "cold_water_supply_temperature_schedule_name",
            "drain_water_heat_exchanger_type",
            "drain_water_heat_exchanger_destination",
            "drain_water_heat_exchanger_u_factor_times_area"
        ],
        "alphas": {
            "fields": [
                "name",
                "inlet_node_name",
                "outlet_node_name",
                "supply_water_storage_tank_name",
                "reclamation_water_storage_tank_name",
                "hot_water_supply_temperature_schedule_name",
                "cold_water_supply_temperature_schedule_name",
                "drain_water_heat_exchanger_type",
                "drain_water_heat_exchanger_destination"
            ],
            "extensions": [
                "water_use_equipment_name"
            ]
        },
        "numerics": {
            "fields": [
                "drain_water_heat_exchanger_u_factor_times_area"
            ]
        },
        "extensibles": [
            "water_use_equipment_name"
        ],
        "extension": "connections"
    },
    "type": "object",
    "memo": "A subsystem that groups together multiple WaterUse:Equipment components. As its name suggests, the object provides connections that are shared by these components, including: 1. Inlet node and outlet node connections to a plant loop 2. Connections to WaterUse:Storage objects to store and draw reclaimed water 3. Internal connections to simulate drainwater heat recovery.",
    "extensible_size": 1.0
}
```
