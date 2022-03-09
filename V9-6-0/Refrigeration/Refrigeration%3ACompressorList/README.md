```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "compressors": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "refrigeration_compressor_name": {
                                "type": "string",
                                "note": "Enter the name of a Refrigeration:Compressor object.",
                                "data_type": "object_list",
                                "object_list": [
                                    "RefrigerationCompressorNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "refrigeration_compressor_name"
                        ]
                    }
                }
            }
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "RefrigerationCompressorAndListNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "refrigeration_compressor_name": {
                "field_name": "Refrigeration Compressor Name",
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
                "refrigeration_compressor_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "refrigeration_compressor_name"
        ],
        "extension": "compressors"
    },
    "type": "object",
    "memo": "List of all the compressors included within a single refrigeration system (Refrigeration:System). Each list must contain at least one compressor. The order in which the individual compressors are listed here will be the order in which the compressors are dispatched to meet the system load. IMPORTANT: List compressor names in the order in which the compressors will be loaded Data is available for many compressors in the RefrigerationCompressor.idf dataset",
    "min_fields": 2.0,
    "extensible_size": 1.0
}
```
