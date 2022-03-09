```
{
    "DistrictHeating": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "hot_water_inlet_node_name": {
                        "type": "string"
                    },
                    "hot_water_outlet_node_name": {
                        "type": "string"
                    },
                    "nominal_capacity": {
                        "units": "W",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "capacity_fraction_schedule_name": {
                        "type": "string",
                        "note": "Schedule values are multiplied by Nominal Capacity for current capacity",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "hot_water_inlet_node_name",
                    "hot_water_outlet_node_name"
                ]
            }
        },
        "group": "Plant Heating and Cooling Equipment",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validCondenserEquipmentTypes",
                "validPlantEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames",
                "validCondenserEquipmentNames",
                "validPlantEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "hot_water_inlet_node_name": {
                    "field_name": "Hot Water Inlet Node Name",
                    "field_type": "a"
                },
                "hot_water_outlet_node_name": {
                    "field_name": "Hot Water Outlet Node Name",
                    "field_type": "a"
                },
                "nominal_capacity": {
                    "field_name": "Nominal Capacity",
                    "field_type": "n"
                },
                "capacity_fraction_schedule_name": {
                    "field_name": "Capacity Fraction Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "hot_water_inlet_node_name",
                "hot_water_outlet_node_name",
                "nominal_capacity",
                "capacity_fraction_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "hot_water_inlet_node_name",
                    "hot_water_outlet_node_name",
                    "capacity_fraction_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "nominal_capacity"
                ]
            }
        },
        "type": "object",
        "memo": "Centralized source of hot water, such as a district heating system."
    }
}
```
