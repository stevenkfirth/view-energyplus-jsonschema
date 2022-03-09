```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "meter_name": {
                    "type": "string",
                    "data_type": "external_list",
                    "external_list": [
                        "autoRDDmeter"
                    ]
                },
                "demand_limit_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "demand_limit_safety_fraction": {
                    "type": "number",
                    "minimum": 0.0
                },
                "billing_period_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This field should reference the same schedule as the month schedule name field of the UtilityCost:Tariff object, if used. If blank, defaults to regular divisions between months."
                },
                "peak_period_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This field should reference the same schedule as the period schedule name field of the UtilityCost:Tariff object, if used. If blank, defaults to always on peak."
                },
                "demand_window_length": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "minutes"
                },
                "demand_manager_priority": {
                    "type": "string",
                    "enum": [
                        "All",
                        "Sequential"
                    ]
                },
                "manager_data": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "demandmanager_object_type": {
                                "type": "string",
                                "enum": [
                                    "DemandManager:ElectricEquipment",
                                    "DemandManager:ExteriorLights",
                                    "DemandManager:Lights",
                                    "DemandManager:Thermostats",
                                    "DemandManager:Ventilation"
                                ]
                            },
                            "demandmanager_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "DemandManagerNames"
                                ]
                            }
                        },
                        "type": "object"
                    }
                }
            },
            "required": [
                "meter_name",
                "demand_limit_safety_fraction",
                "demand_window_length",
                "demand_manager_priority"
            ]
        }
    },
    "group": "Demand Limiting Controls",
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
            "meter_name": {
                "field_name": "Meter Name",
                "field_type": "a"
            },
            "demand_limit_schedule_name": {
                "field_name": "Demand Limit Schedule Name",
                "field_type": "a"
            },
            "demand_limit_safety_fraction": {
                "field_name": "Demand Limit Safety Fraction",
                "field_type": "n"
            },
            "billing_period_schedule_name": {
                "field_name": "Billing Period Schedule Name",
                "field_type": "a"
            },
            "peak_period_schedule_name": {
                "field_name": "Peak Period Schedule Name",
                "field_type": "a"
            },
            "demand_window_length": {
                "field_name": "Demand Window Length",
                "field_type": "n"
            },
            "demand_manager_priority": {
                "field_name": "Demand Manager Priority",
                "field_type": "a"
            },
            "demandmanager_object_type": {
                "field_name": "DemandManager Object Type",
                "field_type": "a"
            },
            "demandmanager_name": {
                "field_name": "DemandManager Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "meter_name",
            "demand_limit_schedule_name",
            "demand_limit_safety_fraction",
            "billing_period_schedule_name",
            "peak_period_schedule_name",
            "demand_window_length",
            "demand_manager_priority"
        ],
        "alphas": {
            "fields": [
                "name",
                "meter_name",
                "demand_limit_schedule_name",
                "billing_period_schedule_name",
                "peak_period_schedule_name",
                "demand_manager_priority"
            ],
            "extensions": [
                "demandmanager_object_type",
                "demandmanager_name"
            ]
        },
        "numerics": {
            "fields": [
                "demand_limit_safety_fraction",
                "demand_window_length"
            ]
        },
        "extensibles": [
            "demandmanager_object_type",
            "demandmanager_name"
        ],
        "extension": "manager_data"
    },
    "type": "object",
    "memo": "a list of meters that can be reported are available after a run on the meter dictionary file (.mdd) if the Output:VariableDictionary has been requested.",
    "extensible_size": 2.0
}
```
