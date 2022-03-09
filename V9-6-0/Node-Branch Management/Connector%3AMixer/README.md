```
{
    "Connector:Mixer": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "outlet_branch_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Branches"
                        ]
                    },
                    "branches": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "inlet_branch_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "Branches"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "inlet_branch_name"
                            ]
                        }
                    }
                },
                "required": [
                    "outlet_branch_name"
                ]
            }
        },
        "group": "Node-Branch Management",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "PlantConnectors"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "outlet_branch_name": {
                    "field_name": "Outlet Branch Name",
                    "field_type": "a"
                },
                "inlet_branch_name": {
                    "field_name": "Inlet Branch Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "outlet_branch_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "outlet_branch_name"
                ],
                "extensions": [
                    "inlet_branch_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "inlet_branch_name"
            ],
            "extension": "branches"
        },
        "type": "object",
        "memo": "Mix N inlet air/water streams into one. Branch names cannot be duplicated within a single mixer list.",
        "min_fields": 3.0,
        "extensible_size": 1.0
    }
}
```
