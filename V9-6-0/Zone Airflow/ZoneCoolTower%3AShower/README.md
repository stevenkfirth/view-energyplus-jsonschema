```
{
    "ZoneCoolTower:Shower": {
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
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "water_supply_storage_tank_name": {
                        "type": "string",
                        "note": "In case of stand alone tank or underground water, leave this input blank",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    },
                    "flow_control_type": {
                        "type": "string",
                        "note": "Water flow schedule should be selected when the water flow rate is known. Wind-driven flow should be selected when the water flow rate is unknown.",
                        "enum": [
                            "",
                            "WaterFlowSchedule",
                            "WindDrivenFlow"
                        ],
                        "default": "WindDrivenFlow"
                    },
                    "pump_flow_rate_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "maximum_water_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min"
                    },
                    "effective_tower_height": {
                        "type": "number",
                        "note": "This field is from either the spray or the wet pad to the top of the outlet.",
                        "units": "m"
                    },
                    "airflow_outlet_area": {
                        "type": "number",
                        "note": "User have to specify effective area when outlet area is relatively bigger than the cross sectional area of cooltower. If the number of outlet is more than one, assume the air passes through only one.",
                        "units": "m2"
                    },
                    "maximum_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "minimum_indoor_temperature": {
                        "type": "number",
                        "note": "This field is to specify the indoor temperature below which cooltower is shutoff.",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0
                    },
                    "fraction_of_water_loss": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "fraction_of_flow_schedule": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "rated_power_consumption": {
                        "type": "number",
                        "units": "W"
                    }
                },
                "required": [
                    "zone_name",
                    "pump_flow_rate_schedule_name",
                    "maximum_water_flow_rate",
                    "effective_tower_height",
                    "airflow_outlet_area",
                    "maximum_air_flow_rate",
                    "minimum_indoor_temperature",
                    "rated_power_consumption"
                ]
            }
        },
        "group": "Zone Airflow",
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
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "water_supply_storage_tank_name": {
                    "field_name": "Water Supply Storage Tank Name",
                    "field_type": "a"
                },
                "flow_control_type": {
                    "field_name": "Flow Control Type",
                    "field_type": "a"
                },
                "pump_flow_rate_schedule_name": {
                    "field_name": "Pump Flow Rate Schedule Name",
                    "field_type": "a"
                },
                "maximum_water_flow_rate": {
                    "field_name": "Maximum Water Flow Rate",
                    "field_type": "n"
                },
                "effective_tower_height": {
                    "field_name": "Effective Tower Height",
                    "field_type": "n"
                },
                "airflow_outlet_area": {
                    "field_name": "Airflow Outlet Area",
                    "field_type": "n"
                },
                "maximum_air_flow_rate": {
                    "field_name": "Maximum Air Flow Rate",
                    "field_type": "n"
                },
                "minimum_indoor_temperature": {
                    "field_name": "Minimum Indoor Temperature",
                    "field_type": "n"
                },
                "fraction_of_water_loss": {
                    "field_name": "Fraction of Water Loss",
                    "field_type": "n"
                },
                "fraction_of_flow_schedule": {
                    "field_name": "Fraction of Flow Schedule",
                    "field_type": "n"
                },
                "rated_power_consumption": {
                    "field_name": "Rated Power Consumption",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "water_supply_storage_tank_name",
                "flow_control_type",
                "pump_flow_rate_schedule_name",
                "maximum_water_flow_rate",
                "effective_tower_height",
                "airflow_outlet_area",
                "maximum_air_flow_rate",
                "minimum_indoor_temperature",
                "fraction_of_water_loss",
                "fraction_of_flow_schedule",
                "rated_power_consumption"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "zone_name",
                    "water_supply_storage_tank_name",
                    "flow_control_type",
                    "pump_flow_rate_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_water_flow_rate",
                    "effective_tower_height",
                    "airflow_outlet_area",
                    "maximum_air_flow_rate",
                    "minimum_indoor_temperature",
                    "fraction_of_water_loss",
                    "fraction_of_flow_schedule",
                    "rated_power_consumption"
                ]
            }
        },
        "type": "object",
        "memo": "A cooltower (sometimes referred to as a wind tower or a shower cooling tower) models passive downdraught evaporative cooling (PDEC) that is designed to capture the wind at the top of a tower and cool the outdoor air using water evaporation before delivering it to a space."
    }
}
```
