```
{
    "ZoneAirBalance:OutdoorAir": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "air_balance_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "None",
                            "Quadrature"
                        ],
                        "default": "Quadrature",
                        "note": "None: Only perform simple calculations without using a combined zone outdoor air. Quadrature: A combined outdoor air is used in the quadrature sum."
                    },
                    "induced_outdoor_air_due_to_unbalanced_duct_leakage": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "induced_outdoor_air_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the fraction values applied to the Induced Outdoor Air given in the previous input field (0.0 - 1.0)."
                    }
                },
                "required": [
                    "zone_name"
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
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "air_balance_method": {
                    "field_name": "Air Balance Method",
                    "field_type": "a"
                },
                "induced_outdoor_air_due_to_unbalanced_duct_leakage": {
                    "field_name": "Induced Outdoor Air Due to Unbalanced Duct Leakage",
                    "field_type": "n"
                },
                "induced_outdoor_air_schedule_name": {
                    "field_name": "Induced Outdoor Air Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "air_balance_method",
                "induced_outdoor_air_due_to_unbalanced_duct_leakage",
                "induced_outdoor_air_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "air_balance_method",
                    "induced_outdoor_air_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "induced_outdoor_air_due_to_unbalanced_duct_leakage"
                ]
            }
        },
        "type": "object",
        "memo": "Provide a combined zone outdoor air flow by including interactions between mechanical ventilation, infiltration and duct leakage. This object will combine outdoor flows from all ZoneInfiltration and ZoneVentilation objects in the same zone. Balanced flows will be summed, while unbalanced flows will be added in quadrature."
    }
}
```
