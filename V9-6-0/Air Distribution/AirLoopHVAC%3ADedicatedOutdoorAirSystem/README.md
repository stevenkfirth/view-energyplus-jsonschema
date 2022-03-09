```
{
    "AirLoopHVAC:DedicatedOutdoorAirSystem": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "airloophvac_outdoorairsystem_name": {
                        "type": "string",
                        "note": "Enter the name of an AirLoopHVAC:OutdoorAirSystem object.",
                        "data_type": "object_list",
                        "object_list": [
                            "validBranchEquipmentNames"
                        ]
                    },
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "airloophvac_mixer_name": {
                        "type": "string",
                        "note": "Name of AirLoopHVAC:Mixer.",
                        "object_list": [
                            "AirLoopHVACMixerNames"
                        ]
                    },
                    "airloophvac_splitter_name": {
                        "type": "string",
                        "note": "Name of AirLoopHVAC:Splitter.",
                        "object_list": [
                            "AirLoopHVACSplitterNames"
                        ]
                    },
                    "preheat_design_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "preheat_design_humidity_ratio": {
                        "type": "number",
                        "units": "kgWater/kgDryAir"
                    },
                    "precool_design_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "precool_design_humidity_ratio": {
                        "type": "number",
                        "units": "kgWater/kgDryAir"
                    },
                    "number_of_airloophvac": {
                        "type": "number",
                        "note": "Enter the number of the AirLoopHAVC served by AirLoopHVAC:DedicatedOutdoorAirSystem"
                    },
                    "airloophvacs": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "airloophvac_name": {
                                    "type": "string",
                                    "note": "The rest of fields are extensible. It requires AirLoopHVAC names served by an AirLoopHVAC:DedicatedOutdoorAirSystem.",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "AirPrimaryLoops"
                                    ]
                                }
                            },
                            "type": "object"
                        }
                    }
                },
                "required": [
                    "airloophvac_mixer_name",
                    "airloophvac_splitter_name",
                    "preheat_design_temperature",
                    "preheat_design_humidity_ratio",
                    "precool_design_temperature",
                    "precool_design_humidity_ratio",
                    "number_of_airloophvac"
                ]
            }
        },
        "group": "Air Distribution",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DOASAirLoops"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "airloophvac_outdoorairsystem_name": {
                    "field_name": "AirLoopHVAC:OutdoorAirSystem Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "airloophvac_mixer_name": {
                    "field_name": "AirLoopHVAC:Mixer Name",
                    "field_type": "a"
                },
                "airloophvac_splitter_name": {
                    "field_name": "AirLoopHVAC:Splitter Name",
                    "field_type": "a"
                },
                "preheat_design_temperature": {
                    "field_name": "Preheat Design Temperature",
                    "field_type": "n"
                },
                "preheat_design_humidity_ratio": {
                    "field_name": "Preheat Design Humidity Ratio",
                    "field_type": "n"
                },
                "precool_design_temperature": {
                    "field_name": "Precool Design Temperature",
                    "field_type": "n"
                },
                "precool_design_humidity_ratio": {
                    "field_name": "Precool Design Humidity Ratio",
                    "field_type": "n"
                },
                "number_of_airloophvac": {
                    "field_name": "Number of AirLoopHVAC",
                    "field_type": "n"
                },
                "airloophvac_name": {
                    "field_name": "AirLoopHVAC Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "airloophvac_outdoorairsystem_name",
                "availability_schedule_name",
                "airloophvac_mixer_name",
                "airloophvac_splitter_name",
                "preheat_design_temperature",
                "preheat_design_humidity_ratio",
                "precool_design_temperature",
                "precool_design_humidity_ratio",
                "number_of_airloophvac"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "airloophvac_outdoorairsystem_name",
                    "availability_schedule_name",
                    "airloophvac_mixer_name",
                    "airloophvac_splitter_name"
                ],
                "extensions": [
                    "airloophvac_name"
                ]
            },
            "numerics": {
                "fields": [
                    "preheat_design_temperature",
                    "preheat_design_humidity_ratio",
                    "precool_design_temperature",
                    "precool_design_humidity_ratio",
                    "number_of_airloophvac"
                ]
            },
            "extensibles": [
                "airloophvac_name"
            ],
            "extension": "airloophvacs"
        },
        "type": "object",
        "memo": "Defines a central forced air system to provide dedicated outdoor air to multiple AirLoopHVACs.",
        "min_fields": 11.0,
        "extensible_size": 1.0
    }
}
```
