```
{
    "AvailabilityManager:HybridVentilation": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "hvac_air_loop_name": {
                        "type": "string",
                        "note": "Enter the name of an AirLoopHVAC or HVACTemplate:System:* object. If this field is left blank, hybrid ventilation managers will be simulated for zone equipment control",
                        "data_type": "object_list",
                        "object_list": [
                            "AirPrimaryLoops",
                            "HVACTemplateSystems"
                        ]
                    },
                    "control_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "the zone name should be a zone where a thermostat or humidistat is located served by an air primary loop."
                    },
                    "ventilation_control_mode_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "The Ventilation control mode contains appropriate integer control types. 0 - uncontrolled (Natural ventilation and HVAC system are controlled by themselves) 1 = Temperature control 2 = Enthalpy control 3 = Dewpoint control 4 = Outdoor ventilation air control 5 = Operative temperature control with 80% adaptive comfort acceptability limits 6 = Operative temperature control with 90% adaptive comfort acceptability limits 7 = Carbon dioxide control"
                    },
                    "use_weather_file_rain_indicators": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes",
                        "note": "If Yes, ventilation is shutoff when there is rain If No, there is no rain control"
                    },
                    "maximum_wind_speed": {
                        "type": "number",
                        "units": "m/s",
                        "minimum": 0.0,
                        "maximum": 40.0,
                        "default": 40.0,
                        "note": "this is the wind speed above which ventilation is shutoff"
                    },
                    "minimum_outdoor_temperature": {
                        "type": "number",
                        "note": "this is the outdoor temperature below which ventilation is shutoff",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": -100.0
                    },
                    "maximum_outdoor_temperature": {
                        "type": "number",
                        "note": "this is the outdoor temperature above which ventilation is shutoff",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": 100.0
                    },
                    "minimum_outdoor_enthalpy": {
                        "type": "number",
                        "note": "this is the outdoor Enthalpy below which ventilation is shutoff",
                        "units": "J/kg",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 300000.0
                    },
                    "maximum_outdoor_enthalpy": {
                        "type": "number",
                        "note": "this is the outdoor Enthalpy above which ventilation is shutoff",
                        "units": "J/kg",
                        "exclusiveMinimum": 0.0,
                        "exclusiveMaximum": 300000.0
                    },
                    "minimum_outdoor_dewpoint": {
                        "type": "number",
                        "note": "this is the outdoor temperature below which ventilation is shutoff Applicable only if Ventilation Control Mode = 3",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": -100.0
                    },
                    "maximum_outdoor_dewpoint": {
                        "type": "number",
                        "note": "this is the outdoor dewpoint above which ventilation is shutoff Applicable only if Ventilation Control Mode = 3",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": 100.0
                    },
                    "minimum_outdoor_ventilation_air_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Used only if Ventilation Control Mode = 4"
                    },
                    "opening_factor_function_of_wind_speed_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "linear curve = a + b*WS quadratic curve = a + b*WS + c*WS**2 WS = wind speed (m/s)"
                    },
                    "airflownetwork_control_type_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "The schedule is used to incorporate operation of AirflowNetwork large opening objects and HVAC system operation."
                    },
                    "simple_airflow_control_type_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "The schedule is used to incorporate operation of simple airflow objects and HVAC system operation. The simple airflow objects are Ventilation and Mixing only"
                    },
                    "zoneventilation_object_name": {
                        "type": "string",
                        "note": "This field has not been instrumented to work with global Zone or Zone List names option for Ventilation:DesignFlowRate. In order to use, you must enter the single <Ventilation:DesignFlowRate> name in this field. If it is a part of a global ventilation assignment the name will be <Zone Name> <global Ventilation:DesignFlowRate> name. The other ZoneVentilation:* and ZoneMixing objects controlled in the same AirLoopHVAC will work in the same way as this ventilation object.",
                        "data_type": "object_list",
                        "object_list": [
                            "VentilationNames"
                        ]
                    },
                    "minimum_hvac_operation_time": {
                        "type": "number",
                        "note": "Minimum operation time when HVAC system is forced on.",
                        "units": "minutes",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "minimum_ventilation_time": {
                        "type": "number",
                        "note": "Minimum ventilation time when natural ventilation is forced on.",
                        "units": "minutes",
                        "minimum": 0.0,
                        "default": 0.0
                    }
                },
                "required": [
                    "control_zone_name",
                    "ventilation_control_mode_schedule_name"
                ]
            }
        },
        "group": "System Availability Managers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SystemAvailabilityManagers"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "hvac_air_loop_name": {
                    "field_name": "HVAC Air Loop Name",
                    "field_type": "a"
                },
                "control_zone_name": {
                    "field_name": "Control Zone Name",
                    "field_type": "a"
                },
                "ventilation_control_mode_schedule_name": {
                    "field_name": "Ventilation Control Mode Schedule Name",
                    "field_type": "a"
                },
                "use_weather_file_rain_indicators": {
                    "field_name": "Use Weather File Rain Indicators",
                    "field_type": "a"
                },
                "maximum_wind_speed": {
                    "field_name": "Maximum Wind Speed",
                    "field_type": "n"
                },
                "minimum_outdoor_temperature": {
                    "field_name": "Minimum Outdoor Temperature",
                    "field_type": "n"
                },
                "maximum_outdoor_temperature": {
                    "field_name": "Maximum Outdoor Temperature",
                    "field_type": "n"
                },
                "minimum_outdoor_enthalpy": {
                    "field_name": "Minimum Outdoor Enthalpy",
                    "field_type": "n"
                },
                "maximum_outdoor_enthalpy": {
                    "field_name": "Maximum Outdoor Enthalpy",
                    "field_type": "n"
                },
                "minimum_outdoor_dewpoint": {
                    "field_name": "Minimum Outdoor Dewpoint",
                    "field_type": "n"
                },
                "maximum_outdoor_dewpoint": {
                    "field_name": "Maximum Outdoor Dewpoint",
                    "field_type": "n"
                },
                "minimum_outdoor_ventilation_air_schedule_name": {
                    "field_name": "Minimum Outdoor Ventilation Air Schedule Name",
                    "field_type": "a"
                },
                "opening_factor_function_of_wind_speed_curve_name": {
                    "field_name": "Opening Factor Function of Wind Speed Curve Name",
                    "field_type": "a"
                },
                "airflownetwork_control_type_schedule_name": {
                    "field_name": "AirflowNetwork Control Type Schedule Name",
                    "field_type": "a"
                },
                "simple_airflow_control_type_schedule_name": {
                    "field_name": "Simple Airflow Control Type Schedule Name",
                    "field_type": "a"
                },
                "zoneventilation_object_name": {
                    "field_name": "ZoneVentilation Object Name",
                    "field_type": "a"
                },
                "minimum_hvac_operation_time": {
                    "field_name": "Minimum HVAC Operation Time",
                    "field_type": "n"
                },
                "minimum_ventilation_time": {
                    "field_name": "Minimum Ventilation Time",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "hvac_air_loop_name",
                "control_zone_name",
                "ventilation_control_mode_schedule_name",
                "use_weather_file_rain_indicators",
                "maximum_wind_speed",
                "minimum_outdoor_temperature",
                "maximum_outdoor_temperature",
                "minimum_outdoor_enthalpy",
                "maximum_outdoor_enthalpy",
                "minimum_outdoor_dewpoint",
                "maximum_outdoor_dewpoint",
                "minimum_outdoor_ventilation_air_schedule_name",
                "opening_factor_function_of_wind_speed_curve_name",
                "airflownetwork_control_type_schedule_name",
                "simple_airflow_control_type_schedule_name",
                "zoneventilation_object_name",
                "minimum_hvac_operation_time",
                "minimum_ventilation_time"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "hvac_air_loop_name",
                    "control_zone_name",
                    "ventilation_control_mode_schedule_name",
                    "use_weather_file_rain_indicators",
                    "minimum_outdoor_ventilation_air_schedule_name",
                    "opening_factor_function_of_wind_speed_curve_name",
                    "airflownetwork_control_type_schedule_name",
                    "simple_airflow_control_type_schedule_name",
                    "zoneventilation_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_wind_speed",
                    "minimum_outdoor_temperature",
                    "maximum_outdoor_temperature",
                    "minimum_outdoor_enthalpy",
                    "maximum_outdoor_enthalpy",
                    "minimum_outdoor_dewpoint",
                    "maximum_outdoor_dewpoint",
                    "minimum_hvac_operation_time",
                    "minimum_ventilation_time"
                ]
            }
        },
        "type": "object",
        "memo": "Depending on zone and outdoor conditions overrides window/door opening controls to maximize natural ventilation and turn off an HVAC system when ventilation control conditions are met. This object (zone ventilation object name) has not been instrumented to work with global Zone or Zone List names option for Ventilation:DesignFlowRate. In order to use, you must enter the single <Ventilation:DesignFlowRate> name in that field. If it is a part of a global ventilation assignment the name will be <Zone Name> <global Ventilation:DesignFlowRate> name. Currently, hybrid ventilation manager is restricted to one per zone. It can either be applied through the air loop or directly to the zone. If hybrid ventilation manager is applied to an air loop and one of the zones served by that air loop also has hybrid ventilation manager, then zone hybrid ventilation manager is disabled.",
        "min_fields": 13.0
    }
}
```
