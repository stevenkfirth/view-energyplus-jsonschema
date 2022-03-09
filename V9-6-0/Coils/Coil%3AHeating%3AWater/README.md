```
{
    "Coil:Heating:Water": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "u_factor_times_area_value": {
                        "note": "UA value under rating conditions",
                        "units": "W/K",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "maximum_water_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autosize"
                                ]
                            }
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
                    "performance_input_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "NominalCapacity",
                            "UFactorTimesAreaAndDesignWaterFlowRate"
                        ],
                        "default": "UFactorTimesAreaAndDesignWaterFlowRate"
                    },
                    "rated_capacity": {
                        "units": "W",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "rated_inlet_water_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 82.2
                    },
                    "rated_inlet_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 16.6
                    },
                    "rated_outlet_water_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 71.1
                    },
                    "rated_outlet_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 32.2
                    },
                    "rated_ratio_for_air_and_water_convection": {
                        "type": "number",
                        "default": 0.5,
                        "exclusiveMinimum": 0.0
                    },
                    "design_water_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "exclusiveMinimum": 0.0,
                        "note": "This input field is optional. If specified, it is used for sizing the Design Water Flow Rate. If blank or omitted, the Loop Design Temperature Difference value specified in Sizing:Plant object is used for sizing the Design Water Flow Rate."
                    }
                },
                "required": [
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AFNCoilNames",
                "HeatingCoilName",
                "HeatingCoilsWater",
                "SimpleCoils",
                "validBranchEquipmentNames",
                "validOASysEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validOASysEquipmentTypes"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "u_factor_times_area_value": {
                    "field_name": "U-Factor Times Area Value",
                    "field_type": "n"
                },
                "maximum_water_flow_rate": {
                    "field_name": "Maximum Water Flow Rate",
                    "field_type": "n"
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
                "performance_input_method": {
                    "field_name": "Performance Input Method",
                    "field_type": "a"
                },
                "rated_capacity": {
                    "field_name": "Rated Capacity",
                    "field_type": "n"
                },
                "rated_inlet_water_temperature": {
                    "field_name": "Rated Inlet Water Temperature",
                    "field_type": "n"
                },
                "rated_inlet_air_temperature": {
                    "field_name": "Rated Inlet Air Temperature",
                    "field_type": "n"
                },
                "rated_outlet_water_temperature": {
                    "field_name": "Rated Outlet Water Temperature",
                    "field_type": "n"
                },
                "rated_outlet_air_temperature": {
                    "field_name": "Rated Outlet Air Temperature",
                    "field_type": "n"
                },
                "rated_ratio_for_air_and_water_convection": {
                    "field_name": "Rated Ratio for Air and Water Convection",
                    "field_type": "n"
                },
                "design_water_temperature_difference": {
                    "field_name": "Design Water Temperature Difference",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "u_factor_times_area_value",
                "maximum_water_flow_rate",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "performance_input_method",
                "rated_capacity",
                "rated_inlet_water_temperature",
                "rated_inlet_air_temperature",
                "rated_outlet_water_temperature",
                "rated_outlet_air_temperature",
                "rated_ratio_for_air_and_water_convection",
                "design_water_temperature_difference"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "performance_input_method"
                ]
            },
            "numerics": {
                "fields": [
                    "u_factor_times_area_value",
                    "maximum_water_flow_rate",
                    "rated_capacity",
                    "rated_inlet_water_temperature",
                    "rated_inlet_air_temperature",
                    "rated_outlet_water_temperature",
                    "rated_outlet_air_temperature",
                    "rated_ratio_for_air_and_water_convection",
                    "design_water_temperature_difference"
                ]
            }
        },
        "type": "object",
        "memo": "Hot water heating coil, NTU-effectiveness model, assumes a cross-flow heat exchanger. Two options for capacity inputs: UA and water flow rate or capacity and design temperatures.",
        "min_fields": 15.0
    }
}
```
