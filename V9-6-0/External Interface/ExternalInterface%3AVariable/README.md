```
{
    "ExternalInterface:Variable": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "initial_value": {
                        "type": "number",
                        "note": "Used during warm-up and system sizing."
                    }
                },
                "required": [
                    "initial_value"
                ]
            }
        },
        "group": "External Interface",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "This name becomes a variable for use in Erl programs no spaces allowed in name"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "initial_value": {
                    "field_name": "Initial Value",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "initial_value"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "initial_value"
                ]
            }
        },
        "type": "object",
        "memo": "This input object is similar to EnergyManagementSystem:GlobalVariable. However, at the beginning of each zone time step, its value is set to the value received from the external interface. During the warm-up period and the system sizing, its value is set to the value specified by the field \"initial value.\" This object can be used to move data into Erl subroutines."
    }
}
```
