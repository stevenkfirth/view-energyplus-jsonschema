```
{
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
                "design_water_flow_rate": {
                    "units": "m3/s",
                    "default": "Autosize",
                    "ip-units": "gal/min",
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
                "design_air_flow_rate": {
                    "units": "m3/s",
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
                "design_inlet_water_temperature": {
                    "units": "C",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
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
                "design_inlet_air_temperature": {
                    "units": "C",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
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
                "design_outlet_air_temperature": {
                    "units": "C",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
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
                "design_inlet_air_humidity_ratio": {
                    "units": "kgWater/kgDryAir",
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
                "design_outlet_air_humidity_ratio": {
                    "units": "kgWater/kgDryAir",
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
                "type_of_analysis": {
                    "type": "string",
                    "enum": [
                        "",
                        "DetailedAnalysis",
                        "SimpleAnalysis"
                    ],
                    "default": "SimpleAnalysis"
                },
                "heat_exchanger_configuration": {
                    "type": "string",
                    "enum": [
                        "",
                        "CounterFlow",
                        "CrossFlow"
                    ],
                    "default": "CounterFlow"
                },
                "condensate_collection_water_storage_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
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
            "CoolingCoilName",
            "CoolingCoilsWater",
            "CoolingCoilsWaterNoHX",
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
            "design_water_flow_rate": {
                "field_name": "Design Water Flow Rate",
                "field_type": "n"
            },
            "design_air_flow_rate": {
                "field_name": "Design Air Flow Rate",
                "field_type": "n"
            },
            "design_inlet_water_temperature": {
                "field_name": "Design Inlet Water Temperature",
                "field_type": "n"
            },
            "design_inlet_air_temperature": {
                "field_name": "Design Inlet Air Temperature",
                "field_type": "n"
            },
            "design_outlet_air_temperature": {
                "field_name": "Design Outlet Air Temperature",
                "field_type": "n"
            },
            "design_inlet_air_humidity_ratio": {
                "field_name": "Design Inlet Air Humidity Ratio",
                "field_type": "n"
            },
            "design_outlet_air_humidity_ratio": {
                "field_name": "Design Outlet Air Humidity Ratio",
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
            "type_of_analysis": {
                "field_name": "Type of Analysis",
                "field_type": "a"
            },
            "heat_exchanger_configuration": {
                "field_name": "Heat Exchanger Configuration",
                "field_type": "a"
            },
            "condensate_collection_water_storage_tank_name": {
                "field_name": "Condensate Collection Water Storage Tank Name",
                "field_type": "a"
            },
            "design_water_temperature_difference": {
                "field_name": "Design Water Temperature Difference",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "design_water_flow_rate",
            "design_air_flow_rate",
            "design_inlet_water_temperature",
            "design_inlet_air_temperature",
            "design_outlet_air_temperature",
            "design_inlet_air_humidity_ratio",
            "design_outlet_air_humidity_ratio",
            "water_inlet_node_name",
            "water_outlet_node_name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "type_of_analysis",
            "heat_exchanger_configuration",
            "condensate_collection_water_storage_tank_name",
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
                "type_of_analysis",
                "heat_exchanger_configuration",
                "condensate_collection_water_storage_tank_name"
            ]
        },
        "numerics": {
            "fields": [
                "design_water_flow_rate",
                "design_air_flow_rate",
                "design_inlet_water_temperature",
                "design_inlet_air_temperature",
                "design_outlet_air_temperature",
                "design_inlet_air_humidity_ratio",
                "design_outlet_air_humidity_ratio",
                "design_water_temperature_difference"
            ]
        }
    },
    "type": "object",
    "memo": "Chilled water cooling coil, NTU-effectiveness model, with inputs for design entering and leaving conditions.",
    "min_fields": 15.0
}
```
