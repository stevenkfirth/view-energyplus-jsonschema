```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "pressure_drop_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Optional field to include this branch in plant pressure drop calculations This field is only relevant for branches in PlantLoops and CondenserLoops Air loops do not account for pressure drop using this field Valid curve types are: Curve:Functional:PressureDrop or one of Curve:{Linear,Quadratic,Cubic,Exponent}')"
                },
                "components": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "component_object_type": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "validBranchEquipmentTypes"
                                ]
                            },
                            "component_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "validBranchEquipmentNames"
                                ]
                            },
                            "component_inlet_node_name": {
                                "type": "string"
                            },
                            "component_outlet_node_name": {
                                "type": "string"
                            }
                        },
                        "type": "object",
                        "required": [
                            "component_inlet_node_name",
                            "component_name",
                            "component_object_type",
                            "component_outlet_node_name"
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
            "Branches"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "pressure_drop_curve_name": {
                "field_name": "Pressure Drop Curve Name",
                "field_type": "a"
            },
            "component_object_type": {
                "field_name": "Component Object Type",
                "field_type": "a"
            },
            "component_name": {
                "field_name": "Component Name",
                "field_type": "a"
            },
            "component_inlet_node_name": {
                "field_name": "Component Inlet Node Name",
                "field_type": "a"
            },
            "component_outlet_node_name": {
                "field_name": "Component Outlet Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "pressure_drop_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "pressure_drop_curve_name"
            ],
            "extensions": [
                "component_object_type",
                "component_name",
                "component_inlet_node_name",
                "component_outlet_node_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "component_object_type",
            "component_name",
            "component_inlet_node_name",
            "component_outlet_node_name"
        ],
        "extension": "components"
    },
    "type": "object",
    "memo": "List components on the branch in simulation and connection order Note: this should NOT include splitters or mixers which define endpoints of branches",
    "extensible_size": 4.0
}
```
