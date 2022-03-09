```
{
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
                "rated_coil_cooling_capacity": {
                    "type": "number",
                    "units": "W"
                },
                "operating_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMaximum": 20.0
                },
                "rated_cooling_source_temperature": {
                    "type": "number",
                    "note": "If DXEvaporator, use evaporating temperature (saturated suction temperature) If BrineCoil, use Brine entering temperature used to set minimum suction pressure for DX systems and minimum brine temp for secondary systems",
                    "units": "C",
                    "minimum": -70.0,
                    "maximum": 40.0
                },
                "rated_total_heating_power": {
                    "type": "number",
                    "units": "W",
                    "note": "Include total for all anti-sweat, door, drip-pan, and floor heater power Do not include defrost heater power"
                },
                "heating_power_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Values will be used to multiply the total heating power Values in the schedule should be between 0.0 and 1.0 For example, this could be used if display door antisweat heaters are turned off at night Defaults to always on if schedule name left blank."
                },
                "rated_cooling_coil_fan_power": {
                    "type": "number",
                    "units": "W",
                    "default": 375.0,
                    "minimum": 0.0
                },
                "rated_circulation_fan_power": {
                    "type": "number",
                    "units": "W",
                    "default": 0.0,
                    "minimum": 0.0
                },
                "rated_total_lighting_power": {
                    "type": "number",
                    "units": "W",
                    "note": "Enter the total (display + task) installed lighting power."
                },
                "lighting_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "The schedule should contain values between 0 and 1 Defaults to always on if schedule name left blank."
                },
                "defrost_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Electric",
                        "HotFluid",
                        "None",
                        "OffCycle"
                    ],
                    "default": "Electric",
                    "note": "HotFluid includes either hot gas defrost for a DX system or Hot Brine defrost if this walk in is cooled by brine from a secondary chiller"
                },
                "defrost_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "TemperatureTermination",
                        "TimeSchedule"
                    ],
                    "default": "TimeSchedule"
                },
                "defrost_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "The schedule values should be 0 (off) or 1 (on)"
                },
                "defrost_drip_down_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "The schedule values should be 0 (off) or 1 (on) The start time for each defrost period in this drip-down schedule should coincide with the start time for each defrost period in the defrost schedule (previous input field). The length of each defrost drip-down period must be greater than or equal to the corresponding defrost period specified in the defrost schedule. This extra time allows the melted frost to drip from the coil before refrigeration is restarted."
                },
                "defrost_power": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "note": "needed for all defrost types except none and offcycle"
                },
                "temperature_termination_defrost_fraction_to_ice": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "note": "This is the portion of the defrost energy that is available to melt frost Needed only for defrost control type TemperatureTermination defaults to 0.7 for electric defrost and to 0.3 for hot fluid defrost"
                },
                "restocking_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Schedule values should be in units of Watts Leave this field blank if no restocking is to be modeled"
                },
                "average_refrigerant_charge_inventory": {
                    "type": "number",
                    "units": "kg",
                    "default": 0.0,
                    "note": "This value is only used if the Cooling Source Type is DXEvaporator"
                },
                "insulated_floor_surface_area": {
                    "type": "number",
                    "units": "m2",
                    "exclusiveMinimum": 0.0,
                    "note": "floor area of walk-in cooler"
                },
                "insulated_floor_u_value": {
                    "type": "number",
                    "units": "W/m2-K",
                    "default": 0.3154,
                    "exclusiveMinimum": 0.0,
                    "note": "The default value corresponds to R18 [ft2-F-hr/Btu] To convert other IP R-values to U, divide 5.678 by the R-value Some examples: R15 is U 0.3785 W/m2-K R5 is U 1.136 W/m2-K"
                },
                "zone_data": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "zone_name": {
                                "type": "string",
                                "note": "This must be a controlled zone and appear in a ZoneHVAC:EquipmentConnections object. The walk-in cooler can face multiple zones. The heat exchange with each zone must be input separately",
                                "data_type": "object_list",
                                "object_list": [
                                    "ZoneNames"
                                ]
                            },
                            "total_insulated_surface_area_facing_zone": {
                                "type": "number",
                                "units": "m2",
                                "exclusiveMinimum": 0.0,
                                "note": "Area should include walls and ceilings, but not doors"
                            },
                            "insulated_surface_u_value_facing_zone": {
                                "type": "number",
                                "units": "W/m2-K",
                                "default": 0.3154,
                                "exclusiveMinimum": 0.0,
                                "note": "The default value corresponds to R18 [ft2-F-hr/Btu] To convert other IP R-values to U, divide 5.678 by the R-value Some examples: R15 is U 0.3785 W/m2-K R5 is U 1.136 W/m2-K"
                            },
                            "area_of_glass_reach_in_doors_facing_zone": {
                                "type": "number",
                                "units": "m2",
                                "default": 0.0
                            },
                            "height_of_glass_reach_in_doors_facing_zone": {
                                "type": "number",
                                "units": "m",
                                "default": 1.5
                            },
                            "glass_reach_in_door_u_value_facing_zone": {
                                "type": "number",
                                "units": "W/m2-K",
                                "default": 1.136,
                                "exclusiveMinimum": 0.0,
                                "note": "The default value corresponds to R5 [ft2-F-hr/Btu] To convert other IP R-values to U, divide 5.678 by the R-value"
                            },
                            "glass_reach_in_door_opening_schedule_name_facing_zone": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "ScheduleNames"
                                ],
                                "note": "Schedule values should all be between 0.0 and 1.0. For example, if the door is open 30% of the time during working hours, then the schedule would hold the value 0.3 during working hours and 0 during other hours If no schedule name is entered, default is 5% open time during all hours"
                            },
                            "area_of_stocking_doors_facing_zone": {
                                "type": "number",
                                "units": "m2",
                                "default": 0.0
                            },
                            "height_of_stocking_doors_facing_zone": {
                                "type": "number",
                                "units": "m",
                                "default": 3.0
                            },
                            "stocking_door_u_value_facing_zone": {
                                "type": "number",
                                "units": "W/m2-K",
                                "default": 0.3785,
                                "exclusiveMinimum": 0.0,
                                "note": "The default value corresponds to R15 [ft2-F-hr/Btu] To convert other IP R-values to U, divide 5.678 by the R-value Some examples: R5 is U 1.136 W/m2-K R18 is U 0.3154 W/m2-K"
                            },
                            "stocking_door_opening_schedule_name_facing_zone": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "ScheduleNames"
                                ],
                                "note": "Schedule values should all be between 0.0 and 1.0. For example, if the door is open 30% of the time during working hours, then the schedule would hold the value 0.3 during working hours and 0 during other hours If no schedule name is entered, default is 5% open time during all hours"
                            },
                            "stocking_door_opening_protection_type_facing_zone": {
                                "type": "string",
                                "enum": [
                                    "",
                                    "AirCurtain",
                                    "None",
                                    "StripCurtain"
                                ],
                                "note": "Use StripCurtain for hanging strips or airlock vestibules",
                                "default": "AirCurtain"
                            }
                        },
                        "type": "object",
                        "required": [
                            "total_insulated_surface_area_facing_zone",
                            "zone_name"
                        ]
                    }
                }
            },
            "required": [
                "rated_coil_cooling_capacity",
                "operating_temperature",
                "rated_cooling_source_temperature",
                "rated_total_heating_power",
                "rated_total_lighting_power",
                "defrost_schedule_name",
                "insulated_floor_surface_area"
            ]
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "RefrigerationCaseAndWalkInAndListNames",
            "RefrigerationCaseAndWalkInNames"
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
            "rated_coil_cooling_capacity": {
                "field_name": "Rated Coil Cooling Capacity",
                "field_type": "n"
            },
            "operating_temperature": {
                "field_name": "Operating Temperature",
                "field_type": "n"
            },
            "rated_cooling_source_temperature": {
                "field_name": "Rated Cooling Source Temperature",
                "field_type": "n"
            },
            "rated_total_heating_power": {
                "field_name": "Rated Total Heating Power",
                "field_type": "n"
            },
            "heating_power_schedule_name": {
                "field_name": "Heating Power Schedule Name",
                "field_type": "a"
            },
            "rated_cooling_coil_fan_power": {
                "field_name": "Rated Cooling Coil Fan Power",
                "field_type": "n"
            },
            "rated_circulation_fan_power": {
                "field_name": "Rated Circulation Fan Power",
                "field_type": "n"
            },
            "rated_total_lighting_power": {
                "field_name": "Rated Total Lighting Power",
                "field_type": "n"
            },
            "lighting_schedule_name": {
                "field_name": "Lighting Schedule Name",
                "field_type": "a"
            },
            "defrost_type": {
                "field_name": "Defrost Type",
                "field_type": "a"
            },
            "defrost_control_type": {
                "field_name": "Defrost Control Type",
                "field_type": "a"
            },
            "defrost_schedule_name": {
                "field_name": "Defrost Schedule Name",
                "field_type": "a"
            },
            "defrost_drip_down_schedule_name": {
                "field_name": "Defrost Drip-Down Schedule Name",
                "field_type": "a"
            },
            "defrost_power": {
                "field_name": "Defrost Power",
                "field_type": "n"
            },
            "temperature_termination_defrost_fraction_to_ice": {
                "field_name": "Temperature Termination Defrost Fraction to Ice",
                "field_type": "n"
            },
            "restocking_schedule_name": {
                "field_name": "Restocking Schedule Name",
                "field_type": "a"
            },
            "average_refrigerant_charge_inventory": {
                "field_name": "Average Refrigerant Charge Inventory",
                "field_type": "n"
            },
            "insulated_floor_surface_area": {
                "field_name": "Insulated Floor Surface Area",
                "field_type": "n"
            },
            "insulated_floor_u_value": {
                "field_name": "Insulated Floor U-Value",
                "field_type": "n"
            },
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "total_insulated_surface_area_facing_zone": {
                "field_name": "Total Insulated Surface Area Facing Zone",
                "field_type": "n"
            },
            "insulated_surface_u_value_facing_zone": {
                "field_name": "Insulated Surface U-Value Facing Zone",
                "field_type": "n"
            },
            "area_of_glass_reach_in_doors_facing_zone": {
                "field_name": "Area of Glass Reach In Doors Facing Zone",
                "field_type": "n"
            },
            "height_of_glass_reach_in_doors_facing_zone": {
                "field_name": "Height of Glass Reach In Doors Facing Zone",
                "field_type": "n"
            },
            "glass_reach_in_door_u_value_facing_zone": {
                "field_name": "Glass Reach In Door U Value Facing Zone",
                "field_type": "n"
            },
            "glass_reach_in_door_opening_schedule_name_facing_zone": {
                "field_name": "Glass Reach In Door Opening Schedule Name Facing Zone",
                "field_type": "a"
            },
            "area_of_stocking_doors_facing_zone": {
                "field_name": "Area of Stocking Doors Facing Zone",
                "field_type": "n"
            },
            "height_of_stocking_doors_facing_zone": {
                "field_name": "Height of Stocking Doors Facing Zone",
                "field_type": "n"
            },
            "stocking_door_u_value_facing_zone": {
                "field_name": "Stocking Door U Value Facing Zone",
                "field_type": "n"
            },
            "stocking_door_opening_schedule_name_facing_zone": {
                "field_name": "Stocking Door Opening Schedule Name Facing Zone",
                "field_type": "a"
            },
            "stocking_door_opening_protection_type_facing_zone": {
                "field_name": "Stocking Door Opening Protection Type Facing Zone",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "rated_coil_cooling_capacity",
            "operating_temperature",
            "rated_cooling_source_temperature",
            "rated_total_heating_power",
            "heating_power_schedule_name",
            "rated_cooling_coil_fan_power",
            "rated_circulation_fan_power",
            "rated_total_lighting_power",
            "lighting_schedule_name",
            "defrost_type",
            "defrost_control_type",
            "defrost_schedule_name",
            "defrost_drip_down_schedule_name",
            "defrost_power",
            "temperature_termination_defrost_fraction_to_ice",
            "restocking_schedule_name",
            "average_refrigerant_charge_inventory",
            "insulated_floor_surface_area",
            "insulated_floor_u_value"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "heating_power_schedule_name",
                "lighting_schedule_name",
                "defrost_type",
                "defrost_control_type",
                "defrost_schedule_name",
                "defrost_drip_down_schedule_name",
                "restocking_schedule_name"
            ],
            "extensions": [
                "zone_name",
                "glass_reach_in_door_opening_schedule_name_facing_zone",
                "stocking_door_opening_schedule_name_facing_zone",
                "stocking_door_opening_protection_type_facing_zone"
            ]
        },
        "numerics": {
            "fields": [
                "rated_coil_cooling_capacity",
                "operating_temperature",
                "rated_cooling_source_temperature",
                "rated_total_heating_power",
                "rated_cooling_coil_fan_power",
                "rated_circulation_fan_power",
                "rated_total_lighting_power",
                "defrost_power",
                "temperature_termination_defrost_fraction_to_ice",
                "average_refrigerant_charge_inventory",
                "insulated_floor_surface_area",
                "insulated_floor_u_value"
            ],
            "extensions": [
                "total_insulated_surface_area_facing_zone",
                "insulated_surface_u_value_facing_zone",
                "area_of_glass_reach_in_doors_facing_zone",
                "height_of_glass_reach_in_doors_facing_zone",
                "glass_reach_in_door_u_value_facing_zone",
                "area_of_stocking_doors_facing_zone",
                "height_of_stocking_doors_facing_zone",
                "stocking_door_u_value_facing_zone"
            ]
        },
        "extensibles": [
            "zone_name",
            "total_insulated_surface_area_facing_zone",
            "insulated_surface_u_value_facing_zone",
            "area_of_glass_reach_in_doors_facing_zone",
            "height_of_glass_reach_in_doors_facing_zone",
            "glass_reach_in_door_u_value_facing_zone",
            "glass_reach_in_door_opening_schedule_name_facing_zone",
            "area_of_stocking_doors_facing_zone",
            "height_of_stocking_doors_facing_zone",
            "stocking_door_u_value_facing_zone",
            "stocking_door_opening_schedule_name_facing_zone",
            "stocking_door_opening_protection_type_facing_zone"
        ],
        "extension": "zone_data"
    },
    "type": "object",
    "memo": "Works in conjunction with a compressor rack, a refrigeration system, or a refrigeration secondary system to simulate the performance of a walk-in cooler. The walk-in cooler model uses information at rated conditions along with input descriptions for heat transfer surfaces facing multiple zones to determine performance.",
    "min_fields": 28.0,
    "extensible_size": 12.0
}
```
