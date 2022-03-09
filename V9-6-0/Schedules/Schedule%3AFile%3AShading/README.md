```
{
    "Schedule:File:Shading": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "file_name": {
                        "type": "string",
                        "note": "The name of the file that writes all shading data.",
                        "retaincase": true
                    }
                },
                "required": [
                    "file_name"
                ]
            }
        },
        "group": "Schedules",
        "legacy_idd": {
            "field_info": {
                "file_name": {
                    "field_name": "File Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "file_name"
            ],
            "alphas": {
                "fields": [
                    "file_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "A Schedule:File:Shading points to a CSV file that has 8760-8784 hours of sunlit fraction data for all or some of the exterior surfaces.",
        "min_fields": 1.0
    }
}
```
