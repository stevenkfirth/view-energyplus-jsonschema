```
{
    "EnergyManagementSystem:TrendVariable": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "ems_variable_name": {
                        "type": "string",
                        "note": "must be a global scope EMS variable"
                    },
                    "number_of_timesteps_to_be_logged": {
                        "type": "number",
                        "minimum": 1.0
                    }
                },
                "required": [
                    "ems_variable_name",
                    "number_of_timesteps_to_be_logged"
                ]
            }
        },
        "group": "Energy Management System (EMS)",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "no spaces allowed in name"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "ems_variable_name": {
                    "field_name": "EMS Variable Name",
                    "field_type": "a"
                },
                "number_of_timesteps_to_be_logged": {
                    "field_name": "Number of Timesteps to be Logged",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "ems_variable_name",
                "number_of_timesteps_to_be_logged"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "ems_variable_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_timesteps_to_be_logged"
                ]
            }
        },
        "type": "object",
        "memo": "This object sets up an EMS trend variable from an Erl variable A trend variable logs values across timesteps",
        "min_fields": 3.0
    }
}
```
