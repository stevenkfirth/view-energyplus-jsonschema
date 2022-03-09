```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_or_space_name": {
                    "type": "string",
                    "note": "ZoneList and SpaceList names are not allowed.",
                    "data_type": "object_list",
                    "object_list": [
                        "SpaceNames",
                        "ZoneNames"
                    ]
                },
                "air_flow_calculation_method": {
                    "type": "string",
                    "note": "The specified method is used to calculate the IT inlet temperature and zone return air temperature. If FlowFromSystem is chosen, the zone is assumed to be well-mixed. If FlowControlWithApproachTemperatures is chosen, Supply and Return approach temperature should be defined to indicate the temperature difference due to the air distribution. When FlowControlWithApproachTemperatures is chosen, the inputs of Air Inlet Connection Type, Design Recirculation Fraction and Recirculation Function of Loading and Supply Temperature Curve Name are ignored. For multiple ITE objects defined for one zone, the same calculation method should apply. The FlowControlWithApproachTemperatures only applies to ITE zones with single duct VAV terminal unit. Other return air heat gains from window or lights are not allowed when FlowControlWithApproachTemperatures is chosen.",
                    "enum": [
                        "",
                        "FlowControlWithApproachTemperatures",
                        "FlowFromSystem"
                    ],
                    "default": "FlowFromSystem"
                },
                "design_power_input_calculation_method": {
                    "type": "string",
                    "note": "The entered calculation method is used to specify the design power input Watts/Unit => Watts per Unit -- Design Power = Watts per Unit * Number of Units Watts/Area => Watts per Zone Floor Area -- Design Power = Watts per Zone Floor Area * Floor Area",
                    "enum": [
                        "",
                        "Watts/Area",
                        "Watts/Unit"
                    ],
                    "default": "Watts/Unit"
                },
                "watts_per_unit": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "ip-units": "W"
                },
                "number_of_units": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 1.0
                },
                "watts_per_zone_floor_area": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "W/m2",
                    "ip-units": "W/ft2"
                },
                "design_power_input_schedule_name": {
                    "type": "string",
                    "note": "Operating schedule for this equipment, fraction applied to the design power input, generally (0.0 - 1.0) If this field is blank, the schedule is assumed to always be 1.0.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "cpu_loading_schedule_name": {
                    "type": "string",
                    "note": "CPU loading schedule for this equipment as a fraction from 0.0 (idle) to 1.0 (full load). If this field is blank, the schedule is assumed to always be 1.0.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "cpu_power_input_function_of_loading_and_air_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "The name of a two-variable curve or table lookup object which modifies the CPU power input as a function of CPU loading (x) and air inlet node temperature (y). This curve (table) should equal 1.0 at design conditions (CPU loading = 1.0 and Design Entering Air Temperature)."
                },
                "design_fan_power_input_fraction": {
                    "type": "number",
                    "note": "The fraction of the total power input at design conditions which is for the cooling fan(s)",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "design_fan_air_flow_rate_per_power_input": {
                    "type": "number",
                    "note": "The cooling fan air flow rate per total electric power input at design conditions",
                    "units": "m3/s-W",
                    "minimum": 0.0
                },
                "air_flow_function_of_loading_and_air_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "The name of a two-variable curve or table lookup object which modifies the cooling air flow rate as a function of CPU loading (x) and air inlet node temperature (y). This curve (table) should equal 1.0 at design conditions (CPU loading = 1.0 and Design Entering Air Temperature)."
                },
                "fan_power_input_function_of_flow_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "The name of a single-variable curve or table lookup object which modifies the cooling fan power as a function of flow fraction (x). This curve (table) should equal 1.0 at a flow fraction of 1.0."
                },
                "design_entering_air_temperature": {
                    "type": "number",
                    "note": "The entering air temperature at design conditions.",
                    "units": "C",
                    "default": 15.0
                },
                "environmental_class": {
                    "type": "string",
                    "note": "Specifies the allowable operating conditions for the air inlet conditions. Used for reporting time outside allowable conditions.",
                    "enum": [
                        "",
                        "A1",
                        "A2",
                        "A3",
                        "A4",
                        "B",
                        "C",
                        "None"
                    ],
                    "default": "None"
                },
                "air_inlet_connection_type": {
                    "type": "string",
                    "note": "Specifies the type of connection between the zone and the ITE air inlet node. AdjustedSupply = ITE inlet temperature will be the current Supply Air Node temperature adjusted by the current recirculation fraction. All heat output is added to the zone air heat balance as a convective gain. ZoneAirNode = ITE air inlet condition is  the average zone condition. All heat output is added to the zone air heat balance as a convective gain. RoomAirModel = ITE air inlet and outlet are connected to room air model nodes. This field is only used when Air Flow Calculation Method is FlowFromSystem.",
                    "enum": [
                        "",
                        "AdjustedSupply",
                        "RoomAirModel",
                        "ZoneAirNode"
                    ],
                    "default": "AdjustedSupply"
                },
                "air_inlet_room_air_model_node_name": {
                    "type": "string",
                    "note": "Name of a RoomAir:Node object which is connected to the ITE air inlet.",
                    "data_type": "object_list",
                    "object_list": [
                        "RoomAirNodes"
                    ]
                },
                "air_outlet_room_air_model_node_name": {
                    "type": "string",
                    "note": "Name of a RoomAir:Node object which is connected to the ITE air outlet.",
                    "data_type": "object_list",
                    "object_list": [
                        "RoomAirNodes"
                    ]
                },
                "supply_air_node_name": {
                    "type": "string",
                    "note": "Name of the supply air inlet node serving this ITE. Required if the Air Node Connection Type = AdjustedSupply. Also required if Calculation Method = FlowControlWithApproachTemperatures. Also required if reporting of Supply Heat Index is desired."
                },
                "design_recirculation_fraction": {
                    "type": "number",
                    "note": "The recirculation fraction for this equipment at design conditions. This field is used only if the Air Node Connection Type = AdjustedSupply. The default is 0.0 (no recirculation). This field is only used when Air Flow Calculation Method is FlowFromSystem.",
                    "minimum": 0.0,
                    "maximum": 0.5,
                    "default": 0.0
                },
                "recirculation_function_of_loading_and_supply_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "The name of a two-variable curve or table lookup object which modifies the recirculation fractionas a function of CPU loading (x) and supply air node temperature (y). This curve (table) should equal 1.0 at design conditions (CPU loading = 1.0 and Design Entering Air Temperature).This field is used only if the Air Node Connection Type = AdjustedSupply. If this curve is left blank, then the curve is assumed to always equal 1.0. This field is only used when Air Flow Calculation Method is FlowFromSystem."
                },
                "design_electric_power_supply_efficiency": {
                    "type": "number",
                    "note": "The efficiency of the power supply system serving this ITE",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0
                },
                "electric_power_supply_efficiency_function_of_part_load_ratio_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "The name of a single-variable curve or table lookup object which modifies the electric power supply efficiency as a function of part-load ratio (x). This curve (table) should equal 1.0 at full load (PLR = 1.0). If this curve is left blank, then the curve is assumed to always equal 1.0."
                },
                "fraction_of_electric_power_supply_losses_to_zone": {
                    "type": "number",
                    "note": "Fraction of the electric power supply losses which are a heat gain to the zone If this field is <1.0, the remainder of the losses are assumed to be lost to the outdoors.",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0
                },
                "cpu_end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "ITE-CPU"
                },
                "fan_end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "ITE-Fans"
                },
                "electric_power_supply_end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "ITE-UPS"
                },
                "supply_temperature_difference": {
                    "type": "number",
                    "note": "The difference of the IT inlet temperature from the AHU supply air temperature. Either Supply Temperature Difference or Supply Temperature Difference Schedule is required if Air Flow Calculation Method is set to FlowControlWithApproachTemperatures. This field is ignored when Air Flow Calculation Method is FlowFromSystem.",
                    "units": "deltaC"
                },
                "supply_temperature_difference_schedule": {
                    "type": "string",
                    "note": "The difference schedule of the IT inlet temperature from the AHU supply air temperature. Either Supply Temperature Difference or Supply Temperature Difference Schedule is required if Air Flow Calculation Method is set to FlowControlWithApproachTemperatures. This field is ignored when Air Flow Calculation Method is FlowFromSystem.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "return_temperature_difference": {
                    "type": "number",
                    "note": "The difference of the the actual AHU return air temperature to the IT equipment outlet temperature. Either Return Temperature Difference or Return Temperature Difference Schedule is required if Air Flow Calculation Method is set to FlowControlWithApproachTemperatures. This field is ignored when Air Flow Calculation Method is FlowFromSystem.",
                    "units": "deltaC"
                },
                "return_temperature_difference_schedule": {
                    "type": "string",
                    "note": "The difference schedule of the actual AHU return air temperature to the IT equipment outlet temperature. Either Return Temperature Difference or Return Temperature Difference Schedule is required if Air Flow Calculation Method is set to FlowControlWithApproachTemperatures. This field is ignored when Air Flow Calculation Method is FlowFromSystem.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "zone_or_space_name",
                "cpu_power_input_function_of_loading_and_air_temperature_curve_name",
                "design_fan_air_flow_rate_per_power_input",
                "air_flow_function_of_loading_and_air_temperature_curve_name",
                "fan_power_input_function_of_flow_curve_name"
            ]
        }
    },
    "group": "Internal Gains",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "zone_or_space_name": {
                "field_name": "Zone or Space Name",
                "field_type": "a"
            },
            "air_flow_calculation_method": {
                "field_name": "Air Flow Calculation Method",
                "field_type": "a"
            },
            "design_power_input_calculation_method": {
                "field_name": "Design Power Input Calculation Method",
                "field_type": "a"
            },
            "watts_per_unit": {
                "field_name": "Watts per Unit",
                "field_type": "n"
            },
            "number_of_units": {
                "field_name": "Number of Units",
                "field_type": "n"
            },
            "watts_per_zone_floor_area": {
                "field_name": "Watts per Zone Floor Area",
                "field_type": "n"
            },
            "design_power_input_schedule_name": {
                "field_name": "Design Power Input Schedule Name",
                "field_type": "a"
            },
            "cpu_loading_schedule_name": {
                "field_name": "CPU Loading  Schedule Name",
                "field_type": "a"
            },
            "cpu_power_input_function_of_loading_and_air_temperature_curve_name": {
                "field_name": "CPU Power Input Function of Loading and Air Temperature Curve Name",
                "field_type": "a"
            },
            "design_fan_power_input_fraction": {
                "field_name": "Design Fan Power Input Fraction",
                "field_type": "n"
            },
            "design_fan_air_flow_rate_per_power_input": {
                "field_name": "Design Fan Air Flow Rate per Power Input",
                "field_type": "n"
            },
            "air_flow_function_of_loading_and_air_temperature_curve_name": {
                "field_name": "Air Flow Function of Loading and Air Temperature Curve Name",
                "field_type": "a"
            },
            "fan_power_input_function_of_flow_curve_name": {
                "field_name": "Fan Power Input Function of Flow Curve Name",
                "field_type": "a"
            },
            "design_entering_air_temperature": {
                "field_name": "Design Entering Air Temperature",
                "field_type": "n"
            },
            "environmental_class": {
                "field_name": "Environmental Class",
                "field_type": "a"
            },
            "air_inlet_connection_type": {
                "field_name": "Air Inlet Connection Type",
                "field_type": "a"
            },
            "air_inlet_room_air_model_node_name": {
                "field_name": "Air Inlet Room Air Model Node Name",
                "field_type": "a"
            },
            "air_outlet_room_air_model_node_name": {
                "field_name": "Air Outlet Room Air Model Node Name",
                "field_type": "a"
            },
            "supply_air_node_name": {
                "field_name": "Supply Air Node Name",
                "field_type": "a"
            },
            "design_recirculation_fraction": {
                "field_name": "Design Recirculation Fraction",
                "field_type": "n"
            },
            "recirculation_function_of_loading_and_supply_temperature_curve_name": {
                "field_name": "Recirculation Function of Loading and Supply Temperature Curve Name",
                "field_type": "a"
            },
            "design_electric_power_supply_efficiency": {
                "field_name": "Design Electric Power Supply Efficiency",
                "field_type": "n"
            },
            "electric_power_supply_efficiency_function_of_part_load_ratio_curve_name": {
                "field_name": "Electric Power Supply Efficiency Function of Part Load Ratio Curve Name",
                "field_type": "a"
            },
            "fraction_of_electric_power_supply_losses_to_zone": {
                "field_name": "Fraction of Electric Power Supply Losses to Zone",
                "field_type": "n"
            },
            "cpu_end_use_subcategory": {
                "field_name": "CPU End-Use Subcategory",
                "field_type": "a"
            },
            "fan_end_use_subcategory": {
                "field_name": "Fan End-Use Subcategory",
                "field_type": "a"
            },
            "electric_power_supply_end_use_subcategory": {
                "field_name": "Electric Power Supply End-Use Subcategory",
                "field_type": "a"
            },
            "supply_temperature_difference": {
                "field_name": "Supply Temperature Difference",
                "field_type": "n"
            },
            "supply_temperature_difference_schedule": {
                "field_name": "Supply Temperature Difference Schedule",
                "field_type": "a"
            },
            "return_temperature_difference": {
                "field_name": "Return Temperature Difference",
                "field_type": "n"
            },
            "return_temperature_difference_schedule": {
                "field_name": "Return Temperature Difference Schedule",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_or_space_name",
            "air_flow_calculation_method",
            "design_power_input_calculation_method",
            "watts_per_unit",
            "number_of_units",
            "watts_per_zone_floor_area",
            "design_power_input_schedule_name",
            "cpu_loading_schedule_name",
            "cpu_power_input_function_of_loading_and_air_temperature_curve_name",
            "design_fan_power_input_fraction",
            "design_fan_air_flow_rate_per_power_input",
            "air_flow_function_of_loading_and_air_temperature_curve_name",
            "fan_power_input_function_of_flow_curve_name",
            "design_entering_air_temperature",
            "environmental_class",
            "air_inlet_connection_type",
            "air_inlet_room_air_model_node_name",
            "air_outlet_room_air_model_node_name",
            "supply_air_node_name",
            "design_recirculation_fraction",
            "recirculation_function_of_loading_and_supply_temperature_curve_name",
            "design_electric_power_supply_efficiency",
            "electric_power_supply_efficiency_function_of_part_load_ratio_curve_name",
            "fraction_of_electric_power_supply_losses_to_zone",
            "cpu_end_use_subcategory",
            "fan_end_use_subcategory",
            "electric_power_supply_end_use_subcategory",
            "supply_temperature_difference",
            "supply_temperature_difference_schedule",
            "return_temperature_difference",
            "return_temperature_difference_schedule"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_or_space_name",
                "air_flow_calculation_method",
                "design_power_input_calculation_method",
                "design_power_input_schedule_name",
                "cpu_loading_schedule_name",
                "cpu_power_input_function_of_loading_and_air_temperature_curve_name",
                "air_flow_function_of_loading_and_air_temperature_curve_name",
                "fan_power_input_function_of_flow_curve_name",
                "environmental_class",
                "air_inlet_connection_type",
                "air_inlet_room_air_model_node_name",
                "air_outlet_room_air_model_node_name",
                "supply_air_node_name",
                "recirculation_function_of_loading_and_supply_temperature_curve_name",
                "electric_power_supply_efficiency_function_of_part_load_ratio_curve_name",
                "cpu_end_use_subcategory",
                "fan_end_use_subcategory",
                "electric_power_supply_end_use_subcategory",
                "supply_temperature_difference_schedule",
                "return_temperature_difference_schedule"
            ]
        },
        "numerics": {
            "fields": [
                "watts_per_unit",
                "number_of_units",
                "watts_per_zone_floor_area",
                "design_fan_power_input_fraction",
                "design_fan_air_flow_rate_per_power_input",
                "design_entering_air_temperature",
                "design_recirculation_fraction",
                "design_electric_power_supply_efficiency",
                "fraction_of_electric_power_supply_losses_to_zone",
                "supply_temperature_difference",
                "return_temperature_difference"
            ]
        }
    },
    "type": "object",
    "memo": "This object describes air-cooled electric information technology equipment (ITE) which has variable power consumption as a function of loading and temperature. If a Zone comprised of more than one Space is specified then this definition applies to all applicable spaces, and each instance will be named with the Space Name plus this Object Name.",
    "min_fields": 28.0
}
```
