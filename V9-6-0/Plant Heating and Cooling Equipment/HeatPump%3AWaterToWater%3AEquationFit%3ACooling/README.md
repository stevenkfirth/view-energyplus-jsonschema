```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "source_side_inlet_node_name": {
                    "type": "string"
                },
                "source_side_outlet_node_name": {
                    "type": "string"
                },
                "load_side_inlet_node_name": {
                    "type": "string"
                },
                "load_side_outlet_node_name": {
                    "type": "string"
                },
                "reference_load_side_flow_rate": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "reference_source_side_flow_rate": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "reference_cooling_capacity": {
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "reference_cooling_power_consumption": {
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "cooling_capacity_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuadvariateFunctions"
                    ]
                },
                "cooling_compressor_power_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuadvariateFunctions"
                    ]
                },
                "reference_coefficient_of_performance": {
                    "type": "number",
                    "note": "This optional field is used to autosize Reference Cooling Power Consumption COP = Rated Cooling Capacity / Rated Cooling Power Consumption",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 8.0
                },
                "sizing_factor": {
                    "type": "number",
                    "note": "Multiplies the autosized capacity and flow rates",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "companion_heating_heat_pump_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WWHPHeatingNames"
                    ],
                    "note": "This optional field is used to coordinate sizing calculations between heating and cooling modes."
                }
            },
            "required": [
                "source_side_inlet_node_name",
                "source_side_outlet_node_name",
                "load_side_inlet_node_name",
                "load_side_outlet_node_name",
                "reference_load_side_flow_rate",
                "reference_source_side_flow_rate",
                "reference_cooling_capacity",
                "reference_cooling_power_consumption",
                "cooling_capacity_curve_name",
                "cooling_compressor_power_curve_name"
            ]
        }
    },
    "group": "Plant Heating and Cooling Equipment",
    "name": {
        "type": "string",
        "reference": [
            "WWHPCoolingNames",
            "validBranchEquipmentNames",
            "validPlantEquipmentNames"
        ],
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validPlantEquipmentTypes"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "source_side_inlet_node_name": {
                "field_name": "Source Side Inlet Node Name",
                "field_type": "a"
            },
            "source_side_outlet_node_name": {
                "field_name": "Source Side Outlet Node Name",
                "field_type": "a"
            },
            "load_side_inlet_node_name": {
                "field_name": "Load Side Inlet Node Name",
                "field_type": "a"
            },
            "load_side_outlet_node_name": {
                "field_name": "Load Side Outlet Node Name",
                "field_type": "a"
            },
            "reference_load_side_flow_rate": {
                "field_name": "Reference Load Side Flow Rate",
                "field_type": "n"
            },
            "reference_source_side_flow_rate": {
                "field_name": "Reference Source Side Flow Rate",
                "field_type": "n"
            },
            "reference_cooling_capacity": {
                "field_name": "Reference Cooling Capacity",
                "field_type": "n"
            },
            "reference_cooling_power_consumption": {
                "field_name": "Reference Cooling Power Consumption",
                "field_type": "n"
            },
            "cooling_capacity_curve_name": {
                "field_name": "Cooling Capacity Curve Name",
                "field_type": "a"
            },
            "cooling_compressor_power_curve_name": {
                "field_name": "Cooling Compressor Power Curve Name",
                "field_type": "a"
            },
            "reference_coefficient_of_performance": {
                "field_name": "Reference Coefficient of Performance",
                "field_type": "n"
            },
            "sizing_factor": {
                "field_name": "Sizing Factor",
                "field_type": "n"
            },
            "companion_heating_heat_pump_name": {
                "field_name": "Companion Heating Heat Pump Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "source_side_inlet_node_name",
            "source_side_outlet_node_name",
            "load_side_inlet_node_name",
            "load_side_outlet_node_name",
            "reference_load_side_flow_rate",
            "reference_source_side_flow_rate",
            "reference_cooling_capacity",
            "reference_cooling_power_consumption",
            "cooling_capacity_curve_name",
            "cooling_compressor_power_curve_name",
            "reference_coefficient_of_performance",
            "sizing_factor",
            "companion_heating_heat_pump_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "source_side_inlet_node_name",
                "source_side_outlet_node_name",
                "load_side_inlet_node_name",
                "load_side_outlet_node_name",
                "cooling_capacity_curve_name",
                "cooling_compressor_power_curve_name",
                "companion_heating_heat_pump_name"
            ]
        },
        "numerics": {
            "fields": [
                "reference_load_side_flow_rate",
                "reference_source_side_flow_rate",
                "reference_cooling_capacity",
                "reference_cooling_power_consumption",
                "reference_coefficient_of_performance",
                "sizing_factor"
            ]
        }
    },
    "type": "object",
    "memo": "simple water-water heat pump curve-fit model",
    "min_fields": 11.0
}
```
