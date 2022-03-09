```
{
    "ZoneHVAC:HybridUnitaryHVAC": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Enter the availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "availability_manager_list_name": {
                        "type": "string",
                        "note": "Enter the name of an AvailabilityManagerAssignmentList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "SystemAvailabilityManagerLists"
                        ]
                    },
                    "minimum_supply_air_temperature_schedule_name": {
                        "type": "string",
                        "note": "Values in this schedule are used as a constraint in choosing the feasible settings for supply air flow rate and ouside air fraction in each operating mode. If this field is blank, no minimum is imposed.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "maximum_supply_air_temperature_schedule_name": {
                        "type": "string",
                        "note": "Values in this schedule are used as a constraint in choosing the feasible settings for supply air flow rate and outdoor air fraction in each operating mode. If this field is blank, no maximum is imposed.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "minimum_supply_air_humidity_ratio_schedule_name": {
                        "type": "string",
                        "note": "Values in this schedule are used as a constraint in choosing the feasible settings for supply air flow rate and outdoor air fraction in each operating mode. If this field is blank, no minimum is imposed.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "maximum_supply_air_humidity_ratio_schedule_name": {
                        "type": "string",
                        "note": "Values in this schedule are used as a constraint in choosing the feasible settings for supply air flow rate and outdoor air fraction in each operating mode. If this field is blank, no maximum is imposed.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "method_to_choose_controlled_inputs_and_part_runtime_fraction": {
                        "type": "string",
                        "note": "Select the method that will be used to choose operating mode(s), supply air flow rate(s), outdoor air fraction(s) and part runtime fraction(s) in each time step. \"Automatic\" = chooses controlled inputs and part runtime fraction(s) to minimize resource use within each time step while best satisfying requested sensible cooling, dehumidification and ventilation, and subject to constraints. \"User Defined\" = EMS will be used to choose controlled inputs and part runtime fraction(s) in each time step. If this field is blank, default to \"Automatic\".",
                        "enum": [
                            "",
                            "Automatic",
                            "User Defined"
                        ],
                        "default": "Automatic"
                    },
                    "return_air_node_name": {
                        "type": "string",
                        "note": "Return air node for the hybrid unit must be a zone exhaust node."
                    },
                    "outdoor_air_node_name": {
                        "type": "string",
                        "note": "Outdoor air node for the hybrid unit must be an outdoor air node."
                    },
                    "supply_air_node_name": {
                        "type": "string",
                        "note": "Supply air node for the hybrid unit must be a zone air inlet node."
                    },
                    "relief_node_name": {
                        "type": "string",
                        "note": "Relief node for the hybrid unit must be a zone exhaust node, unless flow is being balanced elsewhere."
                    },
                    "system_maximum_supply_air_flow_rate": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "note": "The value in this field represents the maximum supply air volume flow rate among all operating modes. Values of extensive variables in lookup tables are normalized by the system maximum supply air mass flow rate that was used to build performance curves. The value in this field is used to rescale the output from exenstive variables to a desired system size.",
                        "units": "m3/s"
                    },
                    "external_static_pressure_at_system_maximum_supply_air_flow_rate": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "note": "Input the external static pressure when the system operates at maximum supply air flow rate. Fan affinity laws are used to scale supply fan power from the values tabulated in lookup tables, to values that match the external static pressure input to this field. If this field is blank, the supply fan power is not scaled from the values tabulated in lookup tables.",
                        "units": "Pa"
                    },
                    "fan_heat_included_in_lookup_tables": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "This field specifies if the fan heat is accounted for in the lookup tables."
                    },
                    "fan_heat_gain_location": {
                        "type": "string",
                        "enum": [
                            "",
                            "MixedAirStream",
                            "SupplyAirStream"
                        ],
                        "default": "SupplyAirStream",
                        "note": "This field specifies where to add the fan heat in the air stream."
                    },
                    "fan_heat_in_air_stream_fraction": {
                        "type": "number",
                        "note": "0.0 means no fan heat is added to the air stream, 1.0 means all fan heat is added to the air stream.",
                        "default": 1.0,
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "scaling_factor": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "note": "The value in this field scales all extensive performance variables including: supply air mass flow rate, fuel uses, and water use. If this field is blank, the default scaling factor is 1.",
                        "default": 1.0
                    },
                    "minimum_time_between_mode_change": {
                        "type": "number",
                        "minimum": 1.0,
                        "note": "Any mode selected will not operate for less time than the value input in this field. If the value in this field is larger than each timestep, the mode selected in one time step will persist in later time steps until the minimum time between mode change is satisfied. Supply air mass flow rate and outdoor air fraction within a mode are not subject to minimum runtime and may change in every time step. Mode 0 does not have a minimum time. If this field is blank, the default minimum time between mode change is 10 minutes.",
                        "units": "minutes",
                        "default": 10.0
                    },
                    "first_fuel_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Coal",
                            "Diesel",
                            "DistrictCooling",
                            "DistrictHeating",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "None",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane",
                            "Steam"
                        ],
                        "note": "Select the fuel type associated with field: \"System Electric Power Lookup Table\" in each mode. If this field is blank, default first fuel type = Electricity.",
                        "default": "Electricity"
                    },
                    "second_fuel_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Coal",
                            "Diesel",
                            "DistrictCooling",
                            "DistrictHeating",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "None",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane",
                            "Steam"
                        ],
                        "note": "Select the fuel type associated with field: \"System Second Fuel Consumption Lookup Table\" in each mode. If this field is blank, default second fuel type = None.",
                        "default": "None"
                    },
                    "third_fuel_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Coal",
                            "Diesel",
                            "DistrictCooling",
                            "DistrictHeating",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "None",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane",
                            "Steam"
                        ],
                        "note": "Select the fuel type associated with field: \"System Third Fuel Consumption Lookup Table\" in each mode. If this field is blank, default third fuel type = None.",
                        "default": "None"
                    },
                    "objective_function_to_minimize": {
                        "type": "string",
                        "enum": [
                            "",
                            "Electricity Use",
                            "Second Fuel Use",
                            "Third Fuel Use",
                            "Water Use"
                        ],
                        "note": "In each time step, controlled variables will be chosen to minimize the selection in this field, subject to constraints. If this field is blank, the objective function will minimize electricity use.",
                        "default": "Electricity Use"
                    },
                    "design_specification_outdoor_air_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DSOASpaceListNames",
                            "DesignSpecificationOutdoorAirNames"
                        ],
                        "note": "Enter the name of a DesignSpecification:OutdoorAir object. Information in that object will be used to compute the minimum outdoor air flow rate in each time step. If this field is blank, the system may still supply outdoor air, if it is capable as described by lookup tables, when doing so is the most efficient way to satisfy other constraints."
                    },
                    "mode_0_name": {
                        "type": "string",
                        "retaincase": true,
                        "note": "Enter a name for Mode 0. Mode 0 describes equipment performance in standby. Mode 0 is usually characterized by electricity use for controls and crankcase heaters, or other standby resouce consumption. Mode 0 will be chosen for any timestep, or portion of timestep, when no ventilation, cooling, humidification, or dehumidification is required. Mode 0 is available at any environmental condition."
                    },
                    "mode_0_supply_air_temperature_lookup_table_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MultivariateFunctions"
                        ],
                        "note": "Enter the name of the Supply Air Temperature Lookup Table for Mode 0. Units for lookup table values should be in C. If this field is blank, Mode 0 will not be considered for any period that requires ventilation, heating, cooling, humidification, or dehumidification. If this field is blank, when Mode 0 is chosen (during standby periods) the supply air temperature will equal the return air temperature."
                    },
                    "mode_0_supply_air_humidity_ratio_lookup_table_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MultivariateFunctions"
                        ],
                        "note": "Enter the name of the Supply Air Humidity Ratio Lookup Table for Mode 0. Units for lookup table values should be in kgWater/kgDryAir. If this field is blank, Mode 0 will not be considered for any period that requires ventilation, heating, cooling, humidification, or dehumidification. If this field is blank, when Mode 0 is chosen (during standby periods) the supply air humidty ratio will equal the return air humidity ratio."
                    },
                    "mode_0_system_electric_power_lookup_table_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MultivariateFunctions"
                        ],
                        "note": "Enter the name of the Electric Power Lookup Table for Mode 0. Units for lookup table values should be in W. If this field is blank, Mode 0 does not consume electricity."
                    },
                    "mode_0_supply_fan_electric_power_lookup_table_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MultivariateFunctions"
                        ],
                        "note": "Enter the name of the Supply Fan Electric Power Lookup Table for Mode 0. Units for lookup table values should be in W. If this field is blank, Mode 0 does not consume electricity for supply fan."
                    },
                    "mode_0_external_static_pressure_lookup_table_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MultivariateFunctions"
                        ],
                        "note": "Enter the name of the External Static Pressure Lookup Table for Mode 0. Units for lookup table values should be in Pa. If this field is blank, external static pressure will not be reported."
                    },
                    "mode_0_system_second_fuel_consumption_lookup_table_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MultivariateFunctions"
                        ],
                        "note": "Enter the name of the System Second Fuel Consumption Lookup Table for Mode 0. Units for lookup table values should be in W. If this field is blank, Mode 0 does not consume a second fuel."
                    },
                    "mode_0_system_third_fuel_consumption_lookup_table_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MultivariateFunctions"
                        ],
                        "note": "Enter the name of the System Third Fuel Consumption Lookup Table for Mode 0. Units for lookup table values should be in W. If this field is blank, Mode 0 does not consume a third fuel."
                    },
                    "mode_0_system_water_use_lookup_table_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MultivariateFunctions"
                        ],
                        "note": "Enter the name of the System Water Use Lookup Table for Mode 0. Units for lookup table values should be in kg/s. If this field is blank, Mode 0 does not consume water."
                    },
                    "mode_0_outdoor_air_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "note": "Enter the outdoor air fraction for Mode 0. If this field is blank, the outdoor air fraction for Mode 0 will be 0.00.",
                        "default": 0.0
                    },
                    "mode_0_supply_air_mass_flow_rate_ratio": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "note": "Enter the supply air mass flow rate ratio for Mode 0. The value in this field will be used to determine the supply air mass flow rate in Mode 0. Supply air mass flow rate ratio describes supply air mass flow rate as a fraction of mass flow rate associated with the value in field: \"System Maximum Supply Air Flow Rate\". If this field is blank, the supply air mass flow rate ratio for Mode 0 will be 0.",
                        "default": 0.0
                    },
                    "modes": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "mode_name": {
                                    "type": "string",
                                    "retaincase": true,
                                    "note": "Enter a name for Mode 1."
                                },
                                "mode_supply_air_temperature_lookup_table_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "MultivariateFunctions"
                                    ],
                                    "note": "Enter the name of the Supply Air Temperature Lookup Table for Mode 1. Units for lookup table values should be in C. If this field is blank, Mode 1 will not be considered for any time step that requires ventilation, heating, cooling, humidification, or dehumidification."
                                },
                                "mode_supply_air_humidity_ratio_lookup_table_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "MultivariateFunctions"
                                    ],
                                    "note": "Enter the name of the Supply Air Humidity Ratio Lookup Table for Mode 1. Units for lookup table values should be in kgWater/kgDryAir. If this field is blank, Mode 1 will not be considered for any time step that requires ventilation, heating, cooling, humidification, or dehumidification."
                                },
                                "mode_system_electric_power_lookup_table_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "MultivariateFunctions"
                                    ],
                                    "note": "Enter the name of the Electric Power Lookup Table for Mode 1. Units for lookup table values should be in W. If this field is blank, Mode 1 does not use electricity"
                                },
                                "mode_supply_fan_electric_power_lookup_table_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "MultivariateFunctions"
                                    ],
                                    "note": "Enter the name of the Supply Fan Electric Power Lookup Table for Mode 1. Units for lookup table values should be in W. If this field is blank, Mode 1 does not use electricity for supply fan."
                                },
                                "mode_external_static_pressure_lookup_table_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "MultivariateFunctions"
                                    ],
                                    "note": "Enter the name of the External Static Pressure Lookup Table for Mode 1. Units for lookup table values should be in Pa. If this field is blank, external static pressure will not be reported for Mode 1."
                                },
                                "mode_system_second_fuel_consumption_lookup_table_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "MultivariateFunctions"
                                    ],
                                    "note": "Enter the name of the System Second Fuel Consumption Lookup Table for Mode 1. Units for lookup table values should be in W. If this field is blank, Mode 1 does not consume a second fuel."
                                },
                                "mode_system_third_fuel_consumption_lookup_table_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "MultivariateFunctions"
                                    ],
                                    "note": "Enter the name of the System Third Fuel Consumption Lookup Table for Mode 1. Units for lookup table values should be in W. If this field is blank, Mode 1 does not consume a third fuel."
                                },
                                "mode_system_water_use_lookup_table_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "MultivariateFunctions"
                                    ],
                                    "note": "Enter the name of the System Water Use Lookup Table for Mode 1. Units for lookup table values should be in kg/s. If this field is blank, Mode 1 does not consume water."
                                },
                                "mode_minimum_outdoor_air_temperature": {
                                    "type": "number",
                                    "units": "C",
                                    "note": "Enter the minimum outdoor air temperature allowed for Mode 1. Mode 1 will not be considered when outdoor air temperature is below the value in this field. If this field is blank, there will be no lower constraint on outdoor air temperature."
                                },
                                "mode_maximum_outdoor_air_temperature": {
                                    "type": "number",
                                    "units": "C",
                                    "note": "Enter the maximum outdoor air temperature allowed for Mode 1. Mode 1 will not be considered wen outdoor air temperature is above the value in this field. If this field is blank, there will be no upper constraint on outdoor air temperature."
                                },
                                "mode_minimum_outdoor_air_humidity_ratio": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 0.1,
                                    "units": "kgWater/kgDryAir",
                                    "note": "Enter the minimum outdoor humidity ratio allowed for Mode 1. Mode 1 will not be considerd when outdoor air absolute humidity is below the value in this field. If this field is blank, the lower constraint on outdoor air humidity ratio will be 0.00 kgWater/kgDryAir.",
                                    "default": 0.0
                                },
                                "mode_maximum_outdoor_air_humidity_ratio": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 0.1,
                                    "units": "kgWater/kgDryAir",
                                    "note": "Enter the maximum outdoor air humidity ratio allowed for Mode 1. Mode 1 will not be considered when outdoor air humidity ratio is above the value in this field. If this field is blank, the upper constraint on outdoor air humidity ratio will be 0.10 kgWater/kgDryAir.",
                                    "default": 0.1
                                },
                                "mode_minimum_outdoor_air_relative_humidity": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 100.0,
                                    "units": "percent",
                                    "note": "Enter the minimum outdoor relative humidity allowed for Mode 1. Mode 1 will not be considered when the outdoor air relative humidity is below the value in this field. If this field is blank, the lower constraint on outdoor air relative humidity will be 0.00%.",
                                    "default": 0.0
                                },
                                "mode_maximum_outdoor_air_relative_humidity": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 100.0,
                                    "units": "percent",
                                    "note": "Enter the maximum outdoor air relative humidity allowed for Mode 1. Relative humidity as percent from 0.00 to 100.00. Mode 1 will not be considered when the outdoor air relative humidity is above the value in this field. If this field is blank, the upper constraint on outdoor air relative humidity will be 100.00%.",
                                    "default": 100.0
                                },
                                "mode_minimum_return_air_temperature": {
                                    "type": "number",
                                    "units": "C",
                                    "note": "Enter the minimum return air temperature allowed for Mode 1. Mode 1 will not be considered when the return air temperature is below the value in this field. If this field is blank, there will be no lower constraint on return air temperature."
                                },
                                "mode_maximum_return_air_temperature": {
                                    "type": "number",
                                    "units": "C",
                                    "note": "Enter the maximum return air temperature allowed for Mode 1. Mode 1 will not be considred when the return air temperature is above the value in this field. If this field is blank, there will be no upper constraint on return air temperature."
                                },
                                "mode_minimum_return_air_humidity_ratio": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 0.1,
                                    "units": "kgWater/kgDryAir",
                                    "note": "Enter the minimum return air humidity ratio allowed for Mode 1. Mode 1 will not be considered when the return air humidity ratio is below the value in this field. If this field is blank, the lower constraint on return air humidity ratio will be 0.00 kgWater/kgDryAir.",
                                    "default": 0.0
                                },
                                "mode_maximum_return_air_humidity_ratio": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 0.1,
                                    "units": "kgWater/kgDryAir",
                                    "note": "Enter the maximum return air humidity ratio allowed for Mode 1. Mode 1 will not be considered when the return air humidity ratio is above the value in this field. If this field is blank, the upper constraint on return air humidity ratio will be 0.10 kgWater/kgDryAir.",
                                    "default": 0.1
                                },
                                "mode_minimum_return_air_relative_humidity": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 100.0,
                                    "units": "percent",
                                    "note": "Enter the minimum return air relative humidity allowed for Mode 1. Relative humidity as percent from 0.00 to 100.00. Mode 1 will not be considered when the return air relative humidity is below the value in this field. If this field is blank, the lower constraint on return air relative humidity will be 0.00%.",
                                    "default": 0.0
                                },
                                "mode_maximum_return_air_relative_humidity": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 100.0,
                                    "units": "percent",
                                    "note": "Enter the maximum return air relative humdity allowed for Mode 1. Relative humidity as percent from 0.00 to 100.00. Mode 1 will not be considered when the return air relative humidity is above the value in this field. If this field is blank, the upper constraint on return air relative humidity will be 100%.",
                                    "default": 100.0
                                },
                                "mode_minimum_outdoor_air_fraction": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 1.0,
                                    "note": "Enter the minimum outdoor air fraction allowed for Mode 1. Outdoor air fractions below this value will not be considered for operation in Mode 1. If this field is blank, the lower constraint on outdoor air fraction will be 0.00.",
                                    "default": 0.1
                                },
                                "mode_maximum_outdoor_air_fraction": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 1.0,
                                    "note": "Enter the maximum outdoor air fraction allowed for Mode 1. Outdoor air fractions above this value will not be considered for operation in Mode 1. If this field is blank, the upper constraint on outdoor air fraction will be 1.00.",
                                    "default": 1.0
                                },
                                "mode_minimum_supply_air_mass_flow_rate_ratio": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 1.0,
                                    "note": "Enter the minimum supply air mass flow rate ratio allowed for Mode 1. Supply air mass flow rate ratios below this value will not be considered for operation in Mode 1. Supply air mass flow rate ratio describes supply air mass flow rate as a fraction of mass flow rate associated with the value in field: \"System Maximum Supply Air Flow Rate\". If this field is blank, the lower constraint on supply air mass flow rate ratio will be 0.10.",
                                    "default": 0.1
                                },
                                "mode_maximum_supply_air_mass_flow_rate_ratio": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 1.0,
                                    "note": "Enter the maximum supply air mass flow rate ratio allowed for Mode 1. Supply air mass flow rate ratios above this value will not be considered for operation in Mode 1. Supply air mass flow rate ratio describes supply air flow rate as a fraction of the value in field: \"System Maximum Supply Air Flow Rate\". If this field is blank, there upper constraint on supply air mass flow rate ratio will be 1.00.",
                                    "default": 1.0
                                }
                            },
                            "type": "object"
                        }
                    }
                },
                "required": [
                    "return_air_node_name",
                    "outdoor_air_node_name",
                    "supply_air_node_name"
                ]
            }
        },
        "group": "Zone HVAC Forced Air Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
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
                "availability_manager_list_name": {
                    "field_name": "Availability Manager List Name",
                    "field_type": "a"
                },
                "minimum_supply_air_temperature_schedule_name": {
                    "field_name": "Minimum Supply Air Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_supply_air_temperature_schedule_name": {
                    "field_name": "Maximum Supply Air Temperature Schedule Name",
                    "field_type": "a"
                },
                "minimum_supply_air_humidity_ratio_schedule_name": {
                    "field_name": "Minimum Supply Air Humidity Ratio Schedule Name",
                    "field_type": "a"
                },
                "maximum_supply_air_humidity_ratio_schedule_name": {
                    "field_name": "Maximum Supply Air Humidity Ratio Schedule Name",
                    "field_type": "a"
                },
                "method_to_choose_controlled_inputs_and_part_runtime_fraction": {
                    "field_name": "Method to Choose Controlled Inputs and Part Runtime Fraction",
                    "field_type": "a"
                },
                "return_air_node_name": {
                    "field_name": "Return Air Node Name",
                    "field_type": "a"
                },
                "outdoor_air_node_name": {
                    "field_name": "Outdoor Air Node Name",
                    "field_type": "a"
                },
                "supply_air_node_name": {
                    "field_name": "Supply Air Node Name",
                    "field_type": "a"
                },
                "relief_node_name": {
                    "field_name": "Relief Node Name",
                    "field_type": "a"
                },
                "system_maximum_supply_air_flow_rate": {
                    "field_name": "System Maximum Supply Air Flow Rate",
                    "field_type": "n"
                },
                "external_static_pressure_at_system_maximum_supply_air_flow_rate": {
                    "field_name": "External Static Pressure at System Maximum Supply Air Flow Rate",
                    "field_type": "n"
                },
                "fan_heat_included_in_lookup_tables": {
                    "field_name": "Fan Heat Included in Lookup Tables",
                    "field_type": "a"
                },
                "fan_heat_gain_location": {
                    "field_name": "Fan Heat Gain Location",
                    "field_type": "a"
                },
                "fan_heat_in_air_stream_fraction": {
                    "field_name": "Fan Heat In Air Stream Fraction",
                    "field_type": "n"
                },
                "scaling_factor": {
                    "field_name": "Scaling Factor",
                    "field_type": "n"
                },
                "minimum_time_between_mode_change": {
                    "field_name": "Minimum Time Between Mode Change",
                    "field_type": "n"
                },
                "first_fuel_type": {
                    "field_name": "First Fuel Type",
                    "field_type": "a"
                },
                "second_fuel_type": {
                    "field_name": "Second Fuel Type",
                    "field_type": "a"
                },
                "third_fuel_type": {
                    "field_name": "Third Fuel Type",
                    "field_type": "a"
                },
                "objective_function_to_minimize": {
                    "field_name": "Objective Function to Minimize",
                    "field_type": "a"
                },
                "design_specification_outdoor_air_object_name": {
                    "field_name": "Design Specification Outdoor Air Object Name",
                    "field_type": "a"
                },
                "mode_0_name": {
                    "field_name": "Mode 0 Name",
                    "field_type": "a"
                },
                "mode_0_supply_air_temperature_lookup_table_name": {
                    "field_name": "Mode 0 Supply Air Temperature Lookup Table Name",
                    "field_type": "a"
                },
                "mode_0_supply_air_humidity_ratio_lookup_table_name": {
                    "field_name": "Mode 0 Supply Air Humidity Ratio Lookup Table Name",
                    "field_type": "a"
                },
                "mode_0_system_electric_power_lookup_table_name": {
                    "field_name": "Mode 0 System Electric Power Lookup Table Name",
                    "field_type": "a"
                },
                "mode_0_supply_fan_electric_power_lookup_table_name": {
                    "field_name": "Mode 0 Supply Fan Electric Power Lookup Table Name",
                    "field_type": "a"
                },
                "mode_0_external_static_pressure_lookup_table_name": {
                    "field_name": "Mode 0 External Static Pressure Lookup Table Name",
                    "field_type": "a"
                },
                "mode_0_system_second_fuel_consumption_lookup_table_name": {
                    "field_name": "Mode 0 System Second Fuel Consumption Lookup Table Name",
                    "field_type": "a"
                },
                "mode_0_system_third_fuel_consumption_lookup_table_name": {
                    "field_name": "Mode 0 System Third Fuel Consumption Lookup Table Name",
                    "field_type": "a"
                },
                "mode_0_system_water_use_lookup_table_name": {
                    "field_name": "Mode 0 System Water Use Lookup Table Name",
                    "field_type": "a"
                },
                "mode_0_outdoor_air_fraction": {
                    "field_name": "Mode 0 Outdoor Air Fraction",
                    "field_type": "n"
                },
                "mode_0_supply_air_mass_flow_rate_ratio": {
                    "field_name": "Mode 0 Supply Air Mass Flow Rate Ratio",
                    "field_type": "n"
                },
                "mode_name": {
                    "field_name": "Mode Name",
                    "field_type": "a"
                },
                "mode_supply_air_temperature_lookup_table_name": {
                    "field_name": "Mode Supply Air Temperature Lookup Table Name",
                    "field_type": "a"
                },
                "mode_supply_air_humidity_ratio_lookup_table_name": {
                    "field_name": "Mode Supply Air Humidity Ratio Lookup Table Name",
                    "field_type": "a"
                },
                "mode_system_electric_power_lookup_table_name": {
                    "field_name": "Mode System Electric Power Lookup Table Name",
                    "field_type": "a"
                },
                "mode_supply_fan_electric_power_lookup_table_name": {
                    "field_name": "Mode Supply Fan Electric Power Lookup Table Name",
                    "field_type": "a"
                },
                "mode_external_static_pressure_lookup_table_name": {
                    "field_name": "Mode External Static Pressure Lookup Table Name",
                    "field_type": "a"
                },
                "mode_system_second_fuel_consumption_lookup_table_name": {
                    "field_name": "Mode System Second Fuel Consumption Lookup Table Name",
                    "field_type": "a"
                },
                "mode_system_third_fuel_consumption_lookup_table_name": {
                    "field_name": "Mode System Third Fuel Consumption Lookup Table Name",
                    "field_type": "a"
                },
                "mode_system_water_use_lookup_table_name": {
                    "field_name": "Mode System Water Use Lookup Table Name",
                    "field_type": "a"
                },
                "mode_minimum_outdoor_air_temperature": {
                    "field_name": "Mode Minimum Outdoor Air Temperature",
                    "field_type": "n"
                },
                "mode_maximum_outdoor_air_temperature": {
                    "field_name": "Mode Maximum Outdoor Air Temperature",
                    "field_type": "n"
                },
                "mode_minimum_outdoor_air_humidity_ratio": {
                    "field_name": "Mode Minimum Outdoor Air Humidity Ratio",
                    "field_type": "n"
                },
                "mode_maximum_outdoor_air_humidity_ratio": {
                    "field_name": "Mode Maximum Outdoor Air Humidity Ratio",
                    "field_type": "n"
                },
                "mode_minimum_outdoor_air_relative_humidity": {
                    "field_name": "Mode Minimum Outdoor Air Relative Humidity",
                    "field_type": "n"
                },
                "mode_maximum_outdoor_air_relative_humidity": {
                    "field_name": "Mode Maximum Outdoor Air Relative Humidity",
                    "field_type": "n"
                },
                "mode_minimum_return_air_temperature": {
                    "field_name": "Mode Minimum Return Air Temperature",
                    "field_type": "n"
                },
                "mode_maximum_return_air_temperature": {
                    "field_name": "Mode Maximum Return Air Temperature",
                    "field_type": "n"
                },
                "mode_minimum_return_air_humidity_ratio": {
                    "field_name": "Mode Minimum Return Air Humidity Ratio",
                    "field_type": "n"
                },
                "mode_maximum_return_air_humidity_ratio": {
                    "field_name": "Mode Maximum Return Air Humidity Ratio",
                    "field_type": "n"
                },
                "mode_minimum_return_air_relative_humidity": {
                    "field_name": "Mode Minimum Return Air Relative Humidity",
                    "field_type": "n"
                },
                "mode_maximum_return_air_relative_humidity": {
                    "field_name": "Mode Maximum Return Air Relative Humidity",
                    "field_type": "n"
                },
                "mode_minimum_outdoor_air_fraction": {
                    "field_name": "Mode Minimum Outdoor Air Fraction",
                    "field_type": "n"
                },
                "mode_maximum_outdoor_air_fraction": {
                    "field_name": "Mode Maximum Outdoor Air Fraction",
                    "field_type": "n"
                },
                "mode_minimum_supply_air_mass_flow_rate_ratio": {
                    "field_name": "Mode Minimum Supply Air Mass Flow Rate Ratio",
                    "field_type": "n"
                },
                "mode_maximum_supply_air_mass_flow_rate_ratio": {
                    "field_name": "Mode Maximum Supply Air Mass Flow Rate Ratio",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "availability_manager_list_name",
                "minimum_supply_air_temperature_schedule_name",
                "maximum_supply_air_temperature_schedule_name",
                "minimum_supply_air_humidity_ratio_schedule_name",
                "maximum_supply_air_humidity_ratio_schedule_name",
                "method_to_choose_controlled_inputs_and_part_runtime_fraction",
                "return_air_node_name",
                "outdoor_air_node_name",
                "supply_air_node_name",
                "relief_node_name",
                "system_maximum_supply_air_flow_rate",
                "external_static_pressure_at_system_maximum_supply_air_flow_rate",
                "fan_heat_included_in_lookup_tables",
                "fan_heat_gain_location",
                "fan_heat_in_air_stream_fraction",
                "scaling_factor",
                "minimum_time_between_mode_change",
                "first_fuel_type",
                "second_fuel_type",
                "third_fuel_type",
                "objective_function_to_minimize",
                "design_specification_outdoor_air_object_name",
                "mode_0_name",
                "mode_0_supply_air_temperature_lookup_table_name",
                "mode_0_supply_air_humidity_ratio_lookup_table_name",
                "mode_0_system_electric_power_lookup_table_name",
                "mode_0_supply_fan_electric_power_lookup_table_name",
                "mode_0_external_static_pressure_lookup_table_name",
                "mode_0_system_second_fuel_consumption_lookup_table_name",
                "mode_0_system_third_fuel_consumption_lookup_table_name",
                "mode_0_system_water_use_lookup_table_name",
                "mode_0_outdoor_air_fraction",
                "mode_0_supply_air_mass_flow_rate_ratio"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "availability_manager_list_name",
                    "minimum_supply_air_temperature_schedule_name",
                    "maximum_supply_air_temperature_schedule_name",
                    "minimum_supply_air_humidity_ratio_schedule_name",
                    "maximum_supply_air_humidity_ratio_schedule_name",
                    "method_to_choose_controlled_inputs_and_part_runtime_fraction",
                    "return_air_node_name",
                    "outdoor_air_node_name",
                    "supply_air_node_name",
                    "relief_node_name",
                    "fan_heat_included_in_lookup_tables",
                    "fan_heat_gain_location",
                    "first_fuel_type",
                    "second_fuel_type",
                    "third_fuel_type",
                    "objective_function_to_minimize",
                    "design_specification_outdoor_air_object_name",
                    "mode_0_name",
                    "mode_0_supply_air_temperature_lookup_table_name",
                    "mode_0_supply_air_humidity_ratio_lookup_table_name",
                    "mode_0_system_electric_power_lookup_table_name",
                    "mode_0_supply_fan_electric_power_lookup_table_name",
                    "mode_0_external_static_pressure_lookup_table_name",
                    "mode_0_system_second_fuel_consumption_lookup_table_name",
                    "mode_0_system_third_fuel_consumption_lookup_table_name",
                    "mode_0_system_water_use_lookup_table_name"
                ],
                "extensions": [
                    "mode_name",
                    "mode_supply_air_temperature_lookup_table_name",
                    "mode_supply_air_humidity_ratio_lookup_table_name",
                    "mode_system_electric_power_lookup_table_name",
                    "mode_supply_fan_electric_power_lookup_table_name",
                    "mode_external_static_pressure_lookup_table_name",
                    "mode_system_second_fuel_consumption_lookup_table_name",
                    "mode_system_third_fuel_consumption_lookup_table_name",
                    "mode_system_water_use_lookup_table_name"
                ]
            },
            "numerics": {
                "fields": [
                    "system_maximum_supply_air_flow_rate",
                    "external_static_pressure_at_system_maximum_supply_air_flow_rate",
                    "fan_heat_in_air_stream_fraction",
                    "scaling_factor",
                    "minimum_time_between_mode_change",
                    "mode_0_outdoor_air_fraction",
                    "mode_0_supply_air_mass_flow_rate_ratio"
                ],
                "extensions": [
                    "mode_minimum_outdoor_air_temperature",
                    "mode_maximum_outdoor_air_temperature",
                    "mode_minimum_outdoor_air_humidity_ratio",
                    "mode_maximum_outdoor_air_humidity_ratio",
                    "mode_minimum_outdoor_air_relative_humidity",
                    "mode_maximum_outdoor_air_relative_humidity",
                    "mode_minimum_return_air_temperature",
                    "mode_maximum_return_air_temperature",
                    "mode_minimum_return_air_humidity_ratio",
                    "mode_maximum_return_air_humidity_ratio",
                    "mode_minimum_return_air_relative_humidity",
                    "mode_maximum_return_air_relative_humidity",
                    "mode_minimum_outdoor_air_fraction",
                    "mode_maximum_outdoor_air_fraction",
                    "mode_minimum_supply_air_mass_flow_rate_ratio",
                    "mode_maximum_supply_air_mass_flow_rate_ratio"
                ]
            },
            "extensibles": [
                "mode_name",
                "mode_supply_air_temperature_lookup_table_name",
                "mode_supply_air_humidity_ratio_lookup_table_name",
                "mode_system_electric_power_lookup_table_name",
                "mode_supply_fan_electric_power_lookup_table_name",
                "mode_external_static_pressure_lookup_table_name",
                "mode_system_second_fuel_consumption_lookup_table_name",
                "mode_system_third_fuel_consumption_lookup_table_name",
                "mode_system_water_use_lookup_table_name",
                "mode_minimum_outdoor_air_temperature",
                "mode_maximum_outdoor_air_temperature",
                "mode_minimum_outdoor_air_humidity_ratio",
                "mode_maximum_outdoor_air_humidity_ratio",
                "mode_minimum_outdoor_air_relative_humidity",
                "mode_maximum_outdoor_air_relative_humidity",
                "mode_minimum_return_air_temperature",
                "mode_maximum_return_air_temperature",
                "mode_minimum_return_air_humidity_ratio",
                "mode_maximum_return_air_humidity_ratio",
                "mode_minimum_return_air_relative_humidity",
                "mode_maximum_return_air_relative_humidity",
                "mode_minimum_outdoor_air_fraction",
                "mode_maximum_outdoor_air_fraction",
                "mode_minimum_supply_air_mass_flow_rate_ratio",
                "mode_maximum_supply_air_mass_flow_rate_ratio"
            ],
            "extension": "modes"
        },
        "type": "object",
        "memo": "Hybrid Unitary HVAC. A black box model for multi-mode packaged forced air equipment. Independent variables include outdoor air conditions and indoor air conditions. Controlled inputs include operating mode, supply air flow rate, and outdoor air faction. Emperical lookup tables are required to map supply air temperature supply air humidity, electricity use, fuel uses, water use, fan electricity use, and external static pressure as a function of each indpednent varaible and each controlled input. In each timestep the model will choose one or more combinations of settings for mode, supply air flow rate, outdoor air faction, and part runtime fraction so as to satisfy zone requests for sensible cooling, heating, ventilation, and/or dehumidification with the least resource consumption. Equipment in this class may consume electricity, water, and up to two additional fuel types.",
        "extensible_size": 25.0
    }
}
```
