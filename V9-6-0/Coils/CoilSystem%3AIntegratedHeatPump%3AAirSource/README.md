```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "supply_hot_water_flow_sensor_node_name": {
                    "type": "string"
                },
                "space_cooling_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsDXVariableSpeed"
                    ],
                    "note": "Must match the name used in the corresponding Coil:Cooling:DX:VariableSpeed object."
                },
                "space_heating_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatingCoilsDXVariableSpeed"
                    ],
                    "note": "Must match the name used in the corresponding Coil:Heating:DX:VariableSpeed object."
                },
                "dedicated_water_heating_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatPumpWaterHeaterDXCoilsVariableSpeed"
                    ],
                    "note": "Must match the name used in the corresponding Coil:WaterHeating:AirToWaterHeatPump:VariableSpeed object."
                },
                "scwh_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatPumpWaterHeaterDXCoilsVariableSpeed"
                    ],
                    "note": "Must match the name used in the corresponding Coil:WaterHeating:AirToWaterHeatPump:VariableSpeed object."
                },
                "scdwh_cooling_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsDXVariableSpeed"
                    ],
                    "note": "Must match the name used in the corresponding Coil:Cooling:DX:VariableSpeed object."
                },
                "scdwh_water_heating_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatPumpWaterHeaterDXCoilsVariableSpeed"
                    ],
                    "note": "Must match the name used in the corresponding Coil:WaterHeating:AirToWaterHeatPump:VariableSpeed object."
                },
                "shdwh_heating_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatingCoilsDXVariableSpeed"
                    ],
                    "note": "Must match the name used in the corresponding Coil:Heating:DX:VariableSpeed object."
                },
                "shdwh_water_heating_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatPumpWaterHeaterDXCoilsVariableSpeed"
                    ],
                    "note": "Must match the name used in the corresponding Coil:WaterHeating:AirToWaterHeatPump:VariableSpeed object."
                },
                "indoor_temperature_limit_for_scwh_mode": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 15.0,
                    "default": 20.0,
                    "note": "Indoor Temperature above which Indoor Overcooling is Allowed during Cooling Operation"
                },
                "ambient_temperature_limit_for_scwh_mode": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 20.0,
                    "default": 27.0,
                    "note": "Ambient Temperature above which Indoor Overcooling is Allowed during Cooling Operation"
                },
                "indoor_temperature_above_which_wh_has_higher_priority": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 15.0,
                    "default": 20.0,
                    "note": "Indoor Temperature above which Water Heating has the higher priority and Space Heating Call Can be ignored."
                },
                "ambient_temperature_above_which_wh_has_higher_priority": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 15.0,
                    "default": 20.0,
                    "note": "Ambient Temperature above which Water Heating has the higher priority and Space Heating Call Can be ignored."
                },
                "flag_to_indicate_load_control_in_scwh_mode": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 0.0,
                    "note": "0: match space cooling load in SCWH mode, 1: match water heating load in SCWH mode"
                },
                "minimum_speed_level_for_scwh_mode": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 10.0
                },
                "maximum_water_flow_volume_before_switching_from_scdwh_to_scwh_mode": {
                    "type": "number",
                    "units": "m3",
                    "default": 0.0
                },
                "minimum_speed_level_for_scdwh_mode": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 10.0
                },
                "maximum_running_time_before_allowing_electric_resistance_heat_use_during_shdwh_mode": {
                    "type": "number",
                    "units": "s",
                    "exclusiveMinimum": 0.0,
                    "default": 360.0
                },
                "minimum_speed_level_for_shdwh_mode": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 10.0
                }
            },
            "required": [
                "supply_hot_water_flow_sensor_node_name",
                "space_cooling_coil_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "IntegratedHeatPumps"
        ],
        "note": "Unique name for this instance of an air-source integrated heat pump."
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "supply_hot_water_flow_sensor_node_name": {
                "field_name": "Supply Hot Water Flow Sensor Node Name",
                "field_type": "a"
            },
            "space_cooling_coil_name": {
                "field_name": "Space Cooling Coil  Name",
                "field_type": "a"
            },
            "space_heating_coil_name": {
                "field_name": "Space Heating Coil Name",
                "field_type": "a"
            },
            "dedicated_water_heating_coil_name": {
                "field_name": "Dedicated Water Heating Coil Name",
                "field_type": "a"
            },
            "scwh_coil_name": {
                "field_name": "SCWH Coil Name",
                "field_type": "a"
            },
            "scdwh_cooling_coil_name": {
                "field_name": "SCDWH Cooling Coil Name",
                "field_type": "a"
            },
            "scdwh_water_heating_coil_name": {
                "field_name": "SCDWH Water Heating Coil Name",
                "field_type": "a"
            },
            "shdwh_heating_coil_name": {
                "field_name": "SHDWH Heating Coil Name",
                "field_type": "a"
            },
            "shdwh_water_heating_coil_name": {
                "field_name": "SHDWH Water Heating Coil Name",
                "field_type": "a"
            },
            "indoor_temperature_limit_for_scwh_mode": {
                "field_name": "Indoor Temperature Limit for SCWH Mode",
                "field_type": "n"
            },
            "ambient_temperature_limit_for_scwh_mode": {
                "field_name": "Ambient Temperature Limit for SCWH Mode",
                "field_type": "n"
            },
            "indoor_temperature_above_which_wh_has_higher_priority": {
                "field_name": "Indoor Temperature above Which WH has Higher Priority",
                "field_type": "n"
            },
            "ambient_temperature_above_which_wh_has_higher_priority": {
                "field_name": "Ambient Temperature above Which WH has Higher Priority",
                "field_type": "n"
            },
            "flag_to_indicate_load_control_in_scwh_mode": {
                "field_name": "Flag to Indicate Load Control in SCWH Mode",
                "field_type": "n"
            },
            "minimum_speed_level_for_scwh_mode": {
                "field_name": "Minimum Speed Level for SCWH Mode",
                "field_type": "n"
            },
            "maximum_water_flow_volume_before_switching_from_scdwh_to_scwh_mode": {
                "field_name": "Maximum Water Flow Volume before Switching from SCDWH to SCWH Mode",
                "field_type": "n"
            },
            "minimum_speed_level_for_scdwh_mode": {
                "field_name": "Minimum Speed Level for SCDWH Mode",
                "field_type": "n"
            },
            "maximum_running_time_before_allowing_electric_resistance_heat_use_during_shdwh_mode": {
                "field_name": "Maximum Running Time before Allowing Electric Resistance Heat Use during SHDWH Mode",
                "field_type": "n"
            },
            "minimum_speed_level_for_shdwh_mode": {
                "field_name": "Minimum Speed Level for SHDWH Mode",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "supply_hot_water_flow_sensor_node_name",
            "space_cooling_coil_name",
            "space_heating_coil_name",
            "dedicated_water_heating_coil_name",
            "scwh_coil_name",
            "scdwh_cooling_coil_name",
            "scdwh_water_heating_coil_name",
            "shdwh_heating_coil_name",
            "shdwh_water_heating_coil_name",
            "indoor_temperature_limit_for_scwh_mode",
            "ambient_temperature_limit_for_scwh_mode",
            "indoor_temperature_above_which_wh_has_higher_priority",
            "ambient_temperature_above_which_wh_has_higher_priority",
            "flag_to_indicate_load_control_in_scwh_mode",
            "minimum_speed_level_for_scwh_mode",
            "maximum_water_flow_volume_before_switching_from_scdwh_to_scwh_mode",
            "minimum_speed_level_for_scdwh_mode",
            "maximum_running_time_before_allowing_electric_resistance_heat_use_during_shdwh_mode",
            "minimum_speed_level_for_shdwh_mode"
        ],
        "alphas": {
            "fields": [
                "name",
                "supply_hot_water_flow_sensor_node_name",
                "space_cooling_coil_name",
                "space_heating_coil_name",
                "dedicated_water_heating_coil_name",
                "scwh_coil_name",
                "scdwh_cooling_coil_name",
                "scdwh_water_heating_coil_name",
                "shdwh_heating_coil_name",
                "shdwh_water_heating_coil_name"
            ]
        },
        "numerics": {
            "fields": [
                "indoor_temperature_limit_for_scwh_mode",
                "ambient_temperature_limit_for_scwh_mode",
                "indoor_temperature_above_which_wh_has_higher_priority",
                "ambient_temperature_above_which_wh_has_higher_priority",
                "flag_to_indicate_load_control_in_scwh_mode",
                "minimum_speed_level_for_scwh_mode",
                "maximum_water_flow_volume_before_switching_from_scdwh_to_scwh_mode",
                "minimum_speed_level_for_scdwh_mode",
                "maximum_running_time_before_allowing_electric_resistance_heat_use_during_shdwh_mode",
                "minimum_speed_level_for_shdwh_mode"
            ]
        }
    },
    "type": "object",
    "memo": "This object is used for air-source integrated heat pump, a collection of its working modes."
}
```
