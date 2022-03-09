```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "cooling_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:Water",
                        "Coil:Cooling:Water:DetailedGeometry",
                        "CoilSystem:Cooling:Water:HeatExchangerAssisted"
                    ]
                },
                "cooling_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsWater"
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
                    "note": "None = meet sensible load only. Valid with all cooling coil types. When a heat  exchanger assisted cooling coil is used, the heat exchanger is locked on at all times.    Multimode = activate water coil and meet sensible load. If no sensible load exists,      and Run on Latent Load = Yes, and a latent load exists, the coil will operate to meet the latent load. If the latent load cannot be met the heat exchanger will be activated. Valid only with cooling coil type CoilSystem:Cooling:Water:HeatExchangerAssisted.    CoolReheat = cool beyond the dry-bulb setpoint as required to meet the humidity setpoint. Valid with all cooling coil types. When a heat exchanger assisted cooling coil is used, the heat exchanger is locked on at all times.       For all dehumidification controls, the max humidity setpoint on the Sensor Node is used. SetpointManager:SingleZone:Humidity:Maximum, SetpointManager:MultiZone:Humidity:Maximum, or SetpointManager:MultiZone:MaximumHumidity:Average, and SetpointManager:OutdoorAirPretreat (optional) objects."
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
                    "note": "If Yes, unit will run if there is a latent load. even if there is no sensible load. If No, unit will not run if there is only a latent load. Dehumidification controls will be active if specified."
                },
                "minimum_air_to_water_temperature_offset": {
                    "type": "number",
                    "note": "Coil will turn on as required when inlet air temperature is above water temperature by amount of offset. To model a waterside economizer connect to condenser loop and increase offset as desired.",
                    "units": "deltaC",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "economizer_lockout": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes",
                    "note": "Yes means that the heat exchanger will be locked out (off)"
                },
                "minimum_water_loop_temperature_for_heat_recovery": {
                    "type": "number",
                    "note": "Only used for heat recovery loops. Loop will turn off below this temperature.",
                    "units": "C",
                    "default": 0.0
                },
                "companion_coil_used_for_heat_recovery": {
                    "type": "string",
                    "note": "Only used for heat recovery loops. Entering a coil name indicates a heat recovery loop is specified. Coil listed is connected in series with this objects coil on demand side  branch of a plant loop. A dedicated plant loop with no supply side equipment, other than a pump, is currently required. Only Coil:Cooling:Water coil type is currently allowed for heat recovery loops.",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsWater"
                    ]
                }
            },
            "required": [
                "air_inlet_node_name",
                "air_outlet_node_name",
                "cooling_coil_object_type",
                "cooling_coil_name"
            ]
        }
    },
    "group": "Coils",
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
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
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
            "minimum_air_to_water_temperature_offset": {
                "field_name": "Minimum Air To Water Temperature Offset",
                "field_type": "n"
            },
            "economizer_lockout": {
                "field_name": "Economizer Lockout",
                "field_type": "a"
            },
            "minimum_water_loop_temperature_for_heat_recovery": {
                "field_name": "Minimum Water Loop Temperature For Heat Recovery",
                "field_type": "n"
            },
            "companion_coil_used_for_heat_recovery": {
                "field_name": "Companion Coil Used For Heat Recovery",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "availability_schedule_name",
            "cooling_coil_object_type",
            "cooling_coil_name",
            "dehumidification_control_type",
            "run_on_sensible_load",
            "run_on_latent_load",
            "minimum_air_to_water_temperature_offset",
            "economizer_lockout",
            "minimum_water_loop_temperature_for_heat_recovery",
            "companion_coil_used_for_heat_recovery"
        ],
        "alphas": {
            "fields": [
                "name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "availability_schedule_name",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "dehumidification_control_type",
                "run_on_sensible_load",
                "run_on_latent_load",
                "economizer_lockout",
                "companion_coil_used_for_heat_recovery"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_air_to_water_temperature_offset",
                "minimum_water_loop_temperature_for_heat_recovery"
            ]
        }
    },
    "type": "object",
    "memo": "Virtual container component that consists of a water cooling coil and its associated controls. This control object supports the available water coil types and may be placed directly on an air loop branch or in an outdoor air equipment list.",
    "min_fields": 10.0
}
```
