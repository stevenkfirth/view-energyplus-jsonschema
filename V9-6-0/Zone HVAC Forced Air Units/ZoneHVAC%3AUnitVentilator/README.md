```
{
    "ZoneHVAC:UnitVentilator": {
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
                    "maximum_supply_air_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "outdoor_air_control_type": {
                        "type": "string",
                        "enum": [
                            "FixedAmount",
                            "FixedTemperature",
                            "VariablePercent"
                        ]
                    },
                    "minimum_outdoor_air_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "minimum_outdoor_air_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "schedule values multiply the minimum outdoor air flow rate"
                    },
                    "maximum_outdoor_air_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "maximum_outdoor_air_fraction_or_temperature_schedule_name": {
                        "type": "string",
                        "note": "that this depends on the control type as to whether it is a fraction or temperature",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "air_inlet_node_name": {
                        "type": "string",
                        "note": "Inlet node name must be zone exhaust node name if there is no DOA Mixer, or if the unit ventilator is connected DOA, then the air inlet node name must be the mixer outlet air node name for InletSide mixer connection."
                    },
                    "air_outlet_node_name": {
                        "type": "string",
                        "note": "Outlet node name must be zone inlet node name if there is no DOA Mixer, or if the unit ventilator is connected DOA, then the air outlet node name must be the mixer secondary air inlet node name for SupplySide mixer connection."
                    },
                    "outdoor_air_node_name": {
                        "type": "string",
                        "note": "this field is left blank only if the Unit Ventilator is connected to a central dedicated outdoor air (DOA) via AirTerminal:SingleDuct:Mixer object"
                    },
                    "exhaust_air_node_name": {
                        "type": "string",
                        "note": "this field is left blank only if the Unit Ventilator is connected to a central dedicated outdoor air (DOA) via AirTerminal:SingleDuct:Mixer object"
                    },
                    "mixed_air_node_name": {
                        "type": "string",
                        "note": "inlet to coils this field is left blank only if the Unit Ventilator is connected to a central dedicated outdoor air (DOA) via AirTerminal:SingleDuct:Mixer object"
                    },
                    "supply_air_fan_object_type": {
                        "type": "string",
                        "enum": [
                            "Fan:ConstantVolume",
                            "Fan:OnOff",
                            "Fan:SystemModel",
                            "Fan:VariableVolume"
                        ],
                        "note": "Allowable fan types are Fan:ConstantVolume, Fan:OnOff, Fan:VariableVolume, and Fan:SystemModel"
                    },
                    "supply_air_fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandOnOffandVAV",
                            "FansSystemModel"
                        ]
                    },
                    "coil_option": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Heating",
                            "HeatingAndCooling",
                            "None"
                        ]
                    },
                    "supply_air_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Enter the name of a schedule that controls fan operation. Schedule name values of 0 denote cycling fan operation (fan cycles with cooling/heating coil). Schedule values greater than 0 denote constant fan operation (fan runs continually regardless of coil operation). The fan operating mode defaults to cycling fan operation if this input field is left blank."
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ]
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName"
                        ]
                    },
                    "heating_convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001
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
                    "cooling_convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001
                    },
                    "availability_manager_list_name": {
                        "type": "string",
                        "note": "Enter the name of an AvailabilityManagerAssignmentList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "SystemAvailabilityManagerLists"
                        ]
                    },
                    "design_specification_zonehvac_sizing_object_name": {
                        "type": "string",
                        "note": "Enter the name of a DesignSpecificationZoneHVACSizing object.",
                        "data_type": "object_list",
                        "object_list": [
                            "DesignSpecificationZoneHVACSizingName"
                        ]
                    }
                },
                "required": [
                    "maximum_supply_air_flow_rate",
                    "outdoor_air_control_type",
                    "minimum_outdoor_air_flow_rate",
                    "minimum_outdoor_air_schedule_name",
                    "maximum_outdoor_air_flow_rate",
                    "maximum_outdoor_air_fraction_or_temperature_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "coil_option"
                ]
            }
        },
        "group": "Zone HVAC Forced Air Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DOAToZonalUnit",
                "ZoneEquipmentNames"
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
                "maximum_supply_air_flow_rate": {
                    "field_name": "Maximum Supply Air Flow Rate",
                    "field_type": "n"
                },
                "outdoor_air_control_type": {
                    "field_name": "Outdoor Air Control Type",
                    "field_type": "a"
                },
                "minimum_outdoor_air_flow_rate": {
                    "field_name": "Minimum Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "minimum_outdoor_air_schedule_name": {
                    "field_name": "Minimum Outdoor Air Schedule Name",
                    "field_type": "a"
                },
                "maximum_outdoor_air_flow_rate": {
                    "field_name": "Maximum Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "maximum_outdoor_air_fraction_or_temperature_schedule_name": {
                    "field_name": "Maximum Outdoor Air Fraction or Temperature Schedule Name",
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
                "outdoor_air_node_name": {
                    "field_name": "Outdoor Air Node Name",
                    "field_type": "a"
                },
                "exhaust_air_node_name": {
                    "field_name": "Exhaust Air Node Name",
                    "field_type": "a"
                },
                "mixed_air_node_name": {
                    "field_name": "Mixed Air Node Name",
                    "field_type": "a"
                },
                "supply_air_fan_object_type": {
                    "field_name": "Supply Air Fan Object Type",
                    "field_type": "a"
                },
                "supply_air_fan_name": {
                    "field_name": "Supply Air Fan Name",
                    "field_type": "a"
                },
                "coil_option": {
                    "field_name": "Coil Option",
                    "field_type": "a"
                },
                "supply_air_fan_operating_mode_schedule_name": {
                    "field_name": "Supply Air Fan Operating Mode Schedule Name",
                    "field_type": "a"
                },
                "heating_coil_object_type": {
                    "field_name": "Heating Coil Object Type",
                    "field_type": "a"
                },
                "heating_coil_name": {
                    "field_name": "Heating Coil Name",
                    "field_type": "a"
                },
                "heating_convergence_tolerance": {
                    "field_name": "Heating Convergence Tolerance",
                    "field_type": "n"
                },
                "cooling_coil_object_type": {
                    "field_name": "Cooling Coil Object Type",
                    "field_type": "a"
                },
                "cooling_coil_name": {
                    "field_name": "Cooling Coil Name",
                    "field_type": "a"
                },
                "cooling_convergence_tolerance": {
                    "field_name": "Cooling Convergence Tolerance",
                    "field_type": "n"
                },
                "availability_manager_list_name": {
                    "field_name": "Availability Manager List Name",
                    "field_type": "a"
                },
                "design_specification_zonehvac_sizing_object_name": {
                    "field_name": "Design Specification ZoneHVAC Sizing Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "maximum_supply_air_flow_rate",
                "outdoor_air_control_type",
                "minimum_outdoor_air_flow_rate",
                "minimum_outdoor_air_schedule_name",
                "maximum_outdoor_air_flow_rate",
                "maximum_outdoor_air_fraction_or_temperature_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "outdoor_air_node_name",
                "exhaust_air_node_name",
                "mixed_air_node_name",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "coil_option",
                "supply_air_fan_operating_mode_schedule_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "heating_convergence_tolerance",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "cooling_convergence_tolerance",
                "availability_manager_list_name",
                "design_specification_zonehvac_sizing_object_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "outdoor_air_control_type",
                    "minimum_outdoor_air_schedule_name",
                    "maximum_outdoor_air_fraction_or_temperature_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "outdoor_air_node_name",
                    "exhaust_air_node_name",
                    "mixed_air_node_name",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "coil_option",
                    "supply_air_fan_operating_mode_schedule_name",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "availability_manager_list_name",
                    "design_specification_zonehvac_sizing_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_supply_air_flow_rate",
                    "minimum_outdoor_air_flow_rate",
                    "maximum_outdoor_air_flow_rate",
                    "heating_convergence_tolerance",
                    "cooling_convergence_tolerance"
                ]
            }
        },
        "type": "object",
        "memo": "Unit ventilator. Forced-convection ventilation unit with supply fan (constant-volume or variable-volume), optional chilled water cooling coil, optional heating coil (gas, electric, hot water, or steam) and controllable outdoor air mixer.",
        "min_fields": 16.0
    }
}
```
