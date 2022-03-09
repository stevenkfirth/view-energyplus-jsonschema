```
{
    "BranchList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "branches": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "branch_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "Branches"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "branch_name"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Node-Branch Management",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "BranchLists"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "branch_name": {
                    "field_name": "Branch Name",
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
                    "branch_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "branch_name"
            ],
            "extension": "branches"
        },
        "type": "object",
        "memo": "Branches MUST be listed in Flow order: Inlet branch, then parallel branches, then Outlet branch. Branches are simulated in the order listed. Branch names cannot be duplicated within a single branch list.",
        "extensible_size": 1.0
    }
}
```
