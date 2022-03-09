```
{
    "AirLoopHVAC:UnitarySystem": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Load",
                            "SetPoint",
                            "SingleZoneVAV"
                        ],
                        "default": "Load",
                        "note": "Load control requires a Controlling Zone name. SetPoint control requires set points at coil outlet node. SingleZoneVAV also requires a Controlling Zone name and allows load control at low speed fan until the load exceeds capacity or outlet air temperature limits. The fan speed is then increased."
                    },
                    "controlling_zone_or_thermostat_location": {
                        "type": "string",
                        "note": "Used only for Load based control Zone name where thermostat is located. Required when Control Type = Load.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
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
                        "note": "None = meet sensible load only. Required when Control Type = SingleZoneVAV. Multimode = activate enhanced dehumidification mode as needed and meet sensible load. Valid only with cooling coil type Coil:Cooling:DX:TwoStageWithHumidityControlMode or CoilSystem:Cooling:DX:HeatExchangerAssisted. This control mode either switches the coil mode or allows the heat exchanger to be turned on and off based on the zone dehumidification requirements. A ZoneControl:Humidistat object is also required. CoolReheat = cool beyond the dry-bulb setpoint. as required to meet the humidity setpoint. Valid with all cooling coil types. When a heat exchanger assisted cooling coil is used, the heat exchanger is locked on at all times. A ZoneControl:Humidistat object is also required."
                    },
                    "availability_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available. A schedule value greater than zero (usually 1 is used) indicates that the unit is available to operate as needed. A value less than or equal to zero (usually zero is used) denotes that the unit must be off."
                    },
                    "air_inlet_node_name": {
                        "type": "string",
                        "note": "Enter the node name used as the inlet air node for the unitary system."
                    },
                    "air_outlet_node_name": {
                        "type": "string",
                        "note": "Enter the node name used as the outlet air node for the unitary system."
                    },
                    "supply_fan_object_type": {
                        "type": "string",
                        "enum": [
                            "Fan:ComponentModel",
                            "Fan:ConstantVolume",
                            "Fan:OnOff",
                            "Fan:SystemModel",
                            "Fan:VariableVolume"
                        ],
                        "note": "Enter the type of supply air fan if included in the unitary system. Fan:ConstantVolume only works with continuous fan operating mode (i.e. supply air fan operating mode schedule values greater than 0). Specify a Fan:SystemModel or a Fan:OnOff object when the Supply Air Fan Operating Mode Schedule Name input field above is left blank. Specify a Fan:SystemModel or a Fan:VariableVolume when modeling VAV systems which used setpoint based control if the fan is included in the unitary system object. The ComponentModel fan type may be substituted for the ConstantVolume or VariableVolume fan types when more detailed fan modeling is required. The variable or constant volume fan may be specified on the branch instead of contained within the unitary system object (i.e., this field may be blank for certain configurations)."
                    },
                    "supply_fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Fans"
                        ],
                        "note": "Enter the name of the supply air fan if included in the unitary system."
                    },
                    "fan_placement": {
                        "type": "string",
                        "enum": [
                            "BlowThrough",
                            "DrawThrough"
                        ],
                        "note": "Enter the type of supply air fan if included in the unitary system."
                    },
                    "supply_air_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "A fan operating mode schedule value of 0 indicates cycling fan mode (supply air fan cycles on and off in tandem with the cooling or heating coil). Any other schedule value indicates continuous fan mode (supply air fan operates continuously regardless of cooling or heating coil operation). Provide a schedule with non-zero values when high humidity control is specified. Leaving this schedule name blank will default to constant fan mode for the entire simulation period. This field is not used when set point based control is used where a set point controls the coil. SingleZoneVAV control type is only active when constant fan operating mode is active."
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:DX:MultiSpeed",
                            "Coil:Heating:DX:SingleSpeed",
                            "Coil:Heating:DX:VariableSpeed",
                            "Coil:Heating:Desuperheater",
                            "Coil:Heating:Electric",
                            "Coil:Heating:Electric:MultiStage",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Gas:MultiStage",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water",
                            "Coil:Heating:WaterToAirHeatPump:EquationFit",
                            "Coil:Heating:WaterToAirHeatPump:ParameterEstimation",
                            "Coil:Heating:WaterToAirHeatPump:VariableSpeedEquationFit",
                            "Coil:UserDefined"
                        ],
                        "note": "Enter the type of heating coil if included in the unitary system."
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName",
                            "HeatingCoilsDX",
                            "HeatingCoilsDXMultiSpeed",
                            "HeatingCoilsDXVariableSpeed",
                            "HeatingCoilsDesuperheater",
                            "HeatingCoilsElectricMultiStage",
                            "HeatingCoilsGasMultiStage",
                            "HeatingCoilsWaterToAirHP",
                            "HeatingCoilsWaterToAirVSHP",
                            "UserDefinedCoil"
                        ],
                        "note": "Enter the name of the heating coil if included in the unitary system."
                    },
                    "dx_heating_coil_sizing_ratio": {
                        "type": "number",
                        "default": 1.0,
                        "exclusiveMinimum": 0.0,
                        "note": "Used to adjust heat pump heating capacity with respect to DX cooling capacity used only for heat pump configurations (i.e., a DX cooling and DX heating coil is used)."
                    },
                    "cooling_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:DX",
                            "Coil:Cooling:DX:MultiSpeed",
                            "Coil:Cooling:DX:SingleSpeed",
                            "Coil:Cooling:DX:SingleSpeed:ThermalStorage",
                            "Coil:Cooling:DX:TwoSpeed",
                            "Coil:Cooling:DX:TwoStageWithHumidityControlMode",
                            "Coil:Cooling:DX:VariableSpeed",
                            "Coil:Cooling:Water",
                            "Coil:Cooling:Water:DetailedGeometry",
                            "Coil:Cooling:WaterToAirHeatPump:EquationFit",
                            "Coil:Cooling:WaterToAirHeatPump:ParameterEstimation",
                            "Coil:Cooling:WaterToAirHeatPump:VariableSpeedEquationFit",
                            "Coil:UserDefined",
                            "CoilSystem:Cooling:DX:HeatExchangerAssisted",
                            "CoilSystem:Cooling:Water:HeatExchangerAssisted"
                        ],
                        "note": "Enter the type of cooling coil if included in the unitary system."
                    },
                    "cooling_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CoilCoolingDX",
                            "CoolingCoilsDX",
                            "CoolingCoilsDXMultiSpeed",
                            "CoolingCoilsDXVariableSpeed",
                            "CoolingCoilsWater",
                            "CoolingCoilsWaterToAirHP",
                            "CoolingCoilsWaterToAirVSHP",
                            "UserDefinedCoil"
                        ],
                        "note": "Enter the name of the cooling coil if included in the unitary system."
                    },
                    "use_doas_dx_cooling_coil": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "If Yes, the DX cooling coil runs as 100% DOAS DX coil. If No, the DX cooling coil runs as a regular DX coil. If left blank the default is regular dx coil."
                    },
                    "minimum_supply_air_temperature": {
                        "units": "C",
                        "default": 2.0,
                        "note": "When Use DOAS DX Cooling Coil is specified as Yes, Minimum Supply Air Temperature defines the minimum DOAS DX cooling coil leaving air temperature that should be maintained to avoid frost formation. This field is not autosizable when the input for Use DOAS DX Cooling Coil = Yes. When Control Type = SingleZoneVAV, enter the minimum air temperature limit for reduced fan speed.",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 20.0
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
                    "latent_load_control": {
                        "type": "string",
                        "enum": [
                            "",
                            "LatentOnlyLoadControl",
                            "LatentOrSensibleLoadControl",
                            "LatentWithSensibleLoadControl",
                            "SensibleOnlyLoadControl"
                        ],
                        "default": "SensibleOnlyLoadControl",
                        "note": "SensibleOnlyLoadControl is selected when thermostat or SingleZoneVAV control is used. LatentOnlyLoadControl is selected when humidistat control is used. LatentWithSensibleLoadControl is selected when thermostat control is used and dehumidification is required only when a sensible load exists. LatentOrSensibleLoadControl is selected when thermostat control is used and dehumidification is required any time the humidistat set point is exceeded."
                    },
                    "supplemental_heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Desuperheater",
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water",
                            "Coil:UserDefined"
                        ],
                        "note": "Enter the type of supplemental heating or reheat coil if included in the unitary system. Only required if dehumidification control type is \"CoolReheat\". This coil supplements heating mode operation or reheats the supply air during dehumidification mode operation. If set point based control is used the coils operate to meet their respective supply air temperature set point."
                    },
                    "supplemental_heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName",
                            "HeatingCoilsDesuperheater",
                            "UserDefinedCoil"
                        ],
                        "note": "Enter the name of the supplemental heating coil if included in the unitary system. Only required if dehumidification control type is \"CoolReheat\"."
                    },
                    "cooling_supply_air_flow_rate_method": {
                        "type": "string",
                        "enum": [
                            "FlowPerCoolingCapacity",
                            "FlowPerFloorArea",
                            "FractionOfAutosizedCoolingValue",
                            "None",
                            "SupplyAirFlowRate"
                        ],
                        "note": "Enter the method used to determine the cooling supply air volume flow rate. None is used when a cooling coil is not included in the unitary system or this field may be blank. SupplyAirFlowRate is selected when the magnitude of the supply air volume is used. FlowPerFloorArea is selected when the supply air volume flow rate is based on total floor area served by the unitary system. FractionOfAutosizedCoolingValue is selected when the supply air volume is a fraction of the value determined by the simulation. FlowPerCoolingCapacity is selected when the supply air volume is a fraction of the cooling capacity as determined by the simulation."
                    },
                    "cooling_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the magnitude of the supply air volume flow rate during cooling operation. Required field when Cooling Supply Air Flow Rate Method is SupplyAirFlowRate. This field may be blank if a cooling coil is not included in the unitary system.",
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
                    "cooling_supply_air_flow_rate_per_floor_area": {
                        "type": "number",
                        "units": "m3/s-m2",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate per total floor area fraction. Required field when Cooling Supply Air Flow Rate Method is FlowPerFloorArea. This field may be blank if a cooling coil is not included in the unitary system."
                    },
                    "cooling_fraction_of_autosized_cooling_supply_air_flow_rate": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the cooling supply air flow rate. Required field when Cooling Supply Air Flow Rate Method is FractionOfAutosizedCoolingValue. This field may be blank if a cooling coil is not included in the unitary system."
                    },
                    "cooling_supply_air_flow_rate_per_unit_of_capacity": {
                        "type": "number",
                        "units": "m3/s-W",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the cooling capacity. Required field when Cooling Supply Air Flow Rate Method is FlowPerCoolingCapacity. This field may be blank if a cooling coil is not included in the unitary system."
                    },
                    "heating_supply_air_flow_rate_method": {
                        "type": "string",
                        "enum": [
                            "FlowPerFloorArea",
                            "FlowPerHeatingCapacity",
                            "FractionOfAutosizedHeatingValue",
                            "None",
                            "SupplyAirFlowRate"
                        ],
                        "note": "Enter the method used to determine the heating supply air volume flow rate. None is used when a heating coil is not included in the unitary system or this field may be blank. SupplyAirFlowRate is selected when the magnitude of the supply air volume is used. FlowPerFloorArea is selected when the supply air volume flow rate is based on total floor area served by the unitary system. FractionOfAutosizedHeatingValue is selected when the supply air volume is a fraction of the value determined by the simulation. FlowPerHeatingCapacity is selected when the supply air volume is a fraction of the heating capacity as determined by the simulation."
                    },
                    "heating_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the magnitude of the supply air volume flow rate during heating operation. Required field when Heating Supply Air Flow Rate Method is SupplyAirFlowRate. This field may be blank if a heating coil is not included in the unitary system.",
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
                    "heating_supply_air_flow_rate_per_floor_area": {
                        "type": "number",
                        "units": "m3/s-m2",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate per total floor area fraction. Required field when Heating Supply Air Flow Rate Method is FlowPerFloorArea. This field may be blank if a heating coil is not included in the unitary system."
                    },
                    "heating_fraction_of_autosized_heating_supply_air_flow_rate": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the heating supply air flow rate. Required field when Heating Supply Air Flow Rate Method is FractionOfAutosizedHeatingValue. This field may be blank if a heating coil is not included in the unitary system."
                    },
                    "heating_supply_air_flow_rate_per_unit_of_capacity": {
                        "type": "number",
                        "units": "m3/s-W",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the heating capacity. Required field when Heating Supply Air Flow Rate Method is FlowPerHeatingCapacity. This field may be blank if a heating coil is not included in the unitary system."
                    },
                    "no_load_supply_air_flow_rate_method": {
                        "type": "string",
                        "enum": [
                            "FlowPerCoolingCapacity",
                            "FlowPerFloorArea",
                            "FlowPerHeatingCapacity",
                            "FractionOfAutosizedCoolingValue",
                            "FractionOfAutosizedHeatingValue",
                            "None",
                            "SupplyAirFlowRate"
                        ],
                        "note": "Enter the method used to determine the supply air volume flow rate when no cooling or heating is required. None is used when a cooling and heating coil is not included in the unitary system or this field may be blank. SupplyAirFlowRate is selected when the magnitude of the supply air volume is used. FlowPerFloorArea is selected when the supply air volume flow rate is based on total floor area served by the unitary system. FractionOfAutosizedCoolingValue is selected when the supply air volume is a fraction of the cooling value determined by the simulation. FractionOfAutosizedHeatingValue is selected when the supply air volume is a fraction of the heating value determined by the simulation. FlowPerCoolingCapacity is selected when the supply air volume is a fraction of the cooling capacity as determined by the simulation. FlowPerHeatingCapacity is selected when the supply air volume is a fraction of the heating capacity as determined by the simulation."
                    },
                    "no_load_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the magnitude of the supply air volume flow rate during when no cooling or heating is required. Required field when No Load Supply Air Flow Rate Method is SupplyAirFlowRate.",
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
                    "no_load_supply_air_flow_rate_per_floor_area": {
                        "type": "number",
                        "units": "m3/s-m2",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate per total floor area fraction. Required field when No Load Supply Air Flow Rate Method is FlowPerFloorArea."
                    },
                    "no_load_fraction_of_autosized_cooling_supply_air_flow_rate": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the cooling supply air flow rate. Required field when No Load Supply Air Flow Rate Method is FractionOfAutosizedCoolingValue."
                    },
                    "no_load_fraction_of_autosized_heating_supply_air_flow_rate": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the heating supply air flow rate. Required field when No Load Supply Air Flow Rate Method is FractionOfAutosizedHeatingValue."
                    },
                    "no_load_supply_air_flow_rate_per_unit_of_capacity_during_cooling_operation": {
                        "type": "number",
                        "units": "m3/s-W",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the cooling capacity. Required field when No Load Supply Air Flow Rate Method is FlowPerCoolingCapacity."
                    },
                    "no_load_supply_air_flow_rate_per_unit_of_capacity_during_heating_operation": {
                        "type": "number",
                        "units": "m3/s-W",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the heating capacity. Required field when No Load Supply Air Flow Rate Method is FlowPerHeatingCapacity."
                    },
                    "maximum_supply_air_temperature": {
                        "units": "C",
                        "default": 80.0,
                        "note": "Enter the maximum supply air temperature leaving the heating coil. When Control Type = SingleZoneVAV, enter the maximum air temperature limit for reduced fan speed.",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation": {
                        "type": "number",
                        "units": "C",
                        "default": 21.0,
                        "note": "Enter the maximum outdoor dry-bulb temperature for supplemental heater operation."
                    },
                    "outdoor_dry_bulb_temperature_sensor_node_name": {
                        "type": "string",
                        "note": "If this field is blank, outdoor temperature from the weather file is used. If this field is not blank, the node name specified determines the outdoor temperature used for controlling supplemental heater operation."
                    },
                    "maximum_cycling_rate": {
                        "type": "number",
                        "units": "cycles/hr",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 2.5,
                        "note": "Used only for water source heat pump. The maximum on-off cycling rate for the compressor. Suggested value is 2.5 for a typical heat pump."
                    },
                    "heat_pump_time_constant": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 500.0,
                        "default": 60.0,
                        "note": "Used only for water source heat pump. Time constant for the cooling coil's capacity to reach steady state after startup. Suggested value is 60 for a typical heat pump."
                    },
                    "fraction_of_on_cycle_power_use": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 0.05,
                        "default": 0.01,
                        "note": "Used only for water source heat pump. The fraction of on-cycle power use to adjust the part load fraction based on the off-cycle power consumption due to crankcase heaters, controls, fans, and etc. Suggested value is 0.01 for a typical heat pump."
                    },
                    "heat_pump_fan_delay_time": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "default": 60.0,
                        "note": "Used only for water source heat pump. Programmed time delay for heat pump fan to shut off after compressor cycle off. Only required when fan operating mode is cycling. Enter 0 when fan operating mode is continuous."
                    },
                    "ancillary_on_cycle_electric_power": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Enter the value of ancillary electric power for controls or other devices consumed during the on cycle."
                    },
                    "ancillary_off_cycle_electric_power": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Enter the value of ancillary electric power for controls or other devices consumed during the off cycle."
                    },
                    "design_heat_recovery_water_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "If non-zero, then the heat recovery inlet and outlet node names must be entered. Used for heat recovery to an EnergyPlus plant loop."
                    },
                    "maximum_temperature_for_heat_recovery": {
                        "type": "number",
                        "units": "C",
                        "maximum": 100.0,
                        "minimum": 0.0,
                        "default": 80.0,
                        "note": "Enter the maximum heat recovery inlet temperature allowed for heat recovery."
                    },
                    "heat_recovery_water_inlet_node_name": {
                        "type": "string",
                        "note": "Enter the name of the heat recovery water inlet node if plant water loop connections are present."
                    },
                    "heat_recovery_water_outlet_node_name": {
                        "type": "string",
                        "note": "Enter the name of the heat recovery water outlet node if plant water loop connections are present."
                    },
                    "design_specification_multispeed_object_type": {
                        "type": "string",
                        "enum": [
                            "UnitarySystemPerformance:Multispeed"
                        ],
                        "note": "Enter the type of performance specification object used to describe the multispeed coil."
                    },
                    "design_specification_multispeed_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnitarySystemPerformaceNames"
                        ],
                        "note": "Enter the name of the performance specification object used to describe the multispeed coil."
                    }
                },
                "required": [
                    "air_inlet_node_name",
                    "air_outlet_node_name"
                ]
            }
        },
        "group": "Unitary Equipment",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DOAToZonalUnit",
                "ZoneEquipmentNames",
                "validBranchEquipmentNames",
                "validOASysEquipmentNames"
            ],
            "note": "Unique name for the Unitary System.",
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
                "control_type": {
                    "field_name": "Control Type",
                    "field_type": "a"
                },
                "controlling_zone_or_thermostat_location": {
                    "field_name": "Controlling Zone or Thermostat Location",
                    "field_type": "a"
                },
                "dehumidification_control_type": {
                    "field_name": "Dehumidification Control Type",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
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
                "supply_fan_object_type": {
                    "field_name": "Supply Fan Object Type",
                    "field_type": "a"
                },
                "supply_fan_name": {
                    "field_name": "Supply Fan Name",
                    "field_type": "a"
                },
                "fan_placement": {
                    "field_name": "Fan Placement",
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
                "dx_heating_coil_sizing_ratio": {
                    "field_name": "DX Heating Coil Sizing Ratio",
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
                "use_doas_dx_cooling_coil": {
                    "field_name": "Use DOAS DX Cooling Coil",
                    "field_type": "a"
                },
                "minimum_supply_air_temperature": {
                    "field_name": "Minimum Supply Air Temperature",
                    "field_type": "n"
                },
                "latent_load_control": {
                    "field_name": "Latent Load Control",
                    "field_type": "a"
                },
                "supplemental_heating_coil_object_type": {
                    "field_name": "Supplemental Heating Coil Object Type",
                    "field_type": "a"
                },
                "supplemental_heating_coil_name": {
                    "field_name": "Supplemental Heating Coil Name",
                    "field_type": "a"
                },
                "cooling_supply_air_flow_rate_method": {
                    "field_name": "Cooling Supply Air Flow Rate Method",
                    "field_type": "a"
                },
                "cooling_supply_air_flow_rate": {
                    "field_name": "Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_supply_air_flow_rate_per_floor_area": {
                    "field_name": "Cooling Supply Air Flow Rate Per Floor Area",
                    "field_type": "n"
                },
                "cooling_fraction_of_autosized_cooling_supply_air_flow_rate": {
                    "field_name": "Cooling Fraction of Autosized Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_supply_air_flow_rate_per_unit_of_capacity": {
                    "field_name": "Cooling Supply Air Flow Rate Per Unit of Capacity",
                    "field_type": "n"
                },
                "heating_supply_air_flow_rate_method": {
                    "field_name": "Heating Supply Air Flow Rate Method",
                    "field_type": "a"
                },
                "heating_supply_air_flow_rate": {
                    "field_name": "Heating Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_supply_air_flow_rate_per_floor_area": {
                    "field_name": "Heating Supply Air Flow Rate Per Floor Area",
                    "field_type": "n"
                },
                "heating_fraction_of_autosized_heating_supply_air_flow_rate": {
                    "field_name": "Heating Fraction of Autosized Heating Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_supply_air_flow_rate_per_unit_of_capacity": {
                    "field_name": "Heating Supply Air Flow Rate Per Unit of Capacity",
                    "field_type": "n"
                },
                "no_load_supply_air_flow_rate_method": {
                    "field_name": "No Load Supply Air Flow Rate Method",
                    "field_type": "a"
                },
                "no_load_supply_air_flow_rate": {
                    "field_name": "No Load Supply Air Flow Rate",
                    "field_type": "n"
                },
                "no_load_supply_air_flow_rate_per_floor_area": {
                    "field_name": "No Load Supply Air Flow Rate Per Floor Area",
                    "field_type": "n"
                },
                "no_load_fraction_of_autosized_cooling_supply_air_flow_rate": {
                    "field_name": "No Load Fraction of Autosized Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "no_load_fraction_of_autosized_heating_supply_air_flow_rate": {
                    "field_name": "No Load Fraction of Autosized Heating Supply Air Flow Rate",
                    "field_type": "n"
                },
                "no_load_supply_air_flow_rate_per_unit_of_capacity_during_cooling_operation": {
                    "field_name": "No Load Supply Air Flow Rate Per Unit of Capacity During Cooling Operation",
                    "field_type": "n"
                },
                "no_load_supply_air_flow_rate_per_unit_of_capacity_during_heating_operation": {
                    "field_name": "No Load Supply Air Flow Rate Per Unit of Capacity During Heating Operation",
                    "field_type": "n"
                },
                "maximum_supply_air_temperature": {
                    "field_name": "Maximum Supply Air Temperature",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation": {
                    "field_name": "Maximum Outdoor Dry-Bulb Temperature for Supplemental Heater Operation",
                    "field_type": "n"
                },
                "outdoor_dry_bulb_temperature_sensor_node_name": {
                    "field_name": "Outdoor Dry-Bulb Temperature Sensor Node Name",
                    "field_type": "a"
                },
                "maximum_cycling_rate": {
                    "field_name": "Maximum Cycling Rate",
                    "field_type": "n"
                },
                "heat_pump_time_constant": {
                    "field_name": "Heat Pump Time Constant",
                    "field_type": "n"
                },
                "fraction_of_on_cycle_power_use": {
                    "field_name": "Fraction of On-Cycle Power Use",
                    "field_type": "n"
                },
                "heat_pump_fan_delay_time": {
                    "field_name": "Heat Pump Fan Delay Time",
                    "field_type": "n"
                },
                "ancillary_on_cycle_electric_power": {
                    "field_name": "Ancillary On-Cycle Electric Power",
                    "field_type": "n"
                },
                "ancillary_off_cycle_electric_power": {
                    "field_name": "Ancillary Off-Cycle Electric Power",
                    "field_type": "n"
                },
                "design_heat_recovery_water_flow_rate": {
                    "field_name": "Design Heat Recovery Water Flow Rate",
                    "field_type": "n"
                },
                "maximum_temperature_for_heat_recovery": {
                    "field_name": "Maximum Temperature for Heat Recovery",
                    "field_type": "n"
                },
                "heat_recovery_water_inlet_node_name": {
                    "field_name": "Heat Recovery Water Inlet Node Name",
                    "field_type": "a"
                },
                "heat_recovery_water_outlet_node_name": {
                    "field_name": "Heat Recovery Water Outlet Node Name",
                    "field_type": "a"
                },
                "design_specification_multispeed_object_type": {
                    "field_name": "Design Specification Multispeed Object Type",
                    "field_type": "a"
                },
                "design_specification_multispeed_object_name": {
                    "field_name": "Design Specification Multispeed Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "control_type",
                "controlling_zone_or_thermostat_location",
                "dehumidification_control_type",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "supply_fan_object_type",
                "supply_fan_name",
                "fan_placement",
                "supply_air_fan_operating_mode_schedule_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "dx_heating_coil_sizing_ratio",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "use_doas_dx_cooling_coil",
                "minimum_supply_air_temperature",
                "latent_load_control",
                "supplemental_heating_coil_object_type",
                "supplemental_heating_coil_name",
                "cooling_supply_air_flow_rate_method",
                "cooling_supply_air_flow_rate",
                "cooling_supply_air_flow_rate_per_floor_area",
                "cooling_fraction_of_autosized_cooling_supply_air_flow_rate",
                "cooling_supply_air_flow_rate_per_unit_of_capacity",
                "heating_supply_air_flow_rate_method",
                "heating_supply_air_flow_rate",
                "heating_supply_air_flow_rate_per_floor_area",
                "heating_fraction_of_autosized_heating_supply_air_flow_rate",
                "heating_supply_air_flow_rate_per_unit_of_capacity",
                "no_load_supply_air_flow_rate_method",
                "no_load_supply_air_flow_rate",
                "no_load_supply_air_flow_rate_per_floor_area",
                "no_load_fraction_of_autosized_cooling_supply_air_flow_rate",
                "no_load_fraction_of_autosized_heating_supply_air_flow_rate",
                "no_load_supply_air_flow_rate_per_unit_of_capacity_during_cooling_operation",
                "no_load_supply_air_flow_rate_per_unit_of_capacity_during_heating_operation",
                "maximum_supply_air_temperature",
                "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation",
                "outdoor_dry_bulb_temperature_sensor_node_name",
                "maximum_cycling_rate",
                "heat_pump_time_constant",
                "fraction_of_on_cycle_power_use",
                "heat_pump_fan_delay_time",
                "ancillary_on_cycle_electric_power",
                "ancillary_off_cycle_electric_power",
                "design_heat_recovery_water_flow_rate",
                "maximum_temperature_for_heat_recovery",
                "heat_recovery_water_inlet_node_name",
                "heat_recovery_water_outlet_node_name",
                "design_specification_multispeed_object_type",
                "design_specification_multispeed_object_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "control_type",
                    "controlling_zone_or_thermostat_location",
                    "dehumidification_control_type",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "supply_fan_object_type",
                    "supply_fan_name",
                    "fan_placement",
                    "supply_air_fan_operating_mode_schedule_name",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "use_doas_dx_cooling_coil",
                    "latent_load_control",
                    "supplemental_heating_coil_object_type",
                    "supplemental_heating_coil_name",
                    "cooling_supply_air_flow_rate_method",
                    "heating_supply_air_flow_rate_method",
                    "no_load_supply_air_flow_rate_method",
                    "outdoor_dry_bulb_temperature_sensor_node_name",
                    "heat_recovery_water_inlet_node_name",
                    "heat_recovery_water_outlet_node_name",
                    "design_specification_multispeed_object_type",
                    "design_specification_multispeed_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "dx_heating_coil_sizing_ratio",
                    "minimum_supply_air_temperature",
                    "cooling_supply_air_flow_rate",
                    "cooling_supply_air_flow_rate_per_floor_area",
                    "cooling_fraction_of_autosized_cooling_supply_air_flow_rate",
                    "cooling_supply_air_flow_rate_per_unit_of_capacity",
                    "heating_supply_air_flow_rate",
                    "heating_supply_air_flow_rate_per_floor_area",
                    "heating_fraction_of_autosized_heating_supply_air_flow_rate",
                    "heating_supply_air_flow_rate_per_unit_of_capacity",
                    "no_load_supply_air_flow_rate",
                    "no_load_supply_air_flow_rate_per_floor_area",
                    "no_load_fraction_of_autosized_cooling_supply_air_flow_rate",
                    "no_load_fraction_of_autosized_heating_supply_air_flow_rate",
                    "no_load_supply_air_flow_rate_per_unit_of_capacity_during_cooling_operation",
                    "no_load_supply_air_flow_rate_per_unit_of_capacity_during_heating_operation",
                    "maximum_supply_air_temperature",
                    "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation",
                    "maximum_cycling_rate",
                    "heat_pump_time_constant",
                    "fraction_of_on_cycle_power_use",
                    "heat_pump_fan_delay_time",
                    "ancillary_on_cycle_electric_power",
                    "ancillary_off_cycle_electric_power",
                    "design_heat_recovery_water_flow_rate",
                    "maximum_temperature_for_heat_recovery"
                ]
            }
        },
        "type": "object",
        "memo": "AirloopHVAC:UnitarySystem is a generic HVAC system type that allows any configuration of coils and/or fan. This object is a replacement of other AirloopHVAC objects. This object can be used in outdoor air systems, outdoor air units, air loops, and as zone equipment if desired.",
        "min_fields": 14.0
    }
}
```
