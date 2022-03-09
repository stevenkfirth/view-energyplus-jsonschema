```
{
    "Refrigeration:SecondarySystem": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "refrigerated_case_or_walkin_or_caseandwalkinlist_name": {
                        "type": "string",
                        "note": "Enter the name of a Refrigeration:Case or Refrigeration:WalkIn object. If there is more than one refrigerated case or walk-in served by this secondary system, enter the name of a Refrigeration:CaseAndWalkInList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "RefrigerationCaseAndWalkInAndListNames"
                        ]
                    },
                    "circulating_fluid_type": {
                        "type": "string",
                        "enum": [
                            "FluidAlwaysLiquid",
                            "FluidPhaseChange"
                        ],
                        "note": "If \"FluidAlwaysLiquid\" is selected, the fluid properties must be input using the objects: FluidProperties:Name, FluidProperties:GlycolConcentration, and, if user defined fluid type, FluidProperties:Temperatures and FluidProperties:Concentration. Many sets of fluid properties can be found in GlycolPropertiesRefData.idf. If \"FluidPhaseChange\" is selected, the refrigerant properties must be input using the objects: (if user defined fluid type): FluidProperties:Name, FluidProperties:Temperatures, FluidProperties:Saturated, and FluidProperties:Superheated. Many sets of refrigerant data can be found in FluidPropertiesRefData.idf."
                    },
                    "circulating_fluid_name": {
                        "type": "string",
                        "note": "This must correspond to a name in the FluidProperties:Name object.",
                        "data_type": "object_list",
                        "object_list": [
                            "FluidAndGlycolNames"
                        ]
                    },
                    "evaporator_capacity": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "W",
                        "note": "For \"FluidAlwaysLiquid\", at least one of the two, Evaporator Capacity OR Evaporator Flow Rate for Secondary Fluid, is required. For \"FluidPhaseChange\", the default capacity is the sum of the rated capacities of the Cases and Walk-ins served by the secondary loop."
                    },
                    "evaporator_flow_rate_for_secondary_fluid": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "note": "For \"FluidAlwaysLiquid\", at least one of the two, Evaporator Capacity OR Evaporator Flow Rate for Secondary Fluid, is required. For \"FluidPhaseChange\" loops, this input is not used. (see PhaseChange Circulating Rate)"
                    },
                    "evaporator_evaporating_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "This is the evaporating temperature in the heat exchanger used to chill or condense the secondary loop circulating fluid. It is NOT the temperature in any cases or walk-ins served by the secondary loop."
                    },
                    "evaporator_approach_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "note": "For \"FluidAlwaysLiquid\", this is the rated difference between the temperature of the circulating fluid leaving the heat exchanger and the heat exchanger's rated evaporating temperature. For \"FluidPhaseChange\", this is the difference between the temperature of the evaporating and condensing temperatures in the heat exchanger."
                    },
                    "evaporator_range_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "note": "For \"FluidAlwaysLiquid\", this is the rated difference between the temperature of the circulating fluid entering the heat exchanger and the temperature of the circulating fluid leaving the heat exchanger, and is Required. For \"FluidPhaseChange\", this input is not used."
                    },
                    "number_of_pumps_in_loop": {
                        "type": "number",
                        "default": 1.0
                    },
                    "total_pump_flow_rate": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "note": "For \"FluidAlwaysLiquid\",if not input, Evaporator Flow Rate for Secondary Fluid will be used. For \"FluidPhaseChange\", if not input, this will be calculated using the PhaseChange Circulating Rate."
                    },
                    "total_pump_power": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "W",
                        "note": "Either the Total Pump Power or the Total Pump Head is required."
                    },
                    "total_pump_head": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "Pa",
                        "note": "Either the Total Pump Power or the Total Pump Head is required."
                    },
                    "phasechange_circulating_rate": {
                        "type": "number",
                        "minimum": 1.0,
                        "units": "dimensionless",
                        "default": 2.5,
                        "note": "This is the total mass flow at the pump divided by the gaseous mass flow leaving the refrigeration load."
                    },
                    "pump_drive_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Constant",
                            "Variable"
                        ],
                        "default": "Constant"
                    },
                    "variable_speed_pump_cubic_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Variable Speed Pump Curve Name is applicable to variable speed pumps only."
                    },
                    "pump_motor_heat_to_fluid": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "This is the portion of the pump motor heat added to secondary circulating fluid and is equal to the motor efficiency for non-hermetic motor. Enter 1.0 for a semi-hermetic motor."
                    },
                    "sum_ua_distribution_piping": {
                        "type": "number",
                        "default": 0.0,
                        "units": "W/K",
                        "note": "Use only if you want to include distribution piping heat gain in refrigeration load."
                    },
                    "distribution_piping_zone_name": {
                        "type": "string",
                        "note": "This will be used to determine the temperature used for distribution piping heat gain. The pipe heat gains are also counted as cooling credit for the zone. Required only if Sum UA Distribution Piping >0.0",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "sum_ua_receiver_separator_shell": {
                        "type": "number",
                        "default": 0.0,
                        "units": "W/K",
                        "note": "Use only if you want to include Receiver/Separator Shell heat gain in refrigeration load."
                    },
                    "receiver_separator_zone_name": {
                        "type": "string",
                        "note": "This will be used to determine the temperature used for Receiver/Separator Shell heat gain. The shell heat gains are also counted as cooling credit for the zone. Required only if Sum UA Receiver/Separator Shell >0.0",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "evaporator_refrigerant_inventory": {
                        "type": "number",
                        "units": "kg",
                        "default": 0.0,
                        "note": "This value refers to the refrigerant circulating within the primary system providing cooling to the chiller for the secondary loop, not to the fluid circulating within the secondary loop itself."
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                        "retaincase": true,
                        "default": "General"
                    }
                },
                "required": [
                    "refrigerated_case_or_walkin_or_caseandwalkinlist_name",
                    "circulating_fluid_type",
                    "circulating_fluid_name",
                    "evaporator_evaporating_temperature",
                    "evaporator_approach_temperature_difference"
                ]
            }
        },
        "group": "Refrigeration",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "RefrigerationCascadeCondenserAndSecondarySystemNames",
                "RefrigerationSecondarySystemAndCascadeCondenserAndTransferLoadListNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "refrigerated_case_or_walkin_or_caseandwalkinlist_name": {
                    "field_name": "Refrigerated Case or Walkin or CaseAndWalkInList Name",
                    "field_type": "a"
                },
                "circulating_fluid_type": {
                    "field_name": "Circulating Fluid Type",
                    "field_type": "a"
                },
                "circulating_fluid_name": {
                    "field_name": "Circulating Fluid Name",
                    "field_type": "a"
                },
                "evaporator_capacity": {
                    "field_name": "Evaporator Capacity",
                    "field_type": "n"
                },
                "evaporator_flow_rate_for_secondary_fluid": {
                    "field_name": "Evaporator Flow Rate for Secondary Fluid",
                    "field_type": "n"
                },
                "evaporator_evaporating_temperature": {
                    "field_name": "Evaporator Evaporating Temperature",
                    "field_type": "n"
                },
                "evaporator_approach_temperature_difference": {
                    "field_name": "Evaporator Approach Temperature Difference",
                    "field_type": "n"
                },
                "evaporator_range_temperature_difference": {
                    "field_name": "Evaporator Range Temperature Difference",
                    "field_type": "n"
                },
                "number_of_pumps_in_loop": {
                    "field_name": "Number of Pumps in Loop",
                    "field_type": "n"
                },
                "total_pump_flow_rate": {
                    "field_name": "Total Pump Flow Rate",
                    "field_type": "n"
                },
                "total_pump_power": {
                    "field_name": "Total Pump Power",
                    "field_type": "n"
                },
                "total_pump_head": {
                    "field_name": "Total Pump Head",
                    "field_type": "n"
                },
                "phasechange_circulating_rate": {
                    "field_name": "PhaseChange Circulating Rate",
                    "field_type": "n"
                },
                "pump_drive_type": {
                    "field_name": "Pump Drive Type",
                    "field_type": "a"
                },
                "variable_speed_pump_cubic_curve_name": {
                    "field_name": "Variable Speed Pump Cubic Curve Name",
                    "field_type": "a"
                },
                "pump_motor_heat_to_fluid": {
                    "field_name": "Pump Motor Heat to Fluid",
                    "field_type": "n"
                },
                "sum_ua_distribution_piping": {
                    "field_name": "Sum UA Distribution Piping",
                    "field_type": "n"
                },
                "distribution_piping_zone_name": {
                    "field_name": "Distribution Piping Zone Name",
                    "field_type": "a"
                },
                "sum_ua_receiver_separator_shell": {
                    "field_name": "Sum UA Receiver/Separator Shell",
                    "field_type": "n"
                },
                "receiver_separator_zone_name": {
                    "field_name": "Receiver/Separator Zone Name",
                    "field_type": "a"
                },
                "evaporator_refrigerant_inventory": {
                    "field_name": "Evaporator Refrigerant Inventory",
                    "field_type": "n"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "refrigerated_case_or_walkin_or_caseandwalkinlist_name",
                "circulating_fluid_type",
                "circulating_fluid_name",
                "evaporator_capacity",
                "evaporator_flow_rate_for_secondary_fluid",
                "evaporator_evaporating_temperature",
                "evaporator_approach_temperature_difference",
                "evaporator_range_temperature_difference",
                "number_of_pumps_in_loop",
                "total_pump_flow_rate",
                "total_pump_power",
                "total_pump_head",
                "phasechange_circulating_rate",
                "pump_drive_type",
                "variable_speed_pump_cubic_curve_name",
                "pump_motor_heat_to_fluid",
                "sum_ua_distribution_piping",
                "distribution_piping_zone_name",
                "sum_ua_receiver_separator_shell",
                "receiver_separator_zone_name",
                "evaporator_refrigerant_inventory",
                "end_use_subcategory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "refrigerated_case_or_walkin_or_caseandwalkinlist_name",
                    "circulating_fluid_type",
                    "circulating_fluid_name",
                    "pump_drive_type",
                    "variable_speed_pump_cubic_curve_name",
                    "distribution_piping_zone_name",
                    "receiver_separator_zone_name",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "evaporator_capacity",
                    "evaporator_flow_rate_for_secondary_fluid",
                    "evaporator_evaporating_temperature",
                    "evaporator_approach_temperature_difference",
                    "evaporator_range_temperature_difference",
                    "number_of_pumps_in_loop",
                    "total_pump_flow_rate",
                    "total_pump_power",
                    "total_pump_head",
                    "phasechange_circulating_rate",
                    "pump_motor_heat_to_fluid",
                    "sum_ua_distribution_piping",
                    "sum_ua_receiver_separator_shell",
                    "evaporator_refrigerant_inventory"
                ]
            }
        },
        "type": "object",
        "memo": "Works in conjunction with refrigerated cases and walkins to simulate the performance of a secondary loop supermarket refrigeration system. Heat from the refrigeration loads served by the secondary loop is absorbed by a primary refrigeration system (Refrigeration:System). The SecondarySystem object simulates a heat exchanger that is an evaporator, or refrigeration load, on the primary refrigeration system.",
        "min_fields": 14.0
    }
}
```
