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
                },
                "optional_initial_value": {
                    "type": "number",
                    "note": "If specified, it is used during warm-up and system sizing. If not specified, then the actuator only overwrites the actuated component after the warm-up and system sizing."
                }
            },
            "required": [
                "actuated_component_unique_name",
                "actuated_component_type",
                "actuated_component_control_type"
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
            },
            "optional_initial_value": {
                "field_name": "Optional Initial Value",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "actuated_component_unique_name",
            "actuated_component_type",
            "actuated_component_control_type",
            "optional_initial_value"
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
            "fields": [
                "optional_initial_value"
            ]
        }
    },
    "type": "object",
    "memo": "Hardware portion of EMS used to set up actuators in the model",
    "min_fields": 4.0
}
```
