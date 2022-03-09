```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "construction_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ConstructionNames"
                    ]
                },
                "fluid_inlet_node_name": {
                    "type": "string"
                },
                "fluid_outlet_node_name": {
                    "type": "string"
                },
                "hydronic_tubing_inside_diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "in"
                },
                "number_of_tubing_circuits": {
                    "type": "number",
                    "minimum": 1.0
                },
                "hydronic_tube_spacing": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "surface_length": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "surface_width": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "lower_surface_environment": {
                    "type": "string",
                    "enum": [
                        "",
                        "Exposed",
                        "Ground"
                    ],
                    "default": "Ground"
                }
            },
            "required": [
                "construction_name",
                "fluid_inlet_node_name",
                "fluid_outlet_node_name"
            ]
        }
    },
    "group": "Condenser Equipment and Heat Exchangers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validCondenserEquipmentTypes",
            "validPlantEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validCondenserEquipmentNames",
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
            "construction_name": {
                "field_name": "Construction Name",
                "field_type": "a"
            },
            "fluid_inlet_node_name": {
                "field_name": "Fluid Inlet Node Name",
                "field_type": "a"
            },
            "fluid_outlet_node_name": {
                "field_name": "Fluid Outlet Node Name",
                "field_type": "a"
            },
            "hydronic_tubing_inside_diameter": {
                "field_name": "Hydronic Tubing Inside Diameter",
                "field_type": "n"
            },
            "number_of_tubing_circuits": {
                "field_name": "Number of Tubing Circuits",
                "field_type": "n"
            },
            "hydronic_tube_spacing": {
                "field_name": "Hydronic Tube Spacing",
                "field_type": "n"
            },
            "surface_length": {
                "field_name": "Surface Length",
                "field_type": "n"
            },
            "surface_width": {
                "field_name": "Surface Width",
                "field_type": "n"
            },
            "lower_surface_environment": {
                "field_name": "Lower Surface Environment",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "construction_name",
            "fluid_inlet_node_name",
            "fluid_outlet_node_name",
            "hydronic_tubing_inside_diameter",
            "number_of_tubing_circuits",
            "hydronic_tube_spacing",
            "surface_length",
            "surface_width",
            "lower_surface_environment"
        ],
        "alphas": {
            "fields": [
                "name",
                "construction_name",
                "fluid_inlet_node_name",
                "fluid_outlet_node_name",
                "lower_surface_environment"
            ]
        },
        "numerics": {
            "fields": [
                "hydronic_tubing_inside_diameter",
                "number_of_tubing_circuits",
                "hydronic_tube_spacing",
                "surface_length",
                "surface_width"
            ]
        }
    },
    "type": "object",
    "memo": "A hydronic surface/panel consisting of a multi-layer construction with embedded rows of tubes. Typically used in hybrid geothermal systems and included in the condenser loop. This component may also be used as a simple solar collector. The bottom surface may be defined as ground-coupled or exposed to wind (eg. bridge deck)."
}
```
