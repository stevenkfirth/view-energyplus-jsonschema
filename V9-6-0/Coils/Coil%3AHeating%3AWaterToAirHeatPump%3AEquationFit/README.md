```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
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
                "rated_air_flow_rate": {
                    "units": "m3/s",
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
                "rated_water_flow_rate": {
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
                "gross_rated_heating_capacity": {
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
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
                "gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "heating_capacity_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuadvariateFunctions"
                    ]
                },
                "heating_power_consumption_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuadvariateFunctions"
                    ]
                }
            },
            "required": [
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "rated_air_flow_rate",
                "rated_water_flow_rate",
                "gross_rated_heating_capacity",
                "gross_rated_heating_cop",
                "heating_capacity_curve_name",
                "heating_power_consumption_curve_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "HeatingCoilsWaterToAirHP",
            "validBranchEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
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
            "rated_air_flow_rate": {
                "field_name": "Rated Air Flow Rate",
                "field_type": "n"
            },
            "rated_water_flow_rate": {
                "field_name": "Rated Water Flow Rate",
                "field_type": "n"
            },
            "gross_rated_heating_capacity": {
                "field_name": "Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "gross_rated_heating_cop": {
                "field_name": "Gross Rated Heating COP",
                "field_type": "n"
            },
            "heating_capacity_curve_name": {
                "field_name": "Heating Capacity Curve Name",
                "field_type": "a"
            },
            "heating_power_consumption_curve_name": {
                "field_name": "Heating Power Consumption Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "water_inlet_node_name",
            "water_outlet_node_name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "rated_air_flow_rate",
            "rated_water_flow_rate",
            "gross_rated_heating_capacity",
            "gross_rated_heating_cop",
            "heating_capacity_curve_name",
            "heating_power_consumption_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "heating_capacity_curve_name",
                "heating_power_consumption_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "rated_air_flow_rate",
                "rated_water_flow_rate",
                "gross_rated_heating_capacity",
                "gross_rated_heating_cop"
            ]
        }
    },
    "type": "object",
    "memo": "Direct expansion (DX) heating coil for water-to-air heat pump (includes electric compressor), single-speed, equation-fit model. Equation-fit model uses normalized curves to describe the heat pump performance."
}
```
