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
                "desiccant_heat_exchanger_object_type": {
                    "type": "string",
                    "enum": [
                        "HeatExchanger:Desiccant:BalancedFlow"
                    ]
                },
                "desiccant_heat_exchanger_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HXDesiccantBalanced"
                    ]
                },
                "sensor_node_name": {
                    "type": "string"
                },
                "regeneration_air_fan_object_type": {
                    "type": "string",
                    "enum": [
                        "Fan:ConstantVolume",
                        "Fan:OnOff",
                        "Fan:SystemModel"
                    ]
                },
                "regeneration_air_fan_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FansOnOffandVAV",
                        "FansSystemModel"
                    ]
                },
                "regeneration_air_fan_placement": {
                    "type": "string",
                    "enum": [
                        "",
                        "BlowThrough",
                        "DrawThrough"
                    ],
                    "default": "DrawThrough"
                },
                "regeneration_air_heater_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Heating:Electric",
                        "Coil:Heating:Fuel",
                        "Coil:Heating:Steam",
                        "Coil:Heating:Water"
                    ],
                    "note": "works with gas, electric, hot water and steam heating coils. For autosizing the regeneration air heating coil the Design Coil Inlet Air Condition used is the outdoor air condition if the desiccant system is on the primary air loop, or else if the desiccant system is on outdoor air system then it is the return air condition. The Design Coil Outlet Air Temperature is the Regeneration Inlet Air Setpoint Temperature specified in the input field below."
                },
                "regeneration_air_heater_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatingCoilName"
                    ]
                },
                "regeneration_inlet_air_setpoint_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 46.0,
                    "note": "This value is also used as regeneration air heater design coil air outlet temperature for autosizing calculation of the heater."
                },
                "companion_cooling_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:DX:SingleSpeed",
                        "Coil:Cooling:DX:TwoStageWithHumidityControlMode",
                        "Coil:Cooling:DX:VariableSpeed"
                    ]
                },
                "companion_cooling_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsDXMultiModeOrSingleSpeed",
                        "CoolingCoilsDXVariableSpeed"
                    ]
                },
                "companion_cooling_coil_upstream_of_dehumidifier_process_inlet": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "Select Yes if the companion cooling coil is located directly upstream of the desiccant heat exchanger's process air inlet node."
                },
                "companion_coil_regeneration_air_heating": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "exhaust_fan_maximum_flow_rate": {
                    "type": "number",
                    "units": "m3/s"
                },
                "exhaust_fan_maximum_power": {
                    "type": "number",
                    "units": "W"
                },
                "exhaust_fan_power_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "note": "Curve object type must be Curve:Quadratic or Curve:Cubic",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                }
            },
            "required": [
                "desiccant_heat_exchanger_object_type",
                "desiccant_heat_exchanger_name",
                "sensor_node_name",
                "regeneration_air_fan_object_type",
                "regeneration_air_fan_name"
            ]
        }
    },
    "group": "Humidifiers and Dehumidifiers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validOASysEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validOASysEquipmentNames"
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
            "desiccant_heat_exchanger_object_type": {
                "field_name": "Desiccant Heat Exchanger Object Type",
                "field_type": "a"
            },
            "desiccant_heat_exchanger_name": {
                "field_name": "Desiccant Heat Exchanger Name",
                "field_type": "a"
            },
            "sensor_node_name": {
                "field_name": "Sensor Node Name",
                "field_type": "a"
            },
            "regeneration_air_fan_object_type": {
                "field_name": "Regeneration Air Fan Object Type",
                "field_type": "a"
            },
            "regeneration_air_fan_name": {
                "field_name": "Regeneration Air Fan Name",
                "field_type": "a"
            },
            "regeneration_air_fan_placement": {
                "field_name": "Regeneration Air Fan Placement",
                "field_type": "a"
            },
            "regeneration_air_heater_object_type": {
                "field_name": "Regeneration Air Heater Object Type",
                "field_type": "a"
            },
            "regeneration_air_heater_name": {
                "field_name": "Regeneration Air Heater Name",
                "field_type": "a"
            },
            "regeneration_inlet_air_setpoint_temperature": {
                "field_name": "Regeneration Inlet Air Setpoint Temperature",
                "field_type": "n"
            },
            "companion_cooling_coil_object_type": {
                "field_name": "Companion Cooling Coil Object Type",
                "field_type": "a"
            },
            "companion_cooling_coil_name": {
                "field_name": "Companion Cooling Coil Name",
                "field_type": "a"
            },
            "companion_cooling_coil_upstream_of_dehumidifier_process_inlet": {
                "field_name": "Companion Cooling Coil Upstream of Dehumidifier Process Inlet",
                "field_type": "a"
            },
            "companion_coil_regeneration_air_heating": {
                "field_name": "Companion Coil Regeneration Air Heating",
                "field_type": "a"
            },
            "exhaust_fan_maximum_flow_rate": {
                "field_name": "Exhaust Fan Maximum Flow Rate",
                "field_type": "n"
            },
            "exhaust_fan_maximum_power": {
                "field_name": "Exhaust Fan Maximum Power",
                "field_type": "n"
            },
            "exhaust_fan_power_curve_name": {
                "field_name": "Exhaust Fan Power Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "desiccant_heat_exchanger_object_type",
            "desiccant_heat_exchanger_name",
            "sensor_node_name",
            "regeneration_air_fan_object_type",
            "regeneration_air_fan_name",
            "regeneration_air_fan_placement",
            "regeneration_air_heater_object_type",
            "regeneration_air_heater_name",
            "regeneration_inlet_air_setpoint_temperature",
            "companion_cooling_coil_object_type",
            "companion_cooling_coil_name",
            "companion_cooling_coil_upstream_of_dehumidifier_process_inlet",
            "companion_coil_regeneration_air_heating",
            "exhaust_fan_maximum_flow_rate",
            "exhaust_fan_maximum_power",
            "exhaust_fan_power_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "desiccant_heat_exchanger_object_type",
                "desiccant_heat_exchanger_name",
                "sensor_node_name",
                "regeneration_air_fan_object_type",
                "regeneration_air_fan_name",
                "regeneration_air_fan_placement",
                "regeneration_air_heater_object_type",
                "regeneration_air_heater_name",
                "companion_cooling_coil_object_type",
                "companion_cooling_coil_name",
                "companion_cooling_coil_upstream_of_dehumidifier_process_inlet",
                "companion_coil_regeneration_air_heating",
                "exhaust_fan_power_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "regeneration_inlet_air_setpoint_temperature",
                "exhaust_fan_maximum_flow_rate",
                "exhaust_fan_maximum_power"
            ]
        }
    },
    "type": "object",
    "memo": "This compound object models a desiccant heat exchanger, an optional heater, and associated fans. The process air stream is the air which is dehumidified. The regeneration air stream is the air which is heated to regenerate the desiccant. The desiccant heat exchanger transfers both sensible and latent energy between the process and regeneration air streams. The desiccant dehumidifier is typically used in an AirLoopHVAC:OutdoorAirSystem, but can also be specified in any AirLoopHVAC.",
    "min_fields": 8.0
}
```
