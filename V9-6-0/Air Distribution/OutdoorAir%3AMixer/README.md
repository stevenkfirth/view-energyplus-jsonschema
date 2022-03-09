```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "mixed_air_node_name": {
                    "type": "string",
                    "note": "Name of Mixed Air Node"
                },
                "outdoor_air_stream_node_name": {
                    "type": "string",
                    "note": "Name of Outdoor Air Stream Node"
                },
                "relief_air_stream_node_name": {
                    "type": "string",
                    "note": "Name of Relief Air Stream Node"
                },
                "return_air_stream_node_name": {
                    "type": "string",
                    "note": "Name of Return Air Stream Node"
                }
            },
            "required": [
                "mixed_air_node_name",
                "outdoor_air_stream_node_name",
                "relief_air_stream_node_name",
                "return_air_stream_node_name"
            ]
        }
    },
    "group": "Air Distribution",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "OutdoorAirMixers",
            "validOASysEquipmentNames"
        ],
        "reference-class-name": [
            "validOASysEquipmentTypes"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "mixed_air_node_name": {
                "field_name": "Mixed Air Node Name",
                "field_type": "a"
            },
            "outdoor_air_stream_node_name": {
                "field_name": "Outdoor Air Stream Node Name",
                "field_type": "a"
            },
            "relief_air_stream_node_name": {
                "field_name": "Relief Air Stream Node Name",
                "field_type": "a"
            },
            "return_air_stream_node_name": {
                "field_name": "Return Air Stream Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "mixed_air_node_name",
            "outdoor_air_stream_node_name",
            "relief_air_stream_node_name",
            "return_air_stream_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "mixed_air_node_name",
                "outdoor_air_stream_node_name",
                "relief_air_stream_node_name",
                "return_air_stream_node_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Outdoor air mixer. Node names cannot be duplicated within a single OutdoorAir:Mixer object or across all outdoor air mixers."
}
```
