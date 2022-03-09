```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "boiler_type": {
                    "type": "string",
                    "enum": [
                        "CondensingHotWaterBoiler",
                        "DistrictHotWater",
                        "HotWaterBoiler"
                    ]
                },
                "capacity": {
                    "default": "Autosize",
                    "units": "W",
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
                "efficiency": {
                    "type": "number",
                    "note": "Not applicable  if Boiler Type is DistrictHotWater",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.8
                },
                "fuel_type": {
                    "type": "string",
                    "note": "Not applicable  if Boiler Type is DistrictHotWater",
                    "enum": [
                        "Coal",
                        "Diesel",
                        "Electricity",
                        "FuelOilNo1",
                        "FuelOilNo2",
                        "Gasoline",
                        "NaturalGas",
                        "OtherFuel1",
                        "OtherFuel2",
                        "Propane"
                    ]
                },
                "priority": {
                    "type": "string",
                    "note": "If Hot Water Plant Operation Scheme Type=Default in HVACTemplate:Plant:HotWaterLoop, then equipment operates in priority order, 1, 2, 3, etc."
                },
                "sizing_factor": {
                    "type": "number",
                    "note": "Multiplies the autosized capacity and flow rates",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "minimum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "maximum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 1.1
                },
                "optimum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 1.0
                },
                "water_outlet_upper_temperature_limit": {
                    "type": "number",
                    "units": "C",
                    "default": 100.0
                },
                "template_plant_loop_type": {
                    "type": "string",
                    "note": "Specifies if this boiler serves a template hot water loop or mixed water loop If left blank, will serve a hot water loop if present, or a mixed water loop (if no hot water loop is present).",
                    "enum": [
                        "HotWater",
                        "MixedWater"
                    ]
                }
            },
            "required": [
                "boiler_type"
            ]
        }
    },
    "group": "HVAC Templates",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "boiler_type": {
                "field_name": "Boiler Type",
                "field_type": "a"
            },
            "capacity": {
                "field_name": "Capacity",
                "field_type": "n"
            },
            "efficiency": {
                "field_name": "Efficiency",
                "field_type": "n"
            },
            "fuel_type": {
                "field_name": "Fuel Type",
                "field_type": "a"
            },
            "priority": {
                "field_name": "Priority",
                "field_type": "a"
            },
            "sizing_factor": {
                "field_name": "Sizing Factor",
                "field_type": "n"
            },
            "minimum_part_load_ratio": {
                "field_name": "Minimum Part Load Ratio",
                "field_type": "n"
            },
            "maximum_part_load_ratio": {
                "field_name": "Maximum Part Load Ratio",
                "field_type": "n"
            },
            "optimum_part_load_ratio": {
                "field_name": "Optimum Part Load Ratio",
                "field_type": "n"
            },
            "water_outlet_upper_temperature_limit": {
                "field_name": "Water Outlet Upper Temperature Limit",
                "field_type": "n"
            },
            "template_plant_loop_type": {
                "field_name": "Template Plant Loop Type",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "boiler_type",
            "capacity",
            "efficiency",
            "fuel_type",
            "priority",
            "sizing_factor",
            "minimum_part_load_ratio",
            "maximum_part_load_ratio",
            "optimum_part_load_ratio",
            "water_outlet_upper_temperature_limit",
            "template_plant_loop_type"
        ],
        "alphas": {
            "fields": [
                "name",
                "boiler_type",
                "fuel_type",
                "priority",
                "template_plant_loop_type"
            ]
        },
        "numerics": {
            "fields": [
                "capacity",
                "efficiency",
                "sizing_factor",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "water_outlet_upper_temperature_limit"
            ]
        }
    },
    "type": "object",
    "memo": "This object adds a boiler to an HVACTemplate:Plant:HotWaterLoop or MixedWaterLoop.",
    "min_fields": 7.0
}
```
