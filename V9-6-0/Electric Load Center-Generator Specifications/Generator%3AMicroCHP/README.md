```
{
    "Generator:MicroCHP": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "performance_parameters_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:MicroCHP:NonNormalizedParameters object.",
                        "data_type": "object_list",
                        "object_list": [
                            "MicroCHPParametersNames"
                        ]
                    },
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "cooling_water_inlet_node_name": {
                        "type": "string"
                    },
                    "cooling_water_outlet_node_name": {
                        "type": "string"
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "generator_fuel_supply_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "GenFuelSupNames"
                        ],
                        "note": "Enter the name of a Generator:FuelSupply object."
                    },
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "reference": [
                "GeneratorNames",
                "validBranchEquipmentNames",
                "validPlantEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validPlantEquipmentTypes"
            ]
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "performance_parameters_name": {
                    "field_name": "Performance Parameters Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "cooling_water_inlet_node_name": {
                    "field_name": "Cooling Water Inlet Node Name",
                    "field_type": "a"
                },
                "cooling_water_outlet_node_name": {
                    "field_name": "Cooling Water Outlet Node Name",
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
                "generator_fuel_supply_name": {
                    "field_name": "Generator Fuel Supply Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "performance_parameters_name",
                "zone_name",
                "cooling_water_inlet_node_name",
                "cooling_water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "generator_fuel_supply_name",
                "availability_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "performance_parameters_name",
                    "zone_name",
                    "cooling_water_inlet_node_name",
                    "cooling_water_outlet_node_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "generator_fuel_supply_name",
                    "availability_schedule_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Small-scale combined heat and power (micro CHP) electric generator using the model developed by IEA/ECBCS Annex 42 see www.cogen-sim.net. The model was developed for both internal combustion and Stirling cycle engines, but might be used for other types of residential CHP devices."
    }
}
```
