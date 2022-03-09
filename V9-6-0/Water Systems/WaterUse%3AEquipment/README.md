```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                },
                "peak_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "flow_rate_fraction_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Defaults to 1.0 at all times"
                },
                "target_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Defaults to hot water supply temperature"
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
                "zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "sensible_fraction_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Defaults to 0.0 at all times"
                },
                "latent_fraction_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Defaults to 0.0 at all times"
                }
            },
            "required": [
                "peak_flow_rate"
            ]
        }
    },
    "group": "Water Systems",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "WaterUseEquipmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            },
            "peak_flow_rate": {
                "field_name": "Peak Flow Rate",
                "field_type": "n"
            },
            "flow_rate_fraction_schedule_name": {
                "field_name": "Flow Rate Fraction Schedule Name",
                "field_type": "a"
            },
            "target_temperature_schedule_name": {
                "field_name": "Target Temperature Schedule Name",
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "sensible_fraction_schedule_name": {
                "field_name": "Sensible Fraction Schedule Name",
                "field_type": "a"
            },
            "latent_fraction_schedule_name": {
                "field_name": "Latent Fraction Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "end_use_subcategory",
            "peak_flow_rate",
            "flow_rate_fraction_schedule_name",
            "target_temperature_schedule_name",
            "hot_water_supply_temperature_schedule_name",
            "cold_water_supply_temperature_schedule_name",
            "zone_name",
            "sensible_fraction_schedule_name",
            "latent_fraction_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "end_use_subcategory",
                "flow_rate_fraction_schedule_name",
                "target_temperature_schedule_name",
                "hot_water_supply_temperature_schedule_name",
                "cold_water_supply_temperature_schedule_name",
                "zone_name",
                "sensible_fraction_schedule_name",
                "latent_fraction_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "peak_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "A generalized object for simulating all water end uses. Hot and cold water uses are included, as well as controlled mixing of hot and cold water at the tap. The WaterUse:Equipment object can be used stand-alone, or coupled into a plant loop using the WaterUse:Connections object (see below). The WaterUse:Connections object allows water uses to be linked to WaterUse:Storage objects to store and draw reclaimed water. The object can also simulate drainwater heat recovery."
}
```
