```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "internal_data_index_key_name": {
                    "type": "string"
                },
                "internal_data_type": {
                    "type": "string"
                }
            },
            "required": [
                "internal_data_type"
            ]
        }
    },
    "group": "Energy Management System (EMS)",
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
            "internal_data_index_key_name": {
                "field_name": "Internal Data Index Key Name",
                "field_type": "a"
            },
            "internal_data_type": {
                "field_name": "Internal Data Type",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "internal_data_index_key_name",
            "internal_data_type"
        ],
        "alphas": {
            "fields": [
                "name",
                "internal_data_index_key_name",
                "internal_data_type"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Declares EMS variable as an internal data variable",
    "min_fields": 3.0
}
```
