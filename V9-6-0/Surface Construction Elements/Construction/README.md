```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "outside_layer": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "layer_2": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "layer_3": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "layer_4": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "layer_5": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "layer_6": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "layer_7": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "layer_8": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "layer_9": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                },
                "layer_10": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "MaterialName"
                    ]
                }
            },
            "required": [
                "outside_layer"
            ]
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
            "outside_layer": {
                "field_name": "Outside Layer",
                "field_type": "a"
            },
            "layer_2": {
                "field_name": "Layer 2",
                "field_type": "a"
            },
            "layer_3": {
                "field_name": "Layer 3",
                "field_type": "a"
            },
            "layer_4": {
                "field_name": "Layer 4",
                "field_type": "a"
            },
            "layer_5": {
                "field_name": "Layer 5",
                "field_type": "a"
            },
            "layer_6": {
                "field_name": "Layer 6",
                "field_type": "a"
            },
            "layer_7": {
                "field_name": "Layer 7",
                "field_type": "a"
            },
            "layer_8": {
                "field_name": "Layer 8",
                "field_type": "a"
            },
            "layer_9": {
                "field_name": "Layer 9",
                "field_type": "a"
            },
            "layer_10": {
                "field_name": "Layer 10",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "outside_layer",
            "layer_2",
            "layer_3",
            "layer_4",
            "layer_5",
            "layer_6",
            "layer_7",
            "layer_8",
            "layer_9",
            "layer_10"
        ],
        "alphas": {
            "fields": [
                "name",
                "outside_layer",
                "layer_2",
                "layer_3",
                "layer_4",
                "layer_5",
                "layer_6",
                "layer_7",
                "layer_8",
                "layer_9",
                "layer_10"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Start with outside layer and work your way to the inside layer Up to 10 layers total, 8 for windows Enter the material name for each layer"
}
```
