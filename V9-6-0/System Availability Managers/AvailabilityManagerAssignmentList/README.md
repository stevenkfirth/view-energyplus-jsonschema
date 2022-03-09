```
{
    "AvailabilityManagerAssignmentList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "managers": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "availability_manager_object_type": {
                                    "type": "string",
                                    "enum": [
                                        "AvailabilityManager:DifferentialThermostat",
                                        "AvailabilityManager:HighTemperatureTurnOff",
                                        "AvailabilityManager:HighTemperatureTurnOn",
                                        "AvailabilityManager:LowTemperatureTurnOff",
                                        "AvailabilityManager:LowTemperatureTurnOn",
                                        "AvailabilityManager:NightCycle",
                                        "AvailabilityManager:NightVentilation",
                                        "AvailabilityManager:OptimumStart",
                                        "AvailabilityManager:Scheduled",
                                        "AvailabilityManager:ScheduledOff",
                                        "AvailabilityManager:ScheduledOn"
                                    ]
                                },
                                "availability_manager_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "SystemAvailabilityManagers"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "availability_manager_name",
                                "availability_manager_object_type"
                            ]
                        }
                    }
                }
            }
        },
        "group": "System Availability Managers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SystemAvailabilityManagerLists"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_manager_object_type": {
                    "field_name": "Availability Manager Object Type",
                    "field_type": "a"
                },
                "availability_manager_name": {
                    "field_name": "Availability Manager Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name"
            ],
            "alphas": {
                "fields": [
                    "name"
                ],
                "extensions": [
                    "availability_manager_object_type",
                    "availability_manager_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "availability_manager_object_type",
                "availability_manager_name"
            ],
            "extension": "managers"
        },
        "type": "object",
        "memo": "Defines the applicable managers used for an AirLoopHVAC or PlantLoop. The priority of availability managers is based on a set of rules and are specific to the type of loop. The output from each availability manager is an availability status flag: NoAction, ForceOff, CycleOn, or CycleOnZoneFansOnly (used only for air loops).",
        "min_fields": 3.0,
        "extensible_size": 2.0
    }
}
```
