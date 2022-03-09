```
{
    "AirflowNetwork:Distribution:Component:Fan": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandOnOffandVAV",
                            "FansSystemModel"
                        ],
                        "reference": [
                            "AirflowNetworkComponentNames"
                        ],
                        "note": "Enter the name of the fan in the primary air loop."
                    },
                    "supply_fan_object_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Fan:ConstantVolume",
                            "Fan:OnOff",
                            "Fan:SystemModel",
                            "Fan:VariableVolume"
                        ],
                        "default": "Fan:ConstantVolume"
                    }
                },
                "required": [
                    "fan_name"
                ]
            }
        },
        "group": "AirflowNetwork",
        "legacy_idd": {
            "field_info": {
                "fan_name": {
                    "field_name": "Fan Name",
                    "field_type": "a"
                },
                "supply_fan_object_type": {
                    "field_name": "Supply Fan Object Type",
                    "field_type": "a"
                }
            },
            "fields": [
                "fan_name",
                "supply_fan_object_type"
            ],
            "alphas": {
                "fields": [
                    "fan_name",
                    "supply_fan_object_type"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object defines the name of the supply Air Fan used in an Air loop.",
        "min_fields": 2.0
    }
}
```
