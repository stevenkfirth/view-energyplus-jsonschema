```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "file_name": {
                    "type": "string",
                    "retaincase": true,
                    "note": "default file name is \"Window5DataFile.dat\" limit on this field is 100 characters."
                }
            }
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ConstructionNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "file_name": {
                "field_name": "File Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "file_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "file_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Initiates search of the Window data file for a window called Name."
}
```
