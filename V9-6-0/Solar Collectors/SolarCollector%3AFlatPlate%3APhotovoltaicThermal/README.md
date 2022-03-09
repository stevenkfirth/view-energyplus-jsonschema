```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AllShadingAndHTSurfNames"
                    ]
                },
                "photovoltaic_thermal_model_performance_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FlatPlatePVTParameters"
                    ]
                },
                "photovoltaic_name": {
                    "type": "string",
                    "note": "Enter the name of a Generator:Photovoltaic object.",
                    "data_type": "object_list",
                    "object_list": [
                        "PVGeneratorNames"
                    ]
                },
                "thermal_working_fluid_type": {
                    "type": "string",
                    "enum": [
                        "Air",
                        "Water"
                    ]
                },
                "water_inlet_node_name": {
                    "type": "string"
                },
                "water_outlet_node_name": {
                    "type": "string"
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "design_flow_rate": {
                    "units": "m3/s",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                }
            },
            "required": [
                "surface_name"
            ]
        }
    },
    "group": "Solar Collectors",
    "name": {
        "type": "string",
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validOASysEquipmentTypes",
            "validPlantEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validOASysEquipmentNames",
            "validPlantEquipmentNames"
        ]
    },
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "photovoltaic_thermal_model_performance_name": {
                "field_name": "Photovoltaic-Thermal Model Performance Name",
                "field_type": "a"
            },
            "photovoltaic_name": {
                "field_name": "Photovoltaic Name",
                "field_type": "a"
            },
            "thermal_working_fluid_type": {
                "field_name": "Thermal Working Fluid Type",
                "field_type": "a"
            },
            "water_inlet_node_name": {
                "field_name": "Water Inlet Node Name",
                "field_type": "a"
            },
            "water_outlet_node_name": {
                "field_name": "Water Outlet Node Name",
                "field_type": "a"
            },
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "design_flow_rate": {
                "field_name": "Design Flow Rate",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "surface_name",
            "photovoltaic_thermal_model_performance_name",
            "photovoltaic_name",
            "thermal_working_fluid_type",
            "water_inlet_node_name",
            "water_outlet_node_name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "design_flow_rate"
        ],
        "alphas": {
            "fields": [
                "name",
                "surface_name",
                "photovoltaic_thermal_model_performance_name",
                "photovoltaic_name",
                "thermal_working_fluid_type",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "design_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Models hybrid photovoltaic-thermal (PVT) solar collectors that convert incident solar energy into both electricity and useful thermal energy by heating air or water."
}
```
