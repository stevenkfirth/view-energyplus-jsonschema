```
{
    "EvaporativeCooler:Direct:CelDekPad": {
        "patternProperties": {
            ".*": {
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
                    "direct_pad_area": {
                        "units": "m2",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
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
                    "direct_pad_depth": {
                        "units": "m",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
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
                    "recirculating_water_pump_power_consumption": {
                        "type": "number",
                        "units": "W",
                        "ip-units": "W"
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "control_type": {
                        "type": "string",
                        "note": "This field is not currently used and can be left blank"
                    },
                    "water_supply_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    }
                },
                "required": [
                    "recirculating_water_pump_power_consumption",
                    "air_inlet_node_name",
                    "air_outlet_node_name"
                ]
            }
        },
        "group": "Evaporative Coolers",
        "name": {
            "type": "string",
            "reference": [
                "EvapCoolerNames",
                "validBranchEquipmentNames",
                "validOASysEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validOASysEquipmentTypes"
            ]
        },
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
                "direct_pad_area": {
                    "field_name": "Direct Pad Area",
                    "field_type": "n"
                },
                "direct_pad_depth": {
                    "field_name": "Direct Pad Depth",
                    "field_type": "n"
                },
                "recirculating_water_pump_power_consumption": {
                    "field_name": "Recirculating Water Pump Power Consumption",
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
                "control_type": {
                    "field_name": "Control Type",
                    "field_type": "a"
                },
                "water_supply_storage_tank_name": {
                    "field_name": "Water Supply Storage Tank Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "direct_pad_area",
                "direct_pad_depth",
                "recirculating_water_pump_power_consumption",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "control_type",
                "water_supply_storage_tank_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "control_type",
                    "water_supply_storage_tank_name"
                ]
            },
            "numerics": {
                "fields": [
                    "direct_pad_area",
                    "direct_pad_depth",
                    "recirculating_water_pump_power_consumption"
                ]
            }
        },
        "type": "object",
        "memo": "Direct evaporative cooler with rigid media evaporative pad and recirculating water pump. This model has no controls other than its availability schedule.",
        "min_fields": 7.0
    }
}
```
