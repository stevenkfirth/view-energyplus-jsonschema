```
{
    "Coil:WaterHeating:Desuperheater": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available. Schedule values of 0 denote the desuperheater heating coil is off and the parasitic electric energy is also off.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "setpoint_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Defines the cut-out temperature where the desuperheater water heating coil turns off. The desuperheater heating coil setpoint temperature should always be greater than the water tank's heater (element or burner) setpoint temperature. Temperature schedule values should be in degrees C."
                    },
                    "dead_band_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "exclusiveMinimum": 0.0,
                        "maximum": 20.0,
                        "default": 5.0,
                        "note": "Setpoint temperature minus the dead band temperature difference defines the cut-in temperature where the desuperheater water heating coil turns on. The water tank's heater (element or burner) setpoint temperature should always be less than the desuperheater heating coil cut-in temperature."
                    },
                    "rated_heat_reclaim_recovery_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the fraction of waste heat reclaimed by the desuperheater water heating coil."
                    },
                    "rated_inlet_water_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "The inlet water temperature corresponding to the rated heat reclaim recovery efficiency."
                    },
                    "rated_outdoor_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "The outdoor air dry-bulb temperature corresponding to the rated heat reclaim recovery efficiency."
                    },
                    "maximum_inlet_water_temperature_for_heat_reclaim": {
                        "type": "number",
                        "units": "C",
                        "note": "The desuperheater water heating coil is off when the inlet water temperature is above the maximum inlet water temperature for heat reclaim."
                    },
                    "heat_reclaim_efficiency_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "A biquadratic curve defining the performance of the desuperheater heating coil. Performance can be specified as a function of inlet water temperature, outdoor air dry-bulb temperature, or both. Curve = a + b*Tw + c*Tw**2 + d*odb + e*odb**2 + f*Tw*odb. Tw = desuperheater heating coil entering water temperature (C). Odb = outdoor dry-bulb temperature at DX system condenser (C)."
                    },
                    "water_inlet_node_name": {
                        "type": "string",
                        "note": "The node from which the desuperheater heating coil draws its inlet water. This name should match the source side outlet node name in the associated water heater tank object."
                    },
                    "water_outlet_node_name": {
                        "type": "string",
                        "note": "The node to which the desuperheater heating coil sends its outlet water. This name should match the source side inlet node name in the associated water heater tank object."
                    },
                    "tank_object_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "WaterHeater:Mixed",
                            "WaterHeater:Stratified"
                        ],
                        "default": "WaterHeater:Mixed",
                        "note": "Specify the type of water heater tank used by this desuperheater water heating coil."
                    },
                    "tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "note": "The name of the water heater tank used by this desuperheater water heating coil. Needs to match the name used in the corresponding water heater object.",
                        "object_list": [
                            "WaterHeaterMixedNames",
                            "WaterHeaterStratifiedNames"
                        ]
                    },
                    "heating_source_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:DX:MultiSpeed",
                            "Coil:Cooling:DX:SingleSpeed",
                            "Coil:Cooling:DX:TwoSpeed",
                            "Coil:Cooling:DX:TwoStageWithHumidityControlMode",
                            "Coil:Cooling:DX:VariableSpeed",
                            "Coil:Cooling:WaterToAirHeatPump:EquationFit",
                            "Refrigeration:CompressorRack",
                            "Refrigeration:Condenser:AirCooled",
                            "Refrigeration:Condenser:EvaporativeCooled",
                            "Refrigeration:Condenser:WaterCooled"
                        ],
                        "note": "The type of DX system that is providing waste heat for reclaim."
                    },
                    "heating_source_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DesuperHeatingCoilSources",
                            "DesuperHeatingWaterOnlySources"
                        ],
                        "note": "The name of the DX system used for heat reclaim."
                    },
                    "water_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "exclusiveMinimum": 0.0,
                        "note": "The operating water flow rate."
                    },
                    "water_pump_power": {
                        "type": "number",
                        "units": "W",
                        "ip-units": "W",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "The water circulation pump electric power."
                    },
                    "fraction_of_pump_heat_to_water": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2,
                        "note": "The fraction of pump heat transferred to the water. The pump is assumed to be downstream of the desuperheater water heating coil."
                    },
                    "on_cycle_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Parasitic electric power consumed when the desuperheater water heating coil operates. Parasitic electric load does not contribute to water heating or the zone air heat balance.",
                        "ip-units": "W"
                    },
                    "off_cycle_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Parasitic electric load consumed when the desuperheater water heating coil is off. Parasitic electric load does not contribute to water heating or the zone air heat balance. Off-cycle parasitic power is 0 when the availability schedule is 0.",
                        "ip-units": "W"
                    }
                },
                "required": [
                    "setpoint_temperature_schedule_name",
                    "rated_inlet_water_temperature",
                    "rated_outdoor_air_temperature",
                    "maximum_inlet_water_temperature_for_heat_reclaim",
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "tank_name",
                    "heating_source_object_type",
                    "heating_source_name",
                    "water_flow_rate"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "Unique name for this instance of a desuperheater water heating coil."
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
                "setpoint_temperature_schedule_name": {
                    "field_name": "Setpoint Temperature Schedule Name",
                    "field_type": "a"
                },
                "dead_band_temperature_difference": {
                    "field_name": "Dead Band Temperature Difference",
                    "field_type": "n"
                },
                "rated_heat_reclaim_recovery_efficiency": {
                    "field_name": "Rated Heat Reclaim Recovery Efficiency",
                    "field_type": "n"
                },
                "rated_inlet_water_temperature": {
                    "field_name": "Rated Inlet Water Temperature",
                    "field_type": "n"
                },
                "rated_outdoor_air_temperature": {
                    "field_name": "Rated Outdoor Air Temperature",
                    "field_type": "n"
                },
                "maximum_inlet_water_temperature_for_heat_reclaim": {
                    "field_name": "Maximum Inlet Water Temperature for Heat Reclaim",
                    "field_type": "n"
                },
                "heat_reclaim_efficiency_function_of_temperature_curve_name": {
                    "field_name": "Heat Reclaim Efficiency Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "water_inlet_node_name": {
                    "field_name": "Water Inlet Node Name",
                    "field_type": "a"
                },
                "water_outlet_node_name": {
                    "field_name": "Water Outlet Node Name",
                    "field_type": "a"
                },
                "tank_object_type": {
                    "field_name": "Tank Object Type",
                    "field_type": "a"
                },
                "tank_name": {
                    "field_name": "Tank Name",
                    "field_type": "a"
                },
                "heating_source_object_type": {
                    "field_name": "Heating Source Object Type",
                    "field_type": "a"
                },
                "heating_source_name": {
                    "field_name": "Heating Source Name",
                    "field_type": "a"
                },
                "water_flow_rate": {
                    "field_name": "Water Flow Rate",
                    "field_type": "n"
                },
                "water_pump_power": {
                    "field_name": "Water Pump Power",
                    "field_type": "n"
                },
                "fraction_of_pump_heat_to_water": {
                    "field_name": "Fraction of Pump Heat to Water",
                    "field_type": "n"
                },
                "on_cycle_parasitic_electric_load": {
                    "field_name": "On-Cycle Parasitic Electric Load",
                    "field_type": "n"
                },
                "off_cycle_parasitic_electric_load": {
                    "field_name": "Off-Cycle Parasitic Electric Load",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "setpoint_temperature_schedule_name",
                "dead_band_temperature_difference",
                "rated_heat_reclaim_recovery_efficiency",
                "rated_inlet_water_temperature",
                "rated_outdoor_air_temperature",
                "maximum_inlet_water_temperature_for_heat_reclaim",
                "heat_reclaim_efficiency_function_of_temperature_curve_name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "tank_object_type",
                "tank_name",
                "heating_source_object_type",
                "heating_source_name",
                "water_flow_rate",
                "water_pump_power",
                "fraction_of_pump_heat_to_water",
                "on_cycle_parasitic_electric_load",
                "off_cycle_parasitic_electric_load"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "setpoint_temperature_schedule_name",
                    "heat_reclaim_efficiency_function_of_temperature_curve_name",
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "tank_object_type",
                    "tank_name",
                    "heating_source_object_type",
                    "heating_source_name"
                ]
            },
            "numerics": {
                "fields": [
                    "dead_band_temperature_difference",
                    "rated_heat_reclaim_recovery_efficiency",
                    "rated_inlet_water_temperature",
                    "rated_outdoor_air_temperature",
                    "maximum_inlet_water_temperature_for_heat_reclaim",
                    "water_flow_rate",
                    "water_pump_power",
                    "fraction_of_pump_heat_to_water",
                    "on_cycle_parasitic_electric_load",
                    "off_cycle_parasitic_electric_load"
                ]
            }
        },
        "type": "object",
        "memo": "Desuperheater air heating coil. The heating energy provided by this coil is reclaimed from the superheated refrigerant gas leaving a compressor and does not impact the performance of the compressor. This coil must be used with a water heater tank, see Water Heater:Mixed.",
        "min_fields": 18.0
    }
}
```
