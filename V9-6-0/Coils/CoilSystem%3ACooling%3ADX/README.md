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
                "dx_cooling_coil_system_inlet_node_name": {
                    "type": "string"
                },
                "dx_cooling_coil_system_outlet_node_name": {
                    "type": "string"
                },
                "dx_cooling_coil_system_sensor_node_name": {
                    "type": "string"
                },
                "cooling_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:DX:SingleSpeed",
                        "Coil:Cooling:DX:SingleSpeed:ThermalStorage",
                        "Coil:Cooling:DX:TwoSpeed",
                        "Coil:Cooling:DX:TwoStageWithHumidityControlMode",
                        "Coil:Cooling:DX:VariableSpeed",
                        "CoilSystem:Cooling:DX:HeatExchangerAssisted"
                    ]
                },
                "cooling_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsDX",
                        "CoolingCoilsDXVariableSpeed"
                    ]
                },
                "dehumidification_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "CoolReheat",
                        "Multimode",
                        "None"
                    ],
                    "default": "None",
                    "note": "None = meet sensible load only Multimode = activate enhanced dehumidification mode as needed and meet sensible load. If no sensible load exists, and Run on Latent Load = Yes, and a latent load exists, the unit will operate to meet the latent load. Valid only with Coil:Cooling:DX:TwoStageWithHumidityControlMode or CoilSystem:Cooling:DX:HeatExchangerAssisted. CoolReheat = cool beyond the dry-bulb setpoint. as required to meet the humidity setpoint. Valid for all coil types. For all dehumidification controls, the max humidity setpoint on the Sensor Node is used. SetpointManager:SingleZone:Humidity:Maximum, SetpointManager:MultiZone:Humidity:Maximum, or SetpointManager:MultiZone:MaximumHumidity:Average, and SetpointManager:OutdoorAirPretreat (optional) objects."
                },
                "run_on_sensible_load": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes",
                    "note": "If Yes, unit will run if there is a sensible load. If No, unit will not run if there is only a sensible load. Dehumidification controls will be active if specified."
                },
                "run_on_latent_load": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "If Yes, unit will run if there is a latent load. even if there is no sensible load. If No, unit will not run only if there is a latent load. Dehumidification controls will be active if specified."
                },
                "use_outdoor_air_dx_cooling_coil": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "This input field is designed for use with DX cooling coils with low air flow to capacity ratio range (100 - 300 cfm/ton). Typical application is 100% dedicated outdoor air system (DOAS). Other air loop or zone HVAC systems with low flow to capacity ratio range may also use this input field. If Yes, the DX cooling coil runs as 100% DOAS DX coil or low flow to capacity ratio range. If No, the DX cooling coil runs as a regular DX coil. If left blank the default is regular DX coil."
                },
                "outdoor_air_dx_cooling_coil_leaving_minimum_air_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 0.0,
                    "maximum": 7.2,
                    "default": 2.0,
                    "note": "DX cooling coil leaving minimum air temperature defines the minimum DX cooling coil leaving air temperature that should be maintained to avoid frost formation. This input field is optional and only used along with the input field above."
                }
            },
            "required": [
                "dx_cooling_coil_system_inlet_node_name",
                "dx_cooling_coil_system_outlet_node_name",
                "dx_cooling_coil_system_sensor_node_name",
                "cooling_coil_object_type",
                "cooling_coil_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "CoolingCoilSystemName",
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
            "dx_cooling_coil_system_inlet_node_name": {
                "field_name": "DX Cooling Coil System Inlet Node Name",
                "field_type": "a"
            },
            "dx_cooling_coil_system_outlet_node_name": {
                "field_name": "DX Cooling Coil System Outlet Node Name",
                "field_type": "a"
            },
            "dx_cooling_coil_system_sensor_node_name": {
                "field_name": "DX Cooling Coil System Sensor Node Name",
                "field_type": "a"
            },
            "cooling_coil_object_type": {
                "field_name": "Cooling Coil Object Type",
                "field_type": "a"
            },
            "cooling_coil_name": {
                "field_name": "Cooling Coil Name",
                "field_type": "a"
            },
            "dehumidification_control_type": {
                "field_name": "Dehumidification Control Type",
                "field_type": "a"
            },
            "run_on_sensible_load": {
                "field_name": "Run on Sensible Load",
                "field_type": "a"
            },
            "run_on_latent_load": {
                "field_name": "Run on Latent Load",
                "field_type": "a"
            },
            "use_outdoor_air_dx_cooling_coil": {
                "field_name": "Use Outdoor Air DX Cooling Coil",
                "field_type": "a"
            },
            "outdoor_air_dx_cooling_coil_leaving_minimum_air_temperature": {
                "field_name": "Outdoor Air DX Cooling Coil Leaving Minimum Air Temperature",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "dx_cooling_coil_system_inlet_node_name",
            "dx_cooling_coil_system_outlet_node_name",
            "dx_cooling_coil_system_sensor_node_name",
            "cooling_coil_object_type",
            "cooling_coil_name",
            "dehumidification_control_type",
            "run_on_sensible_load",
            "run_on_latent_load",
            "use_outdoor_air_dx_cooling_coil",
            "outdoor_air_dx_cooling_coil_leaving_minimum_air_temperature"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "dx_cooling_coil_system_inlet_node_name",
                "dx_cooling_coil_system_outlet_node_name",
                "dx_cooling_coil_system_sensor_node_name",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "dehumidification_control_type",
                "run_on_sensible_load",
                "run_on_latent_load",
                "use_outdoor_air_dx_cooling_coil"
            ]
        },
        "numerics": {
            "fields": [
                "outdoor_air_dx_cooling_coil_leaving_minimum_air_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "Virtual container component that consists of a DX cooling coil and its associated controls. This control object supports several different types of DX cooling coils and may be placed directly in an air loop branch or outdoor air equipment list.",
    "min_fields": 7.0
}
```
