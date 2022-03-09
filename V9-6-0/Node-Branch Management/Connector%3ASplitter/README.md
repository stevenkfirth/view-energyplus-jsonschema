```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "inlet_branch_name": {
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
                            "outlet_branch_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "Branches"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "outlet_branch_name"
                        ]
                    }
                }
            },
            "required": [
                "inlet_branch_name"
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
            "inlet_branch_name": {
                "field_name": "Inlet Branch Name",
                "field_type": "a"
            },
            "outlet_branch_name": {
                "field_name": "Outlet Branch Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "inlet_branch_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "inlet_branch_name"
            ],
            "extensions": [
                "outlet_branch_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "outlet_branch_name"
        ],
        "extension": "branches"
    },
    "type": "object",
    "memo": "Split one air/water stream into N outlet streams. Branch names cannot be duplicated within a single Splitter list.",
    "min_fields": 3.0,
    "extensible_size": 1.0
}
```
