```
{
    "EnergyManagementSystem:GlobalVariable": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "variables": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "erl_variable_name": {
                                    "type": "string",
                                    "note": "no spaces allowed in name"
                                }
                            },
                            "type": "object",
                            "required": [
                                "erl_variable_name"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Energy Management System (EMS)",
        "legacy_idd": {
            "field_info": {
                "erl_variable_name": {
                    "field_name": "Erl Variable Name",
                    "field_type": "a"
                }
            },
            "fields": [],
            "alphas": {
                "fields": [],
                "extensions": [
                    "erl_variable_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "erl_variable_name"
            ],
            "extension": "variables"
        },
        "type": "object",
        "memo": "Declares Erl variable as having global scope No spaces allowed in names used for Erl variables",
        "min_fields": 1.0,
        "extensible_size": 1.0
    }
}
```
