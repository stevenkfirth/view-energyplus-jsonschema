```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "reformer_water_flow_rate_function_of_fuel_rate_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "reformer_water_pump_power_function_of_fuel_rate_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "pump_heat_loss_factor": {
                    "type": "number"
                },
                "water_temperature_modeling_mode": {
                    "type": "string",
                    "enum": [
                        "MainsWaterTemperature",
                        "TemperatureFromAirNode",
                        "TemperatureFromSchedule",
                        "TemperatureFromWaterNode"
                    ]
                },
                "water_temperature_reference_node_name": {
                    "type": "string"
                },
                "water_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            }
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "FCWaterSupNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "reformer_water_flow_rate_function_of_fuel_rate_curve_name": {
                "field_name": "Reformer Water Flow Rate Function of Fuel Rate Curve Name",
                "field_type": "a"
            },
            "reformer_water_pump_power_function_of_fuel_rate_curve_name": {
                "field_name": "Reformer Water Pump Power Function of Fuel Rate Curve Name",
                "field_type": "a"
            },
            "pump_heat_loss_factor": {
                "field_name": "Pump Heat Loss Factor",
                "field_type": "n"
            },
            "water_temperature_modeling_mode": {
                "field_name": "Water Temperature Modeling Mode",
                "field_type": "a"
            },
            "water_temperature_reference_node_name": {
                "field_name": "Water Temperature Reference Node Name",
                "field_type": "a"
            },
            "water_temperature_schedule_name": {
                "field_name": "Water Temperature Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "reformer_water_flow_rate_function_of_fuel_rate_curve_name",
            "reformer_water_pump_power_function_of_fuel_rate_curve_name",
            "pump_heat_loss_factor",
            "water_temperature_modeling_mode",
            "water_temperature_reference_node_name",
            "water_temperature_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "reformer_water_flow_rate_function_of_fuel_rate_curve_name",
                "reformer_water_pump_power_function_of_fuel_rate_curve_name",
                "water_temperature_modeling_mode",
                "water_temperature_reference_node_name",
                "water_temperature_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "pump_heat_loss_factor"
            ]
        }
    },
    "type": "object",
    "memo": "Used to provide details of the water supply subsystem for a fuel cell power generator. This water is used for steam reforming of the fuel and is not the same as the water used for thermal heat recovery."
}
```
