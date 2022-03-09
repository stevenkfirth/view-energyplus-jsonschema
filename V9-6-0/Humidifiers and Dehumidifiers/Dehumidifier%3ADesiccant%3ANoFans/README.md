```
{
    "Dehumidifier:Desiccant:NoFans": {
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
                    "process_air_inlet_node_name": {
                        "type": "string",
                        "note": "This is the node entering the process side of the desiccant wheel."
                    },
                    "process_air_outlet_node_name": {
                        "type": "string",
                        "note": "This is the node leaving the process side of the desiccant wheel."
                    },
                    "regeneration_air_inlet_node_name": {
                        "type": "string",
                        "note": "This is the node entering the regeneration side of the desiccant wheel after the regeneration coil."
                    },
                    "regeneration_fan_inlet_node_name": {
                        "type": "string",
                        "note": "Node for air entering the regeneration fan, mass flow is set by the desiccant dehumidifier module."
                    },
                    "control_type": {
                        "type": "string",
                        "note": "Type of setpoint control: LeavingMaximumHumidityRatioSetpoint means that the unit is controlled to deliver air at the Leaving Max Humidity Ratio Setpoint (see below), SystemNodeMaximumHumidityRatioSetpoint means that the leaving humidity ratio setpoint is the System Node Humidity Ratio Max property of the Process Air Outlet Node. A Setpoint object must be used to control this setpoint. Both control types use bypass dampers to prevent over drying.",
                        "enum": [
                            "LeavingMaximumHumidityRatioSetpoint",
                            "SystemNodeMaximumHumidityRatioSetpoint"
                        ]
                    },
                    "leaving_maximum_humidity_ratio_setpoint": {
                        "type": "number",
                        "note": "Fixed setpoint for maximum process air leaving humidity ratio Applicable only when Control Type = LeavingMaximumHumidityRatioSetpoint.",
                        "units": "kgWater/kgDryAir"
                    },
                    "nominal_process_air_flow_rate": {
                        "type": "number",
                        "note": "Process air flow rate at nominal conditions",
                        "units": "m3/s",
                        "exclusiveMinimum": 0.0
                    },
                    "nominal_process_air_velocity": {
                        "type": "number",
                        "note": "Process air velocity at nominal flow When using Performance Model Type of Default, must be 2.032 to 4.064 m/s (400 to 800 fpm)",
                        "units": "m/s",
                        "exclusiveMinimum": 0.0,
                        "maximum": 6.0
                    },
                    "rotor_power": {
                        "type": "number",
                        "note": "Power input to wheel rotor motor",
                        "units": "W",
                        "minimum": 0.0,
                        "ip-units": "W"
                    },
                    "regeneration_coil_object_type": {
                        "type": "string",
                        "note": "heating coil type works with gas, electric, hot water and steam heating coils",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ]
                    },
                    "regeneration_coil_name": {
                        "type": "string",
                        "note": "Name of heating coil object for regeneration air",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName"
                        ]
                    },
                    "regeneration_fan_object_type": {
                        "type": "string",
                        "note": "Type of fan object for regeneration air. When using the Default Performance Model Type (see below), only Fan:VariableVolume or Fan:SystemModel are valid.",
                        "enum": [
                            "Fan:ConstantVolume",
                            "Fan:SystemModel",
                            "Fan:VariableVolume"
                        ]
                    },
                    "regeneration_fan_name": {
                        "type": "string",
                        "note": "Name of fan object for regeneration air",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandVAV",
                            "FansSystemModel"
                        ]
                    },
                    "performance_model_type": {
                        "type": "string",
                        "note": "Specifies whether the default performance model or user-specified curves should be used to model the performance. The default model is a generic solid desiccant wheel using performance curves of the form: curve = C1 + C2*edb + C3*edb**2 + C4*ew + C5*ew**2 + C6*vel + C7*vel**2 + C8*edb*ew + C9*edb**2*ew**2 + C10*edb*vel + C11*edb**2*vel**2 + C12*ew*vel + C13*ew**2*vel**2 + C14*ALOG(edb) + C15*ALOG(ew) + C16*ALOG(vel) edb = process entering dry-bulb temperature [C] ew  = process entering humidity ratio [kgWater/kgDryAir] vel = process air velocity [m/s] If UserCurves are specified, then performance is calculated as follows: Leaving Dry-Bulb = (Leaving Dry-Bulb fTW Curve) * (Leaving Dry-Bulb fV Curve) Leaving Humidity Ratio = (Leaving Humidity Ratio fTW Curve) * (Leaving Humidity Ratio fV Curve) Regen Energy = (Regen Energy fTW Curve) * (Regen Energy fV Curve) Regen Velocity = (Regen Velocity fTW Curve) * (Regen Velocity fV Curve)",
                        "enum": [
                            "Default",
                            "UserCurves"
                        ]
                    },
                    "leaving_dry_bulb_function_of_entering_dry_bulb_and_humidity_ratio_curve_name": {
                        "type": "string",
                        "note": "Leaving dry-bulb of process air as a function of entering dry-bulb and entering humidity ratio, biquadratic curve curve = C1 + C2*edb + C3*edb**2 + C4*ew + C5*ew**2 + C6*edb*ew edb = process entering dry-bulb temperature [C] ew  = process entering humidity ratio [kgWater/kgDryAir]",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "leaving_dry_bulb_function_of_air_velocity_curve_name": {
                        "type": "string",
                        "note": "Leaving dry-bulb of process air as a function of air velocity, quadratic curve. curve = C1 + C2*v + C3*v**2 v = process air velocity [m/s]",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "leaving_humidity_ratio_function_of_entering_dry_bulb_and_humidity_ratio_curve_name": {
                        "type": "string",
                        "note": "Leaving humidity ratio of process air as a function of entering dry-bulb and entering humidity ratio, biquadratic curve curve = C1 + C2*edb + C3*edb**2 + C4*ew + C5*ew**2 + C6*edb*ew edb = process entering dry-bulb temperature [C] ew  = process entering humidity ratio [kgWater/kgDryAir]",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "leaving_humidity_ratio_function_of_air_velocity_curve_name": {
                        "type": "string",
                        "note": "Leaving humidity ratio of process air as a function of process air velocity, quadratic curve. curve = C1 + C2*v + C3*v**2 v = process air velocity [m/s]",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "regeneration_energy_function_of_entering_dry_bulb_and_humidity_ratio_curve_name": {
                        "type": "string",
                        "note": "Regeneration energy [J/kg of water removed] as a function of entering dry-bulb and entering humidity ratio, biquadratic curve curve = C1 + C2*edb + C3*edb**2 + C4*ew + C5*ew**2 + C6*edb*ew edb = process entering dry-bulb temperature [C] ew  = process entering humidity ratio [kgWater/kgDryAir]",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "regeneration_energy_function_of_air_velocity_curve_name": {
                        "type": "string",
                        "note": "Regeneration energy [J/kg of water removed] as a function of process air velocity, quadratic curve. curve = C1 + C2*v + C3*v**2 v = process air velocity [m/s]",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "regeneration_velocity_function_of_entering_dry_bulb_and_humidity_ratio_curve_name": {
                        "type": "string",
                        "note": "Regeneration velocity [m/s] as a function of entering dry-bulb and entering humidity ratio, biquadratic curve curve = C1 + C2*edb + C3*edb**2 + C4*ew + C5*ew**2 + C6*edb*ew edb = process entering dry-bulb temperature [C] ew  = process entering humidity ratio [kgWater/kgDryAir]",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "regeneration_velocity_function_of_air_velocity_curve_name": {
                        "type": "string",
                        "note": "Regeneration velocity [m/s] as a function of process air velocity, quadratic curve. curve = C1 + C2*v + C3*v**2 v = process air velocity [m/s]",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "nominal_regeneration_temperature": {
                        "type": "number",
                        "note": "Nominal regen temperature upon which the regen energy modifier curve is based. Not used if Default if chosen for the field Performance Mode Type. 121 C is a commonly used value.",
                        "units": "C",
                        "minimum": 40.0,
                        "maximum": 250.0
                    }
                }
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
                "process_air_inlet_node_name": {
                    "field_name": "Process Air Inlet Node Name",
                    "field_type": "a"
                },
                "process_air_outlet_node_name": {
                    "field_name": "Process Air Outlet Node Name",
                    "field_type": "a"
                },
                "regeneration_air_inlet_node_name": {
                    "field_name": "Regeneration Air Inlet Node Name",
                    "field_type": "a"
                },
                "regeneration_fan_inlet_node_name": {
                    "field_name": "Regeneration Fan Inlet Node Name",
                    "field_type": "a"
                },
                "control_type": {
                    "field_name": "Control Type",
                    "field_type": "a"
                },
                "leaving_maximum_humidity_ratio_setpoint": {
                    "field_name": "Leaving Maximum Humidity Ratio Setpoint",
                    "field_type": "n"
                },
                "nominal_process_air_flow_rate": {
                    "field_name": "Nominal Process Air Flow Rate",
                    "field_type": "n"
                },
                "nominal_process_air_velocity": {
                    "field_name": "Nominal Process Air Velocity",
                    "field_type": "n"
                },
                "rotor_power": {
                    "field_name": "Rotor Power",
                    "field_type": "n"
                },
                "regeneration_coil_object_type": {
                    "field_name": "Regeneration Coil Object Type",
                    "field_type": "a"
                },
                "regeneration_coil_name": {
                    "field_name": "Regeneration Coil Name",
                    "field_type": "a"
                },
                "regeneration_fan_object_type": {
                    "field_name": "Regeneration Fan Object Type",
                    "field_type": "a"
                },
                "regeneration_fan_name": {
                    "field_name": "Regeneration Fan Name",
                    "field_type": "a"
                },
                "performance_model_type": {
                    "field_name": "Performance Model Type",
                    "field_type": "a"
                },
                "leaving_dry_bulb_function_of_entering_dry_bulb_and_humidity_ratio_curve_name": {
                    "field_name": "Leaving Dry-Bulb Function of Entering Dry-Bulb and Humidity Ratio Curve Name",
                    "field_type": "a"
                },
                "leaving_dry_bulb_function_of_air_velocity_curve_name": {
                    "field_name": "Leaving Dry-Bulb Function of Air Velocity Curve Name",
                    "field_type": "a"
                },
                "leaving_humidity_ratio_function_of_entering_dry_bulb_and_humidity_ratio_curve_name": {
                    "field_name": "Leaving Humidity Ratio Function of Entering Dry-Bulb and Humidity Ratio Curve Name",
                    "field_type": "a"
                },
                "leaving_humidity_ratio_function_of_air_velocity_curve_name": {
                    "field_name": "Leaving Humidity Ratio Function of Air Velocity Curve Name",
                    "field_type": "a"
                },
                "regeneration_energy_function_of_entering_dry_bulb_and_humidity_ratio_curve_name": {
                    "field_name": "Regeneration Energy Function of Entering Dry-Bulb and Humidity Ratio Curve Name",
                    "field_type": "a"
                },
                "regeneration_energy_function_of_air_velocity_curve_name": {
                    "field_name": "Regeneration Energy Function of Air Velocity Curve Name",
                    "field_type": "a"
                },
                "regeneration_velocity_function_of_entering_dry_bulb_and_humidity_ratio_curve_name": {
                    "field_name": "Regeneration Velocity Function of Entering Dry-Bulb and Humidity Ratio Curve Name",
                    "field_type": "a"
                },
                "regeneration_velocity_function_of_air_velocity_curve_name": {
                    "field_name": "Regeneration Velocity Function of Air Velocity Curve Name",
                    "field_type": "a"
                },
                "nominal_regeneration_temperature": {
                    "field_name": "Nominal Regeneration Temperature",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "process_air_inlet_node_name",
                "process_air_outlet_node_name",
                "regeneration_air_inlet_node_name",
                "regeneration_fan_inlet_node_name",
                "control_type",
                "leaving_maximum_humidity_ratio_setpoint",
                "nominal_process_air_flow_rate",
                "nominal_process_air_velocity",
                "rotor_power",
                "regeneration_coil_object_type",
                "regeneration_coil_name",
                "regeneration_fan_object_type",
                "regeneration_fan_name",
                "performance_model_type",
                "leaving_dry_bulb_function_of_entering_dry_bulb_and_humidity_ratio_curve_name",
                "leaving_dry_bulb_function_of_air_velocity_curve_name",
                "leaving_humidity_ratio_function_of_entering_dry_bulb_and_humidity_ratio_curve_name",
                "leaving_humidity_ratio_function_of_air_velocity_curve_name",
                "regeneration_energy_function_of_entering_dry_bulb_and_humidity_ratio_curve_name",
                "regeneration_energy_function_of_air_velocity_curve_name",
                "regeneration_velocity_function_of_entering_dry_bulb_and_humidity_ratio_curve_name",
                "regeneration_velocity_function_of_air_velocity_curve_name",
                "nominal_regeneration_temperature"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "process_air_inlet_node_name",
                    "process_air_outlet_node_name",
                    "regeneration_air_inlet_node_name",
                    "regeneration_fan_inlet_node_name",
                    "control_type",
                    "regeneration_coil_object_type",
                    "regeneration_coil_name",
                    "regeneration_fan_object_type",
                    "regeneration_fan_name",
                    "performance_model_type",
                    "leaving_dry_bulb_function_of_entering_dry_bulb_and_humidity_ratio_curve_name",
                    "leaving_dry_bulb_function_of_air_velocity_curve_name",
                    "leaving_humidity_ratio_function_of_entering_dry_bulb_and_humidity_ratio_curve_name",
                    "leaving_humidity_ratio_function_of_air_velocity_curve_name",
                    "regeneration_energy_function_of_entering_dry_bulb_and_humidity_ratio_curve_name",
                    "regeneration_energy_function_of_air_velocity_curve_name",
                    "regeneration_velocity_function_of_entering_dry_bulb_and_humidity_ratio_curve_name",
                    "regeneration_velocity_function_of_air_velocity_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "leaving_maximum_humidity_ratio_setpoint",
                    "nominal_process_air_flow_rate",
                    "nominal_process_air_velocity",
                    "rotor_power",
                    "nominal_regeneration_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "This object models a solid desiccant dehumidifier. The process air stream is the air which is dehumidified. The regeneration air stream is the air which is heated to regenerate the desiccant. This object determines the process air outlet conditions, the load on the regeneration heating coil, the electric power consumption for the wheel rotor motor, and the regeneration air fan mass flow rate. All other heat exchangers are modeled as separate objects connected to the inlet and outlet nodes of the dehumidifier. The solid desiccant dehumidifier is typically used in an AirLoopHVAC:OutdoorAirSystem, but can also be specified in any AirLoopHVAC."
    }
}
```
