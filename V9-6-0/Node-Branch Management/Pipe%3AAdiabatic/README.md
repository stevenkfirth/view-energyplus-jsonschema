```
{
    "Pipe:Adiabatic": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "inlet_node_name": {
                        "type": "string"
                    },
                    "outlet_node_name": {
                        "type": "string"
                    }
                },
                "required": [
                    "inlet_node_name",
                    "outlet_node_name"
                ]
            }
        },
        "group": "Node-Branch Management",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "inlet_node_name": {
                    "field_name": "Inlet Node Name",
                    "field_type": "a"
                },
                "outlet_node_name": {
                    "field_name": "Outlet Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "inlet_node_name",
                "outlet_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "inlet_node_name",
                    "outlet_node_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Passes Inlet Node state variables to Outlet Node state variables"
    }
}
```
