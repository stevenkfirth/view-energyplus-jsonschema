```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "lines": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "program_line": {
                                "type": "string"
                            }
                        },
                        "type": "object"
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
            "ErlProgramNames"
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
            "program_line": {
                "field_name": "Program Line",
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
                "program_line"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "program_line"
        ],
        "extension": "lines"
    },
    "type": "object",
    "memo": "This input defines an Erl program subroutine Each field after the name is a line of EMS Runtime Language",
    "min_fields": 2.0,
    "extensible_size": 1.0
}
```
