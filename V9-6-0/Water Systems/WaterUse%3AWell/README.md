```
{
    "WaterUse:Well": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    },
                    "pump_depth": {
                        "type": "number",
                        "units": "m"
                    },
                    "pump_rated_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min"
                    },
                    "pump_rated_head": {
                        "type": "number",
                        "units": "Pa"
                    },
                    "pump_rated_power_consumption": {
                        "type": "number",
                        "units": "W"
                    },
                    "pump_efficiency": {
                        "type": "number"
                    },
                    "well_recovery_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min"
                    },
                    "nominal_well_storage_volume": {
                        "type": "number",
                        "units": "m3",
                        "ip-units": "gal"
                    },
                    "water_table_depth_mode": {
                        "type": "string",
                        "enum": [
                            "Constant",
                            "Scheduled"
                        ]
                    },
                    "water_table_depth": {
                        "type": "number",
                        "units": "m"
                    },
                    "water_table_depth_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "storage_tank_name"
                ]
            }
        },
        "group": "Water Systems",
        "name": {
            "type": "string",
            "is_required": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "storage_tank_name": {
                    "field_name": "Storage Tank Name",
                    "field_type": "a"
                },
                "pump_depth": {
                    "field_name": "Pump Depth",
                    "field_type": "n"
                },
                "pump_rated_flow_rate": {
                    "field_name": "Pump Rated Flow Rate",
                    "field_type": "n"
                },
                "pump_rated_head": {
                    "field_name": "Pump Rated Head",
                    "field_type": "n"
                },
                "pump_rated_power_consumption": {
                    "field_name": "Pump Rated Power Consumption",
                    "field_type": "n"
                },
                "pump_efficiency": {
                    "field_name": "Pump Efficiency",
                    "field_type": "n"
                },
                "well_recovery_rate": {
                    "field_name": "Well Recovery Rate",
                    "field_type": "n"
                },
                "nominal_well_storage_volume": {
                    "field_name": "Nominal Well Storage Volume",
                    "field_type": "n"
                },
                "water_table_depth_mode": {
                    "field_name": "Water Table Depth Mode",
                    "field_type": "a"
                },
                "water_table_depth": {
                    "field_name": "Water Table Depth",
                    "field_type": "n"
                },
                "water_table_depth_schedule_name": {
                    "field_name": "Water Table Depth Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "storage_tank_name",
                "pump_depth",
                "pump_rated_flow_rate",
                "pump_rated_head",
                "pump_rated_power_consumption",
                "pump_efficiency",
                "well_recovery_rate",
                "nominal_well_storage_volume",
                "water_table_depth_mode",
                "water_table_depth",
                "water_table_depth_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "storage_tank_name",
                    "water_table_depth_mode",
                    "water_table_depth_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "pump_depth",
                    "pump_rated_flow_rate",
                    "pump_rated_head",
                    "pump_rated_power_consumption",
                    "pump_efficiency",
                    "well_recovery_rate",
                    "nominal_well_storage_volume",
                    "water_table_depth"
                ]
            }
        },
        "type": "object",
        "memo": "Simulates on-site water supply from a well. Well water is pumped out of the ground into a WaterUse:Storage. The operation of the ground water well is controlled by the associated WaterUse:Storage which is assumed to be operated as a vented cistern with no pressure tank."
    }
}
```
