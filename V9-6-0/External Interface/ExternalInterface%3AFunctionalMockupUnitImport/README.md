```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "fmu_file_name": {
                    "type": "string",
                    "retaincase": true,
                    "reference": [
                        "FMUFileName"
                    ]
                },
                "fmu_timeout": {
                    "type": "number",
                    "note": "in milli-seconds",
                    "units": "ms",
                    "default": 0.0
                },
                "fmu_loggingon": {
                    "type": "number",
                    "default": 0.0
                }
            },
            "required": [
                "fmu_file_name"
            ]
        }
    },
    "group": "External Interface",
    "legacy_idd": {
        "field_info": {
            "fmu_file_name": {
                "field_name": "FMU File Name",
                "field_type": "a"
            },
            "fmu_timeout": {
                "field_name": "FMU Timeout",
                "field_type": "n"
            },
            "fmu_loggingon": {
                "field_name": "FMU LoggingOn",
                "field_type": "n"
            }
        },
        "fields": [
            "fmu_file_name",
            "fmu_timeout",
            "fmu_loggingon"
        ],
        "alphas": {
            "fields": [
                "fmu_file_name"
            ]
        },
        "numerics": {
            "fields": [
                "fmu_timeout",
                "fmu_loggingon"
            ]
        }
    },
    "type": "object",
    "memo": "This object declares an FMU",
    "min_fields": 3.0
}
```
