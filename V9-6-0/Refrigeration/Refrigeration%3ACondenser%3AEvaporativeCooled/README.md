```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "rated_effective_total_heat_rejection_rate": {
                    "type": "number",
                    "note": "Rating as per ARI 490 Be sure the rating corresponds to the correct refrigerant",
                    "minimum": 0.0,
                    "units": "W"
                },
                "rated_subcooling_temperature_difference": {
                    "type": "number",
                    "units": "deltaC",
                    "default": 0.0,
                    "minimum": 0.0,
                    "note": "must correspond to rating given for total heat rejection effect"
                },
                "fan_speed_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Fixed",
                        "FixedLinear",
                        "TwoSpeed",
                        "VariableSpeed"
                    ],
                    "default": "Fixed"
                },
                "rated_fan_power": {
                    "type": "number",
                    "note": "Power for condenser fan(s) corresponding to rated total heat rejection effect.",
                    "units": "W",
                    "minimum": 0.0
                },
                "minimum_fan_air_flow_ratio": {
                    "type": "number",
                    "note": "Minimum air flow fraction through condenser fan",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "default": 0.2
                },
                "approach_temperature_constant_term": {
                    "type": "number",
                    "units": "C",
                    "minimum": 0.0,
                    "maximum": 20.0,
                    "default": 6.63,
                    "note": "A1 in delta T = A1 + A2(hrcf) + A3/(hrcf) + A4(Twb)"
                },
                "approach_temperature_coefficient_2": {
                    "type": "number",
                    "units": "C",
                    "minimum": 0.0,
                    "maximum": 20.0,
                    "default": 0.468,
                    "note": "A2 in delta T = A1 + A2(hrcf) +A3/(hrcf) +A4(Twb)"
                },
                "approach_temperature_coefficient_3": {
                    "type": "number",
                    "units": "C",
                    "minimum": 0.0,
                    "maximum": 30.0,
                    "default": 17.93,
                    "note": "A3 in delta T = A1 + A2(hrcf) +A3/(hrcf) +A4(Twb)"
                },
                "approach_temperature_coefficient_4": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": -20.0,
                    "maximum": 20.0,
                    "default": -0.322,
                    "note": "A4 in deltaT=A1 + A2(hrcf) +A3/(hrcf) +A4(Twb)"
                },
                "minimum_capacity_factor": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 0.5,
                    "note": "taken from manufacturer's Heat Rejection Capacity Factor Table"
                },
                "maximum_capacity_factor": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 5.0,
                    "note": "taken from manufacturer's Heat Rejection Capacity Factor Table"
                },
                "air_inlet_node_name": {
                    "type": "string",
                    "note": "If field is left blank, then the model assumes that the inlet air conditions are the outdoor air conditions for the current timestep (e.g., no adjustment for height above ground)."
                },
                "rated_air_flow_rate": {
                    "units": "m3/s",
                    "default": "Autocalculate",
                    "note": "Used to calculate evaporative condenser water use and fan energy use.",
                    "anyOf": [
                        {
                            "type": "number"
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
                    "note": "This field is only used for periods when the evap condenser is available (field Evaporative Condenser Availability Schedule). For this situation, the heater heats the basin water when the outdoor air dry-bulb temperature falls below the set point temperature, but only when the condenser fans are off (i.e., no refrigerated case load)."
                },
                "basin_heater_setpoint_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 2.0,
                    "default": 2.0,
                    "note": "Enter the outdoor dry-bulb temperature at which the basin heater turns on."
                },
                "rated_water_pump_power": {
                    "units": "W",
                    "default": 1000.0,
                    "note": "Design recirculating water pump power.",
                    "anyOf": [
                        {
                            "type": "number"
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
                    "note": "If blank, water supply is from Mains."
                },
                "evaporative_condenser_availability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Schedule values greater than 0 indicate that evaporative cooling of the condenser is available. This schedule allows the user to define seasonal shutdown/draining of the water cooling system in cold climate applications. For periods with schedule values of 0, the condenser operates as Air Cooled."
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                },
                "condenser_refrigerant_operating_charge_inventory": {
                    "type": "number",
                    "units": "kg",
                    "default": 0.0,
                    "note": "optional input"
                },
                "condensate_receiver_refrigerant_inventory": {
                    "type": "number",
                    "units": "kg",
                    "default": 0.0,
                    "note": "optional input"
                },
                "condensate_piping_refrigerant_inventory": {
                    "type": "number",
                    "units": "kg",
                    "default": 0.0,
                    "note": "optional input"
                }
            },
            "required": [
                "rated_effective_total_heat_rejection_rate",
                "rated_fan_power"
            ]
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DesuperHeatingCoilSources",
            "RefrigerationAllTypesCondenserNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "rated_effective_total_heat_rejection_rate": {
                "field_name": "Rated Effective Total Heat Rejection Rate",
                "field_type": "n"
            },
            "rated_subcooling_temperature_difference": {
                "field_name": "Rated Subcooling Temperature Difference",
                "field_type": "n"
            },
            "fan_speed_control_type": {
                "field_name": "Fan Speed Control Type",
                "field_type": "a"
            },
            "rated_fan_power": {
                "field_name": "Rated Fan Power",
                "field_type": "n"
            },
            "minimum_fan_air_flow_ratio": {
                "field_name": "Minimum Fan Air Flow Ratio",
                "field_type": "n"
            },
            "approach_temperature_constant_term": {
                "field_name": "Approach Temperature Constant Term",
                "field_type": "n"
            },
            "approach_temperature_coefficient_2": {
                "field_name": "Approach Temperature Coefficient 2",
                "field_type": "n"
            },
            "approach_temperature_coefficient_3": {
                "field_name": "Approach Temperature Coefficient 3",
                "field_type": "n"
            },
            "approach_temperature_coefficient_4": {
                "field_name": "Approach Temperature Coefficient 4",
                "field_type": "n"
            },
            "minimum_capacity_factor": {
                "field_name": "Minimum Capacity Factor",
                "field_type": "n"
            },
            "maximum_capacity_factor": {
                "field_name": "Maximum Capacity Factor",
                "field_type": "n"
            },
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "rated_air_flow_rate": {
                "field_name": "Rated Air Flow Rate",
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
            "rated_water_pump_power": {
                "field_name": "Rated Water Pump Power",
                "field_type": "n"
            },
            "evaporative_water_supply_tank_name": {
                "field_name": "Evaporative Water Supply Tank Name",
                "field_type": "a"
            },
            "evaporative_condenser_availability_schedule_name": {
                "field_name": "Evaporative Condenser Availability Schedule Name",
                "field_type": "a"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            },
            "condenser_refrigerant_operating_charge_inventory": {
                "field_name": "Condenser Refrigerant Operating Charge Inventory",
                "field_type": "n"
            },
            "condensate_receiver_refrigerant_inventory": {
                "field_name": "Condensate Receiver Refrigerant Inventory",
                "field_type": "n"
            },
            "condensate_piping_refrigerant_inventory": {
                "field_name": "Condensate Piping Refrigerant Inventory",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "rated_effective_total_heat_rejection_rate",
            "rated_subcooling_temperature_difference",
            "fan_speed_control_type",
            "rated_fan_power",
            "minimum_fan_air_flow_ratio",
            "approach_temperature_constant_term",
            "approach_temperature_coefficient_2",
            "approach_temperature_coefficient_3",
            "approach_temperature_coefficient_4",
            "minimum_capacity_factor",
            "maximum_capacity_factor",
            "air_inlet_node_name",
            "rated_air_flow_rate",
            "basin_heater_capacity",
            "basin_heater_setpoint_temperature",
            "rated_water_pump_power",
            "evaporative_water_supply_tank_name",
            "evaporative_condenser_availability_schedule_name",
            "end_use_subcategory",
            "condenser_refrigerant_operating_charge_inventory",
            "condensate_receiver_refrigerant_inventory",
            "condensate_piping_refrigerant_inventory"
        ],
        "alphas": {
            "fields": [
                "name",
                "fan_speed_control_type",
                "air_inlet_node_name",
                "evaporative_water_supply_tank_name",
                "evaporative_condenser_availability_schedule_name",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "rated_effective_total_heat_rejection_rate",
                "rated_subcooling_temperature_difference",
                "rated_fan_power",
                "minimum_fan_air_flow_ratio",
                "approach_temperature_constant_term",
                "approach_temperature_coefficient_2",
                "approach_temperature_coefficient_3",
                "approach_temperature_coefficient_4",
                "minimum_capacity_factor",
                "maximum_capacity_factor",
                "rated_air_flow_rate",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "rated_water_pump_power",
                "condenser_refrigerant_operating_charge_inventory",
                "condensate_receiver_refrigerant_inventory",
                "condensate_piping_refrigerant_inventory"
            ]
        }
    },
    "type": "object",
    "memo": "Evaporative-cooled condenser for a refrigeration system (Refrigeration:System).",
    "min_fields": 10.0
}
```
