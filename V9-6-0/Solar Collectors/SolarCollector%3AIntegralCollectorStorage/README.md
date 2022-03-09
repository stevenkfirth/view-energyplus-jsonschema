```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "integralcollectorstorageparameters_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CollectorStoragePerformance"
                    ]
                },
                "surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AllShadingAndHTSurfNames"
                    ]
                },
                "bottom_surface_boundary_conditions_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AmbientAir",
                        "OtherSideConditionsModel"
                    ],
                    "default": "AmbientAir"
                },
                "boundary_condition_model_name": {
                    "type": "string",
                    "note": "Enter the name of a SurfaceProperty:OtherSideConditionsModel object. Specified only if the boundary condition type is OtherSideConditionsModel, otherwise leave it blank"
                },
                "inlet_node_name": {
                    "type": "string"
                },
                "outlet_node_name": {
                    "type": "string"
                },
                "maximum_flow_rate": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m3/s",
                    "ip-units": "gal/min"
                }
            },
            "required": [
                "integralcollectorstorageparameters_name",
                "surface_name",
                "inlet_node_name",
                "outlet_node_name"
            ]
        }
    },
    "group": "Solar Collectors",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validPlantEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validPlantEquipmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "integralcollectorstorageparameters_name": {
                "field_name": "IntegralCollectorStorageParameters Name",
                "field_type": "a"
            },
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "bottom_surface_boundary_conditions_type": {
                "field_name": "Bottom Surface Boundary Conditions Type",
                "field_type": "a"
            },
            "boundary_condition_model_name": {
                "field_name": "Boundary Condition Model Name",
                "field_type": "a"
            },
            "inlet_node_name": {
                "field_name": "Inlet Node Name",
                "field_type": "a"
            },
            "outlet_node_name": {
                "field_name": "Outlet Node Name",
                "field_type": "a"
            },
            "maximum_flow_rate": {
                "field_name": "Maximum Flow Rate",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "integralcollectorstorageparameters_name",
            "surface_name",
            "bottom_surface_boundary_conditions_type",
            "boundary_condition_model_name",
            "inlet_node_name",
            "outlet_node_name",
            "maximum_flow_rate"
        ],
        "alphas": {
            "fields": [
                "name",
                "integralcollectorstorageparameters_name",
                "surface_name",
                "bottom_surface_boundary_conditions_type",
                "boundary_condition_model_name",
                "inlet_node_name",
                "outlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Glazed solar collector with integral storage unit. Thermal and optical properties are taken from the referenced SolarCollectorPerformance:IntegralCollectorStorage object. Collector tilt, azimuth, and gross area are taken from the referenced building surface or shading surface. The collector surface participates normally in all shading calculations.",
    "min_fields": 7.0
}
```
