```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "inlet_node_name": {
                    "type": "string"
                },
                "outlet_node_name": {
                    "type": "string"
                },
                "design_flow_rate": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m3/s",
                    "ip-units": "gal/min"
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
                },
                "ground_thermal_conductivity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "W/m-K"
                },
                "ground_thermal_heat_capacity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "J/m3-K"
                },
                "ghe_vertical_responsefactors_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "GroundHeatExchangerVerticalResponseFactorNames"
                    ]
                },
                "g_function_calculation_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "UBHWTcalc",
                        "UHFcalc"
                    ],
                    "default": "UHFcalc"
                },
                "ghe_vertical_array_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "GroundHeatExchangerVerticalArrayNames"
                    ]
                },
                "vertical_well_locations": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "ghe_vertical_single_object_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "GroundHeatExchangerVerticalSingleNames"
                                ]
                            }
                        },
                        "type": "object"
                    }
                }
            },
            "required": [
                "inlet_node_name",
                "outlet_node_name",
                "design_flow_rate",
                "undisturbed_ground_temperature_model_type",
                "undisturbed_ground_temperature_model_name",
                "ground_thermal_conductivity",
                "ground_thermal_heat_capacity"
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
            "inlet_node_name": {
                "field_name": "Inlet Node Name",
                "field_type": "a"
            },
            "outlet_node_name": {
                "field_name": "Outlet Node Name",
                "field_type": "a"
            },
            "design_flow_rate": {
                "field_name": "Design Flow Rate",
                "field_type": "n"
            },
            "undisturbed_ground_temperature_model_type": {
                "field_name": "Undisturbed Ground Temperature Model Type",
                "field_type": "a"
            },
            "undisturbed_ground_temperature_model_name": {
                "field_name": "Undisturbed Ground Temperature Model Name",
                "field_type": "a"
            },
            "ground_thermal_conductivity": {
                "field_name": "Ground Thermal Conductivity",
                "field_type": "n"
            },
            "ground_thermal_heat_capacity": {
                "field_name": "Ground Thermal Heat Capacity",
                "field_type": "n"
            },
            "ghe_vertical_responsefactors_object_name": {
                "field_name": "GHE:Vertical:ResponseFactors Object Name",
                "field_type": "a"
            },
            "g_function_calculation_method": {
                "field_name": "g-Function Calculation Method",
                "field_type": "a"
            },
            "ghe_vertical_array_object_name": {
                "field_name": "GHE:Vertical:Array Object Name",
                "field_type": "a"
            },
            "ghe_vertical_single_object_name": {
                "field_name": "GHE:Vertical:Single Object Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "inlet_node_name",
            "outlet_node_name",
            "design_flow_rate",
            "undisturbed_ground_temperature_model_type",
            "undisturbed_ground_temperature_model_name",
            "ground_thermal_conductivity",
            "ground_thermal_heat_capacity",
            "ghe_vertical_responsefactors_object_name",
            "g_function_calculation_method",
            "ghe_vertical_array_object_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "inlet_node_name",
                "outlet_node_name",
                "undisturbed_ground_temperature_model_type",
                "undisturbed_ground_temperature_model_name",
                "ghe_vertical_responsefactors_object_name",
                "g_function_calculation_method",
                "ghe_vertical_array_object_name"
            ],
            "extensions": [
                "ghe_vertical_single_object_name"
            ]
        },
        "numerics": {
            "fields": [
                "design_flow_rate",
                "ground_thermal_conductivity",
                "ground_thermal_heat_capacity"
            ]
        },
        "extensibles": [
            "ghe_vertical_single_object_name"
        ],
        "extension": "vertical_well_locations"
    },
    "type": "object",
    "memo": "Models vertical ground heat exchangers systems using the response factor approach developed by Eskilson. Response factors are calculated using a finite line source model assuming uniform heat flux at the borehole wall if UHFcalc is specified, or uniform borehole wall temperature if UBHWTcalc is specified.",
    "min_fields": 9.0,
    "extensible_size": 1.0
}
```
