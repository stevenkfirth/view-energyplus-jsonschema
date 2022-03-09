```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "actuated_component_unique_name": {
                    "type": "string"
                },
                "actuated_component_type": {
                    "type": "string"
                },
                "actuated_component_control_type": {
                    "type": "string"
                }
            },
            "required": [
                "actuated_component_unique_name",
                "actuated_component_type",
                "actuated_component_control_type"
            ]
        }
    },
    "group": "Energy Management System (EMS)",
    "name": {
        "type": "string",
        "is_required": true,
        "note": "This name becomes a variable for use in Erl programs no spaces or other special characters (-,+,/,\\) allowed in name"
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "actuated_component_unique_name": {
                "field_name": "Actuated Component Unique Name",
                "field_type": "a"
            },
            "actuated_component_type": {
                "field_name": "Actuated Component Type",
                "field_type": "a"
            },
            "actuated_component_control_type": {
                "field_name": "Actuated Component Control Type",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "actuated_component_unique_name",
            "actuated_component_type",
            "actuated_component_control_type"
        ],
        "alphas": {
            "fields": [
                "name",
                "actuated_component_unique_name",
                "actuated_component_type",
                "actuated_component_control_type"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Hardware portion of EMS used to set up actuators in the model",
    "min_fields": 4.0
}
```
