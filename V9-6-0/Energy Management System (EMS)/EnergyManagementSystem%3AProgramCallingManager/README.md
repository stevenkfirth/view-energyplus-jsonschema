```
{
    "EnergyManagementSystem:ProgramCallingManager": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "energyplus_model_calling_point": {
                        "type": "string",
                        "enum": [
                            "AfterComponentInputReadIn",
                            "AfterNewEnvironmentWarmUpIsComplete",
                            "AfterPredictorAfterHVACManagers",
                            "AfterPredictorBeforeHVACManagers",
                            "BeginNewEnvironment",
                            "BeginTimestepBeforePredictor",
                            "BeginZoneTimestepAfterInitHeatBalance",
                            "BeginZoneTimestepBeforeInitHeatBalance",
                            "BeginZoneTimestepBeforeSetCurrentWeather",
                            "EndOfSystemSizing",
                            "EndOfSystemTimestepAfterHVACReporting",
                            "EndOfSystemTimestepBeforeHVACReporting",
                            "EndOfZoneSizing",
                            "EndOfZoneTimestepAfterZoneReporting",
                            "EndOfZoneTimestepBeforeZoneReporting",
                            "InsideHVACSystemIterationLoop",
                            "UnitarySystemSizing",
                            "UserDefinedComponentModel"
                        ]
                    },
                    "programs": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "program_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "note": "no spaces allowed in name",
                                    "object_list": [
                                        "ErlProgramNames"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "program_name"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Energy Management System (EMS)",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ProgramNames"
            ],
            "note": "no spaces allowed in name"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "energyplus_model_calling_point": {
                    "field_name": "EnergyPlus Model Calling Point",
                    "field_type": "a"
                },
                "program_name": {
                    "field_name": "Program Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "energyplus_model_calling_point"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "energyplus_model_calling_point"
                ],
                "extensions": [
                    "program_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "program_name"
            ],
            "extension": "programs"
        },
        "type": "object",
        "memo": "Input EMS program. a program needs a name a description of when it should be called and then lines of program code for EMS Runtime language",
        "min_fields": 3.0,
        "extensible_size": 1.0
    }
}
```
