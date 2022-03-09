```
{
    "Humidifier:Steam:Electric": {
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
                    "rated_capacity": {
                        "note": "Capacity is m3/s of water at 5.05 C",
                        "units": "m3/s",
                        "ip-units": "gal/min",
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
                    "rated_power": {
                        "units": "W",
                        "ip-units": "W",
                        "note": "if autosized the rated power is calculated from the rated capacity and enthalpy rise of water from 20.0C to 100.0C steam and assumes electric to thermal energy conversion efficiency of 100.0%",
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
                    "rated_fan_power": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "ip-units": "W"
                    },
                    "standby_power": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "ip-units": "W"
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    }
                }
            }
        },
        "group": "Humidifiers and Dehumidifiers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validOASysEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames",
                "validOASysEquipmentNames"
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
                "rated_capacity": {
                    "field_name": "Rated Capacity",
                    "field_type": "n"
                },
                "rated_power": {
                    "field_name": "Rated Power",
                    "field_type": "n"
                },
                "rated_fan_power": {
                    "field_name": "Rated Fan Power",
                    "field_type": "n"
                },
                "standby_power": {
                    "field_name": "Standby Power",
                    "field_type": "n"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "water_storage_tank_name": {
                    "field_name": "Water Storage Tank Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "rated_capacity",
                "rated_power",
                "rated_fan_power",
                "standby_power",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "water_storage_tank_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "water_storage_tank_name"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_capacity",
                    "rated_power",
                    "rated_fan_power",
                    "standby_power"
                ]
            }
        },
        "type": "object",
        "memo": "Electrically heated steam humidifier with fan."
    }
}
```
