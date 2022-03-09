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
                "sun_exposure": {
                    "type": "string",
                    "enum": [
                        "NoSun",
                        "SunExposed"
                    ]
                },
                "pipe_inside_diameter": {
                    "type": "number",
                    "note": "pipe thickness is defined in the Construction object",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "in"
                },
                "pipe_length": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "soil_material_name": {
                    "type": "string"
                },
                "undisturbed_ground_temperature_model_type": {
                    "type": "string",
                    "enum": [
                        "Site:GroundTemperature:Undisturbed:FiniteDifference",
                        "Site:GroundTemperature:Undisturbed:KusudaAchenbach",
                        "Site:GroundTemperature:Undisturbed:Xing"
                    ]
                },
                "undisturbed_ground_temperature_model_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UndisturbedGroundTempModels"
                    ]
                }
            },
            "required": [
                "construction_name",
                "fluid_inlet_node_name",
                "fluid_outlet_node_name",
                "sun_exposure",
                "soil_material_name",
                "undisturbed_ground_temperature_model_type",
                "undisturbed_ground_temperature_model_name"
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
            "sun_exposure": {
                "field_name": "Sun Exposure",
                "field_type": "a"
            },
            "pipe_inside_diameter": {
                "field_name": "Pipe Inside Diameter",
                "field_type": "n"
            },
            "pipe_length": {
                "field_name": "Pipe Length",
                "field_type": "n"
            },
            "soil_material_name": {
                "field_name": "Soil Material Name",
                "field_type": "a"
            },
            "undisturbed_ground_temperature_model_type": {
                "field_name": "Undisturbed Ground Temperature Model Type",
                "field_type": "a"
            },
            "undisturbed_ground_temperature_model_name": {
                "field_name": "Undisturbed Ground Temperature Model Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "construction_name",
            "fluid_inlet_node_name",
            "fluid_outlet_node_name",
            "sun_exposure",
            "pipe_inside_diameter",
            "pipe_length",
            "soil_material_name",
            "undisturbed_ground_temperature_model_type",
            "undisturbed_ground_temperature_model_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "construction_name",
                "fluid_inlet_node_name",
                "fluid_outlet_node_name",
                "sun_exposure",
                "soil_material_name",
                "undisturbed_ground_temperature_model_type",
                "undisturbed_ground_temperature_model_name"
            ]
        },
        "numerics": {
            "fields": [
                "pipe_inside_diameter",
                "pipe_length"
            ]
        }
    },
    "type": "object",
    "memo": "Buried Pipe model: For pipes buried at a depth less than one meter, this is an alternative object to: HeatExchanger:Surface"
}
```
