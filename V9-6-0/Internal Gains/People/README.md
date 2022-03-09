```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_or_zonelist_or_space_or_spacelist_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SpaceAndSpaceListNames",
                        "ZoneAndZoneListNames"
                    ]
                },
                "number_of_people_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "note": "units in schedule should be fraction applied to number of people (0.0 - 1.0)",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_people_calculation_method": {
                    "type": "string",
                    "note": "The entered calculation method is used to create the maximum number of people for this set of attributes (i.e. sensible fraction, schedule, etc) Choices: People -- simply enter number of occupants. People per Floor Area -- enter the number to apply. Value * Floor Area = Number of people Floor Area per Person -- enter the number to apply. Floor Area / Value = Number of people",
                    "enum": [
                        "",
                        "Area/Person",
                        "People",
                        "People/Area"
                    ],
                    "default": "People"
                },
                "number_of_people": {
                    "type": "number",
                    "minimum": 0.0
                },
                "people_per_floor_area": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "person/m2"
                },
                "floor_area_per_person": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "m2/person"
                },
                "fraction_radiant": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.3,
                    "note": "This is radiant fraction of the sensible heat released by people in a zone. This value will be multiplied by the total sensible heat released by people yields the amount of long wavelength radiation gain from people in a zone. Default value is 0.30."
                },
                "sensible_heat_fraction": {
                    "note": "if input, overrides program calculated sensible/latent split",
                    "default": "Autocalculate",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0,
                            "maximum": 1.0
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
                "activity_level_schedule_name": {
                    "type": "string",
                    "note": "Note that W has to be converted to mets in TC routine units in schedule are W/person",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "carbon_dioxide_generation_rate": {
                    "type": "number",
                    "note": "CO2 generation rate per unit of activity level. The default value is obtained from ASHRAE Std 62.1 at 0.0084 cfm/met/person over the general adult population.",
                    "units": "m3/s-W",
                    "default": 3.82e-08,
                    "minimum": 0.0,
                    "maximum": 3.82e-07
                },
                "enable_ashrae_55_comfort_warnings": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "mean_radiant_temperature_calculation_type": {
                    "type": "string",
                    "note": "optional (only required for thermal comfort runs)",
                    "enum": [
                        "",
                        "AngleFactor",
                        "SurfaceWeighted",
                        "ZoneAveraged"
                    ],
                    "default": "ZoneAveraged"
                },
                "surface_name_angle_factor_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AllHeatTranAngFacNames"
                    ],
                    "note": "optional (only required for runs of thermal comfort models: Fanger, Pierce, KSU, CoolingEffectASH55 and AnkleDraftASH55)"
                },
                "work_efficiency_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "units in schedule are 0.0 to 1.0 optional (only required for runs of thermal comfort models: Fanger, Pierce, KSU, CoolingEffectASH55 and AnkleDraftASH55)"
                },
                "clothing_insulation_calculation_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "CalculationMethodSchedule",
                        "ClothingInsulationSchedule",
                        "DynamicClothingModelASHRAE55"
                    ],
                    "default": "ClothingInsulationSchedule"
                },
                "clothing_insulation_calculation_method_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "a schedule value of 1 for the Scheduled method, and 2 for the DynamicClothingModelASHRAE55 method"
                },
                "clothing_insulation_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "use \"Clo\" from ASHRAE or Thermal Comfort guides optional (only required for runs of thermal comfort models: Fanger, Pierce, KSU, CoolingEffectASH55 and AnkleDraftASH55)"
                },
                "air_velocity_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "units in the schedule are m/s optional (only required for runs of thermal comfort models: Fanger, Pierce, KSU, CoolingEffectASH55 and AnkleDraftASH55)"
                },
                "thermal_comfort_model_1_type": {
                    "type": "string",
                    "enum": [
                        "AdaptiveASH55",
                        "AdaptiveCEN15251",
                        "AnkleDraftASH55",
                        "CoolingEffectASH55",
                        "Fanger",
                        "KSU",
                        "Pierce"
                    ],
                    "note": "optional (only needed for people thermal comfort results reporting)"
                },
                "thermal_comfort_model_2_type": {
                    "type": "string",
                    "enum": [
                        "AdaptiveASH55",
                        "AdaptiveCEN15251",
                        "AnkleDraftASH55",
                        "CoolingEffectASH55",
                        "Fanger",
                        "KSU",
                        "Pierce"
                    ],
                    "note": "optional (second type of thermal comfort model and results reporting)"
                },
                "thermal_comfort_model_3_type": {
                    "type": "string",
                    "enum": [
                        "AdaptiveASH55",
                        "AdaptiveCEN15251",
                        "AnkleDraftASH55",
                        "CoolingEffectASH55",
                        "Fanger",
                        "KSU",
                        "Pierce"
                    ],
                    "note": "optional (third thermal comfort model and report type)"
                },
                "thermal_comfort_model_4_type": {
                    "type": "string",
                    "enum": [
                        "AdaptiveASH55",
                        "AdaptiveCEN15251",
                        "AnkleDraftASH55",
                        "CoolingEffectASH55",
                        "Fanger",
                        "KSU",
                        "Pierce"
                    ],
                    "note": "optional (fourth thermal comfort model and report type)"
                },
                "thermal_comfort_model_5_type": {
                    "type": "string",
                    "enum": [
                        "AdaptiveASH55",
                        "AdaptiveCEN15251",
                        "AnkleDraftASH55",
                        "CoolingEffectASH55",
                        "Fanger",
                        "KSU",
                        "Pierce"
                    ],
                    "note": "optional (fifth thermal comfort model and report type)"
                },
                "thermal_comfort_model_6_type": {
                    "type": "string",
                    "enum": [
                        "AdaptiveASH55",
                        "AdaptiveCEN15251",
                        "AnkleDraftASH55",
                        "CoolingEffectASH55",
                        "Fanger",
                        "KSU",
                        "Pierce"
                    ],
                    "note": "optional (sixth thermal comfort model and report type)"
                },
                "thermal_comfort_model_7_type": {
                    "type": "string",
                    "enum": [
                        "AdaptiveASH55",
                        "AdaptiveCEN15251",
                        "AnkleDraftASH55",
                        "CoolingEffectASH55",
                        "Fanger",
                        "KSU",
                        "Pierce"
                    ],
                    "note": "optional (seventh thermal comfort model and report type)"
                },
                "ankle_level_air_velocity_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "units in the schedule are m/s this is the schedule of the air speed at the 0.1 m above the floor optional (only required for runs of thermal comfort models AnkleDraftASH55)"
                }
            },
            "required": [
                "zone_or_zonelist_or_space_or_spacelist_name",
                "number_of_people_schedule_name",
                "activity_level_schedule_name"
            ]
        }
    },
    "group": "Internal Gains",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "PeopleNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "zone_or_zonelist_or_space_or_spacelist_name": {
                "field_name": "Zone or ZoneList or Space or SpaceList Name",
                "field_type": "a"
            },
            "number_of_people_schedule_name": {
                "field_name": "Number of People Schedule Name",
                "field_type": "a"
            },
            "number_of_people_calculation_method": {
                "field_name": "Number of People Calculation Method",
                "field_type": "a"
            },
            "number_of_people": {
                "field_name": "Number of People",
                "field_type": "n"
            },
            "people_per_floor_area": {
                "field_name": "People per Floor Area",
                "field_type": "n"
            },
            "floor_area_per_person": {
                "field_name": "Floor Area per Person",
                "field_type": "n"
            },
            "fraction_radiant": {
                "field_name": "Fraction Radiant",
                "field_type": "n"
            },
            "sensible_heat_fraction": {
                "field_name": "Sensible Heat Fraction",
                "field_type": "n"
            },
            "activity_level_schedule_name": {
                "field_name": "Activity Level Schedule Name",
                "field_type": "a"
            },
            "carbon_dioxide_generation_rate": {
                "field_name": "Carbon Dioxide Generation Rate",
                "field_type": "n"
            },
            "enable_ashrae_55_comfort_warnings": {
                "field_name": "Enable ASHRAE 55 Comfort Warnings",
                "field_type": "a"
            },
            "mean_radiant_temperature_calculation_type": {
                "field_name": "Mean Radiant Temperature Calculation Type",
                "field_type": "a"
            },
            "surface_name_angle_factor_list_name": {
                "field_name": "Surface Name/Angle Factor List Name",
                "field_type": "a"
            },
            "work_efficiency_schedule_name": {
                "field_name": "Work Efficiency Schedule Name",
                "field_type": "a"
            },
            "clothing_insulation_calculation_method": {
                "field_name": "Clothing Insulation Calculation Method",
                "field_type": "a"
            },
            "clothing_insulation_calculation_method_schedule_name": {
                "field_name": "Clothing Insulation Calculation Method Schedule Name",
                "field_type": "a"
            },
            "clothing_insulation_schedule_name": {
                "field_name": "Clothing Insulation Schedule Name",
                "field_type": "a"
            },
            "air_velocity_schedule_name": {
                "field_name": "Air Velocity Schedule Name",
                "field_type": "a"
            },
            "thermal_comfort_model_1_type": {
                "field_name": "Thermal Comfort Model 1 Type",
                "field_type": "a"
            },
            "thermal_comfort_model_2_type": {
                "field_name": "Thermal Comfort Model 2 Type",
                "field_type": "a"
            },
            "thermal_comfort_model_3_type": {
                "field_name": "Thermal Comfort Model 3 Type",
                "field_type": "a"
            },
            "thermal_comfort_model_4_type": {
                "field_name": "Thermal Comfort Model 4 Type",
                "field_type": "a"
            },
            "thermal_comfort_model_5_type": {
                "field_name": "Thermal Comfort Model 5 Type",
                "field_type": "a"
            },
            "thermal_comfort_model_6_type": {
                "field_name": "Thermal Comfort Model 6 Type",
                "field_type": "a"
            },
            "thermal_comfort_model_7_type": {
                "field_name": "Thermal Comfort Model 7 Type",
                "field_type": "a"
            },
            "ankle_level_air_velocity_schedule_name": {
                "field_name": "Ankle Level Air Velocity Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_or_zonelist_or_space_or_spacelist_name",
            "number_of_people_schedule_name",
            "number_of_people_calculation_method",
            "number_of_people",
            "people_per_floor_area",
            "floor_area_per_person",
            "fraction_radiant",
            "sensible_heat_fraction",
            "activity_level_schedule_name",
            "carbon_dioxide_generation_rate",
            "enable_ashrae_55_comfort_warnings",
            "mean_radiant_temperature_calculation_type",
            "surface_name_angle_factor_list_name",
            "work_efficiency_schedule_name",
            "clothing_insulation_calculation_method",
            "clothing_insulation_calculation_method_schedule_name",
            "clothing_insulation_schedule_name",
            "air_velocity_schedule_name",
            "thermal_comfort_model_1_type",
            "thermal_comfort_model_2_type",
            "thermal_comfort_model_3_type",
            "thermal_comfort_model_4_type",
            "thermal_comfort_model_5_type",
            "thermal_comfort_model_6_type",
            "thermal_comfort_model_7_type",
            "ankle_level_air_velocity_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_or_zonelist_or_space_or_spacelist_name",
                "number_of_people_schedule_name",
                "number_of_people_calculation_method",
                "activity_level_schedule_name",
                "enable_ashrae_55_comfort_warnings",
                "mean_radiant_temperature_calculation_type",
                "surface_name_angle_factor_list_name",
                "work_efficiency_schedule_name",
                "clothing_insulation_calculation_method",
                "clothing_insulation_calculation_method_schedule_name",
                "clothing_insulation_schedule_name",
                "air_velocity_schedule_name",
                "thermal_comfort_model_1_type",
                "thermal_comfort_model_2_type",
                "thermal_comfort_model_3_type",
                "thermal_comfort_model_4_type",
                "thermal_comfort_model_5_type",
                "thermal_comfort_model_6_type",
                "thermal_comfort_model_7_type",
                "ankle_level_air_velocity_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "number_of_people",
                "people_per_floor_area",
                "floor_area_per_person",
                "fraction_radiant",
                "sensible_heat_fraction",
                "carbon_dioxide_generation_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Sets internal gains and contaminant rates for occupants in the zone. If a ZoneList, SpaceList, or a Zone comprised of more than one Space is specified then this definition applies to all applicable spaces, and each instance will be named with the Space Name plus this Object Name.",
    "min_fields": 10.0
}
```
