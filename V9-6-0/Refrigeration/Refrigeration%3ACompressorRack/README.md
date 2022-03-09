```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "heat_rejection_location": {
                    "type": "string",
                    "enum": [
                        "",
                        "Outdoors",
                        "Zone"
                    ],
                    "default": "Outdoors"
                },
                "design_compressor_rack_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 2.0,
                    "note": "It is important that this COP correspond to the lowest saturated suction temperature needed to serve all refrigeration loads"
                },
                "compressor_rack_cop_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "It is important that this COP curve correspond to the lowest saturated suction temperature needed to serve all refrigeration loads"
                },
                "design_condenser_fan_power": {
                    "type": "number",
                    "note": "Design power for condenser fan(s).",
                    "units": "W",
                    "minimum": 0.0,
                    "default": 250.0
                },
                "condenser_fan_power_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "condenser_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AirCooled",
                        "EvaporativelyCooled",
                        "WaterCooled"
                    ],
                    "default": "AirCooled",
                    "note": "Applicable only when Heat Rejection Location is Outdoors."
                },
                "water_cooled_condenser_inlet_node_name": {
                    "type": "string"
                },
                "water_cooled_condenser_outlet_node_name": {
                    "type": "string"
                },
                "water_cooled_loop_flow_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "ConstantFlow",
                        "VariableFlow"
                    ],
                    "default": "VariableFlow",
                    "note": "Applicable only when Condenser Type is WaterCooled."
                },
                "water_cooled_condenser_outlet_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Applicable only when loop Flow type is VariableFlow."
                },
                "water_cooled_condenser_design_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "exclusiveMinimum": 0.0,
                    "note": "Applicable only when loop flow type is ConstantFlow."
                },
                "water_cooled_condenser_maximum_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "exclusiveMinimum": 0.0
                },
                "water_cooled_condenser_maximum_water_outlet_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 10.0,
                    "maximum": 60.0,
                    "default": 55.0
                },
                "water_cooled_condenser_minimum_water_inlet_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 10.0,
                    "maximum": 30.0,
                    "default": 10.0
                },
                "evaporative_condenser_availability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled. Schedule values greater than 0 indicate that evaporative cooling of the condenser is available. This schedule allows the user to define seasonal shutdown/draining of the water cooling system in cold climate applications. For periods with schedule values of 0, the condenser operates as AirCooled."
                },
                "evaporative_condenser_effectiveness": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.9,
                    "note": "Applicable only for Condenser Type = EvaporativlyCooled."
                },
                "evaporative_condenser_air_flow_rate": {
                    "units": "m3/s",
                    "default": "Autocalculate",
                    "note": "Applicable only for Condenser Type = EvaporativelyCooled. Used to calculate evaporative condenser water use.",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "basin_heater_capacity": {
                    "type": "number",
                    "units": "W/K",
                    "minimum": 0.0,
                    "default": 200.0,
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled and for periods when the evaporatively cooled condenser is available (field Evaporative Condenser Availability Schedule Name). For this situation, the heater heats the basin water when the outdoor air dry-bulb temperature falls below the setpoint temperature, but only when the condenser fans are off (i.e., no refrigerated case load)."
                },
                "basin_heater_setpoint_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 2.0,
                    "default": 2.0,
                    "note": "Enter the outdoor dry-bulb temperature at which the basin heater turns on."
                },
                "design_evaporative_condenser_water_pump_power": {
                    "units": "W",
                    "default": 1000.0,
                    "note": "Design recirc water pump power for Condenser Type = EvaporativelyCooled. Applicable only for Condenser Type = EvaporativelyCooled.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "evaporative_water_supply_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ],
                    "note": "If blank, water supply is from Mains. Applicable only for Condenser Type = EvaporativelyCooled."
                },
                "condenser_air_inlet_node_name": {
                    "type": "string",
                    "note": "Applicable only when Heat Rejection Location is Outdoors and Condenser Type is not WaterCooled; otherwise, leave field blank. If field is left blank with Heat Rejection Location = Outdoors, then the model assumes that the Inlet Air conditions are the outdoor air conditions for the current timestep (e.g., no adjustment for height above ground)."
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                },
                "refrigeration_case_name_or_walkin_name_or_caseandwalkinlist_name": {
                    "type": "string",
                    "note": "Enter the name of a Refrigeration:Case or Refrigeration:Walkin or Refrigeration:CaseAndWalkinList object.",
                    "data_type": "object_list",
                    "object_list": [
                        "RefrigerationCaseAndWalkInAndListNames"
                    ]
                },
                "heat_rejection_zone_name": {
                    "type": "string",
                    "note": "This must be a controlled zone and appear in a ZoneHVAC:EquipmentConnections object. Required only if walk-in[s] are connected to this rack AND the heat rejection location is \"Zone\"",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                }
            },
            "required": [
                "compressor_rack_cop_function_of_temperature_curve_name"
            ]
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DesuperHeatingCoilSources",
            "validBranchEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "heat_rejection_location": {
                "field_name": "Heat Rejection Location",
                "field_type": "a"
            },
            "design_compressor_rack_cop": {
                "field_name": "Design Compressor Rack COP",
                "field_type": "n"
            },
            "compressor_rack_cop_function_of_temperature_curve_name": {
                "field_name": "Compressor Rack COP Function of Temperature Curve Name",
                "field_type": "a"
            },
            "design_condenser_fan_power": {
                "field_name": "Design Condenser Fan Power",
                "field_type": "n"
            },
            "condenser_fan_power_function_of_temperature_curve_name": {
                "field_name": "Condenser Fan Power Function of Temperature Curve Name",
                "field_type": "a"
            },
            "condenser_type": {
                "field_name": "Condenser Type",
                "field_type": "a"
            },
            "water_cooled_condenser_inlet_node_name": {
                "field_name": "Water-Cooled Condenser Inlet Node Name",
                "field_type": "a"
            },
            "water_cooled_condenser_outlet_node_name": {
                "field_name": "Water-Cooled Condenser Outlet Node Name",
                "field_type": "a"
            },
            "water_cooled_loop_flow_type": {
                "field_name": "Water-Cooled Loop Flow Type",
                "field_type": "a"
            },
            "water_cooled_condenser_outlet_temperature_schedule_name": {
                "field_name": "Water-Cooled Condenser Outlet Temperature Schedule Name",
                "field_type": "a"
            },
            "water_cooled_condenser_design_flow_rate": {
                "field_name": "Water-Cooled Condenser Design Flow Rate",
                "field_type": "n"
            },
            "water_cooled_condenser_maximum_flow_rate": {
                "field_name": "Water-Cooled Condenser Maximum Flow Rate",
                "field_type": "n"
            },
            "water_cooled_condenser_maximum_water_outlet_temperature": {
                "field_name": "Water-Cooled Condenser Maximum Water Outlet Temperature",
                "field_type": "n"
            },
            "water_cooled_condenser_minimum_water_inlet_temperature": {
                "field_name": "Water-Cooled Condenser Minimum Water Inlet Temperature",
                "field_type": "n"
            },
            "evaporative_condenser_availability_schedule_name": {
                "field_name": "Evaporative Condenser Availability Schedule Name",
                "field_type": "a"
            },
            "evaporative_condenser_effectiveness": {
                "field_name": "Evaporative Condenser Effectiveness",
                "field_type": "n"
            },
            "evaporative_condenser_air_flow_rate": {
                "field_name": "Evaporative Condenser Air Flow Rate",
                "field_type": "n"
            },
            "basin_heater_capacity": {
                "field_name": "Basin Heater Capacity",
                "field_type": "n"
            },
            "basin_heater_setpoint_temperature": {
                "field_name": "Basin Heater Setpoint Temperature",
                "field_type": "n"
            },
            "design_evaporative_condenser_water_pump_power": {
                "field_name": "Design Evaporative Condenser Water Pump Power",
                "field_type": "n"
            },
            "evaporative_water_supply_tank_name": {
                "field_name": "Evaporative Water Supply Tank Name",
                "field_type": "a"
            },
            "condenser_air_inlet_node_name": {
                "field_name": "Condenser Air Inlet Node Name",
                "field_type": "a"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            },
            "refrigeration_case_name_or_walkin_name_or_caseandwalkinlist_name": {
                "field_name": "Refrigeration Case Name or WalkIn Name or CaseAndWalkInList Name",
                "field_type": "a"
            },
            "heat_rejection_zone_name": {
                "field_name": "Heat Rejection Zone Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "heat_rejection_location",
            "design_compressor_rack_cop",
            "compressor_rack_cop_function_of_temperature_curve_name",
            "design_condenser_fan_power",
            "condenser_fan_power_function_of_temperature_curve_name",
            "condenser_type",
            "water_cooled_condenser_inlet_node_name",
            "water_cooled_condenser_outlet_node_name",
            "water_cooled_loop_flow_type",
            "water_cooled_condenser_outlet_temperature_schedule_name",
            "water_cooled_condenser_design_flow_rate",
            "water_cooled_condenser_maximum_flow_rate",
            "water_cooled_condenser_maximum_water_outlet_temperature",
            "water_cooled_condenser_minimum_water_inlet_temperature",
            "evaporative_condenser_availability_schedule_name",
            "evaporative_condenser_effectiveness",
            "evaporative_condenser_air_flow_rate",
            "basin_heater_capacity",
            "basin_heater_setpoint_temperature",
            "design_evaporative_condenser_water_pump_power",
            "evaporative_water_supply_tank_name",
            "condenser_air_inlet_node_name",
            "end_use_subcategory",
            "refrigeration_case_name_or_walkin_name_or_caseandwalkinlist_name",
            "heat_rejection_zone_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "heat_rejection_location",
                "compressor_rack_cop_function_of_temperature_curve_name",
                "condenser_fan_power_function_of_temperature_curve_name",
                "condenser_type",
                "water_cooled_condenser_inlet_node_name",
                "water_cooled_condenser_outlet_node_name",
                "water_cooled_loop_flow_type",
                "water_cooled_condenser_outlet_temperature_schedule_name",
                "evaporative_condenser_availability_schedule_name",
                "evaporative_water_supply_tank_name",
                "condenser_air_inlet_node_name",
                "end_use_subcategory",
                "refrigeration_case_name_or_walkin_name_or_caseandwalkinlist_name",
                "heat_rejection_zone_name"
            ]
        },
        "numerics": {
            "fields": [
                "design_compressor_rack_cop",
                "design_condenser_fan_power",
                "water_cooled_condenser_design_flow_rate",
                "water_cooled_condenser_maximum_flow_rate",
                "water_cooled_condenser_maximum_water_outlet_temperature",
                "water_cooled_condenser_minimum_water_inlet_temperature",
                "evaporative_condenser_effectiveness",
                "evaporative_condenser_air_flow_rate",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "design_evaporative_condenser_water_pump_power"
            ]
        }
    },
    "type": "object",
    "memo": "Works in conjunction with the refrigeration case and walk-in objects to simulate the performance of a refrigerated case system. This object models the electric consumption of the rack compressors and the condenser fans. Heat can be rejected either outdoors or to a zone. Compressor rack waste heat can also be reclaimed for use by an optional air- or water-heating coil (Coil:Heating:Desuperheater and Coil:WaterHeating:Desuperheater).",
    "min_fields": 25.0
}
```
