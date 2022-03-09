```
{
    "ExternalInterface:FunctionalMockupUnitImport:To:Actuator": {
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
                    "fmu_file_name": {
                        "type": "string",
                        "retaincase": true,
                        "data_type": "object_list",
                        "object_list": [
                            "FMUFileName"
                        ]
                    },
                    "fmu_instance_name": {
                        "type": "string",
                        "retaincase": true
                    },
                    "fmu_variable_name": {
                        "type": "string",
                        "retaincase": true
                    },
                    "initial_value": {
                        "type": "number",
                        "note": "Used during the first call of EnergyPlus."
                    }
                },
                "required": [
                    "actuated_component_unique_name",
                    "actuated_component_type",
                    "actuated_component_control_type",
                    "fmu_file_name",
                    "fmu_instance_name",
                    "fmu_variable_name",
                    "initial_value"
                ]
            }
        },
        "group": "External Interface",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "This name becomes a read-only variable for use in Erl programs no spaces allowed in name"
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
                "fmu_file_name": {
                    "field_name": "FMU File Name",
                    "field_type": "a"
                },
                "fmu_instance_name": {
                    "field_name": "FMU Instance Name",
                    "field_type": "a"
                },
                "fmu_variable_name": {
                    "field_name": "FMU Variable Name",
                    "field_type": "a"
                },
                "initial_value": {
                    "field_name": "Initial Value",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "actuated_component_unique_name",
                "actuated_component_type",
                "actuated_component_control_type",
                "fmu_file_name",
                "fmu_instance_name",
                "fmu_variable_name",
                "initial_value"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "actuated_component_unique_name",
                    "actuated_component_type",
                    "actuated_component_control_type",
                    "fmu_file_name",
                    "fmu_instance_name",
                    "fmu_variable_name"
                ]
            },
            "numerics": {
                "fields": [
                    "initial_value"
                ]
            }
        },
        "type": "object",
        "memo": "Hardware portion of EMS used to set up actuators in the model that are dynamically updated from the FMU.",
        "min_fields": 8.0
    }
}
```
