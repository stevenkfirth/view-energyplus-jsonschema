```
{
    "Version": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "version_identifier": {
                        "type": "string",
                        "default": "9.6"
                    }
                }
            }
        },
        "group": "Simulation Parameters",
        "legacy_idd": {
            "field_info": {
                "version_identifier": {
                    "field_name": "Version Identifier",
                    "field_type": "a"
                }
            },
            "fields": [
                "version_identifier"
            ],
            "alphas": {
                "fields": [
                    "version_identifier"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Specifies the EnergyPlus version of the IDF file.",
        "format": "singleLine"
    }
}
```
