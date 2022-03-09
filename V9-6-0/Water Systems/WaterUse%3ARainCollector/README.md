```
{
    "WaterUse:RainCollector": {
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
                    "loss_factor_mode": {
                        "type": "string",
                        "enum": [
                            "Constant",
                            "Scheduled"
                        ]
                    },
                    "collection_loss_factor": {
                        "type": "number",
                        "note": "this is the portion of rain that is lost in the process of collecting it the rain collected is one minus this factor"
                    },
                    "collection_loss_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "maximum_collection_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "note": "Defaults to unlimited flow."
                    },
                    "surfaces": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "collection_surface_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "AllShadingAndHTSurfNames"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "collection_surface_name"
                            ]
                        }
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
                "loss_factor_mode": {
                    "field_name": "Loss Factor Mode",
                    "field_type": "a"
                },
                "collection_loss_factor": {
                    "field_name": "Collection Loss Factor",
                    "field_type": "n"
                },
                "collection_loss_factor_schedule_name": {
                    "field_name": "Collection Loss Factor Schedule Name",
                    "field_type": "a"
                },
                "maximum_collection_rate": {
                    "field_name": "Maximum Collection Rate",
                    "field_type": "n"
                },
                "collection_surface_name": {
                    "field_name": "Collection Surface Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "storage_tank_name",
                "loss_factor_mode",
                "collection_loss_factor",
                "collection_loss_factor_schedule_name",
                "maximum_collection_rate"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "storage_tank_name",
                    "loss_factor_mode",
                    "collection_loss_factor_schedule_name"
                ],
                "extensions": [
                    "collection_surface_name"
                ]
            },
            "numerics": {
                "fields": [
                    "collection_loss_factor",
                    "maximum_collection_rate"
                ]
            },
            "extensibles": [
                "collection_surface_name"
            ],
            "extension": "surfaces"
        },
        "type": "object",
        "memo": "Used for harvesting rainwater falling on building surfaces. The rainwater is sent to a WaterUse:Storage object. In order to use this object it is necessary to also include a Site:Precipitation object to describe the rates of rainfall.",
        "extensible_size": 1.0
    }
}
```
