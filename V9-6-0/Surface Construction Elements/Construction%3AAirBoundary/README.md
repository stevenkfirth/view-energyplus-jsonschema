```
{
    "Construction:AirBoundary": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "air_exchange_method": {
                        "type": "string",
                        "note": "This field controls how air exchange is modeled across this boundary.",
                        "enum": [
                            "",
                            "None",
                            "SimpleMixing"
                        ],
                        "default": "None"
                    },
                    "simple_mixing_air_changes_per_hour": {
                        "type": "number",
                        "note": "If the Air Exchange Method is SimpleMixing then this field specifies the air changes per hour using the volume of the smaller zone as the basis. If an AirflowNetwork simulation is active this field is ignored.",
                        "units": "1/hr",
                        "minimum": 0.0,
                        "default": 0.5
                    },
                    "simple_mixing_schedule_name": {
                        "type": "string",
                        "note": "If the Air Exchange Method is SimpleMixing then this field specifies the air exchange schedule. If this field is blank, the schedule is always 1.0. If an AirflowNetwork simulation is active this field is ignored.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                }
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ConstructionNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "air_exchange_method": {
                    "field_name": "Air Exchange Method",
                    "field_type": "a"
                },
                "simple_mixing_air_changes_per_hour": {
                    "field_name": "Simple Mixing Air Changes per Hour",
                    "field_type": "n"
                },
                "simple_mixing_schedule_name": {
                    "field_name": "Simple Mixing Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "air_exchange_method",
                "simple_mixing_air_changes_per_hour",
                "simple_mixing_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "air_exchange_method",
                    "simple_mixing_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "simple_mixing_air_changes_per_hour"
                ]
            }
        },
        "type": "object",
        "memo": "Indicates an open boundary between two zones. It may be used for base surfaces and fenestration surfaces. The two adjacent zones are grouped together for solar, daylighting and radiant exchange. When this construction type is used, the Outside Boundary Condition of the surface (or the base surface of a fenestration surface) must be either Surface or Zone. A base surface with Construction:AirBoundary cannot hold any fenestration surfaces.",
        "min_fields": 4.0
    }
}
```
