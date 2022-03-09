```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "water_inlet_node_name": {
                    "type": "string",
                    "note": "Name of fluid cooler water inlet node"
                },
                "water_outlet_node_name": {
                    "type": "string",
                    "note": "Name of fluid cooler water outlet node"
                },
                "performance_input_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "NominalCapacity",
                        "UFactorTimesAreaAndDesignWaterFlowRate"
                    ],
                    "default": "NominalCapacity",
                    "note": "User can define fluid cooler thermal performance by specifying the fluid cooler UA and the Design Water Flow Rate, or by specifying the fluid cooler nominal capacity"
                },
                "design_air_flow_rate_u_factor_times_area_value": {
                    "units": "W/K",
                    "note": "Leave field blank if fluid cooler Performance Input Method is NominalCapacity",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0,
                            "maximum": 2100000.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "nominal_capacity": {
                    "type": "number",
                    "units": "W",
                    "exclusiveMinimum": 0.0,
                    "note": "Nominal fluid cooler capacity"
                },
                "design_entering_water_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "F",
                    "note": "Design Entering Water Temperature must be specified for both the performance input methods and its value must be greater than Design Entering Air Temperature."
                },
                "design_entering_air_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "F",
                    "note": "Design Entering Air Temperature must be specified for both the performance input methods and its value must be greater than Design Entering Air Wet-bulb Temperature."
                },
                "design_entering_air_wetbulb_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "F",
                    "note": "Design Entering Air Wet-bulb Temperature must be specified for both the performance input methods and its value must be less than Design Entering Air Temperature."
                },
                "design_water_flow_rate": {
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
                "design_air_flow_rate": {
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
                "design_air_flow_rate_fan_power": {
                    "units": "W",
                    "ip-units": "W",
                    "note": "This is the fan motor electric input power",
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
                "outdoor_air_inlet_node_name": {
                    "type": "string",
                    "note": "Enter the name of an outdoor air node"
                }
            },
            "required": [
                "water_inlet_node_name",
                "water_outlet_node_name",
                "design_entering_water_temperature",
                "design_entering_air_temperature",
                "design_entering_air_wetbulb_temperature",
                "design_water_flow_rate",
                "design_air_flow_rate",
                "design_air_flow_rate_fan_power"
            ]
        }
    },
    "group": "Condenser Equipment and Heat Exchangers",
    "name": {
        "type": "string",
        "is_required": true,
        "note": "fluid cooler name",
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
            "water_inlet_node_name": {
                "field_name": "Water Inlet Node Name",
                "field_type": "a"
            },
            "water_outlet_node_name": {
                "field_name": "Water Outlet Node Name",
                "field_type": "a"
            },
            "performance_input_method": {
                "field_name": "Performance Input Method",
                "field_type": "a"
            },
            "design_air_flow_rate_u_factor_times_area_value": {
                "field_name": "Design Air Flow Rate U-factor Times Area Value",
                "field_type": "n"
            },
            "nominal_capacity": {
                "field_name": "Nominal Capacity",
                "field_type": "n"
            },
            "design_entering_water_temperature": {
                "field_name": "Design Entering Water Temperature",
                "field_type": "n"
            },
            "design_entering_air_temperature": {
                "field_name": "Design Entering Air Temperature",
                "field_type": "n"
            },
            "design_entering_air_wetbulb_temperature": {
                "field_name": "Design Entering Air Wetbulb Temperature",
                "field_type": "n"
            },
            "design_water_flow_rate": {
                "field_name": "Design Water Flow Rate",
                "field_type": "n"
            },
            "design_air_flow_rate": {
                "field_name": "Design Air Flow Rate",
                "field_type": "n"
            },
            "design_air_flow_rate_fan_power": {
                "field_name": "Design Air Flow Rate Fan Power",
                "field_type": "n"
            },
            "outdoor_air_inlet_node_name": {
                "field_name": "Outdoor Air Inlet Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "water_inlet_node_name",
            "water_outlet_node_name",
            "performance_input_method",
            "design_air_flow_rate_u_factor_times_area_value",
            "nominal_capacity",
            "design_entering_water_temperature",
            "design_entering_air_temperature",
            "design_entering_air_wetbulb_temperature",
            "design_water_flow_rate",
            "design_air_flow_rate",
            "design_air_flow_rate_fan_power",
            "outdoor_air_inlet_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "performance_input_method",
                "outdoor_air_inlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "design_air_flow_rate_u_factor_times_area_value",
                "nominal_capacity",
                "design_entering_water_temperature",
                "design_entering_air_temperature",
                "design_entering_air_wetbulb_temperature",
                "design_water_flow_rate",
                "design_air_flow_rate",
                "design_air_flow_rate_fan_power"
            ]
        }
    },
    "type": "object",
    "memo": "The fluid cooler is modeled as a cross flow heat exchanger (both streams unmixed) with single-speed fans (induced draft configuration).",
    "min_fields": 12.0
}
```
