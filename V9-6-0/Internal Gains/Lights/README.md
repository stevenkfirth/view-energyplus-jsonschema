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
                "schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "units in schedule should be fraction applied to design level of lights, generally (0.0 - 1.0)"
                },
                "design_level_calculation_method": {
                    "type": "string",
                    "note": "The entered calculation method is used to create the maximum amount of lights for this set of attributes Choices: LightingLevel => Lighting Level -- simply enter watts of lights Watts/Area => Watts per Zone Floor Area -- enter the number to apply. Value * Floor Area = Lights Watts/Person => Watts per Person -- enter the number to apply. Value * Occupants = Lights",
                    "enum": [
                        "",
                        "LightingLevel",
                        "Watts/Area",
                        "Watts/Person"
                    ],
                    "default": "LightingLevel"
                },
                "lighting_level": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "ip-units": "W"
                },
                "watts_per_zone_floor_area": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "W/m2",
                    "ip-units": "W/ft2"
                },
                "watts_per_person": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "W/person",
                    "ip-units": "W/person"
                },
                "return_air_fraction": {
                    "type": "number",
                    "note": "Used only for sizing calculation if return-air-fraction coefficients are specified.",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "fraction_radiant": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "fraction_visible": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "fraction_replaceable": {
                    "type": "number",
                    "note": "For Daylighting:Controls must be 0 or 1:  0 = no dimming control, 1 = full dimming control",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                },
                "return_air_fraction_calculated_from_plenum_temperature": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "return_air_fraction_function_of_plenum_temperature_coefficient_1": {
                    "type": "number",
                    "note": "Used only if Return Air Fraction Is Calculated from Plenum Temperature = Yes Equation is Return Air Fraction = Coefficient#1 - Coefficient#2 X PlenumTemp(degC)",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "return_air_fraction_function_of_plenum_temperature_coefficient_2": {
                    "type": "number",
                    "note": "Used only if Return Air Fraction Is Calculated from Plenum Temperature = Yes Equation is Return Air Fraction = Coefficient#1 - Coefficient#2 X PlenumTemp(degC)",
                    "units": "1/K",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "return_air_heat_gain_node_name": {
                    "type": "string",
                    "note": "Name of the return air node for this heat gain. If left blank, defaults to the first return air node for the zone. Leave this field blank when using a ZoneList name."
                },
                "exhaust_air_heat_gain_node_name": {
                    "type": "string",
                    "note": "Name of the exhaust air node for this heat gain. If the node name is entered, return heat gain will be shared by both return and exhaust air nodes. The air properties of both nodes are weighted by both node mass flow rates."
                }
            },
            "required": [
                "zone_or_zonelist_or_space_or_spacelist_name",
                "schedule_name"
            ]
        }
    },
    "group": "Internal Gains",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "LightsNames"
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
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "design_level_calculation_method": {
                "field_name": "Design Level Calculation Method",
                "field_type": "a"
            },
            "lighting_level": {
                "field_name": "Lighting Level",
                "field_type": "n"
            },
            "watts_per_zone_floor_area": {
                "field_name": "Watts per Zone Floor Area",
                "field_type": "n"
            },
            "watts_per_person": {
                "field_name": "Watts per Person",
                "field_type": "n"
            },
            "return_air_fraction": {
                "field_name": "Return Air Fraction",
                "field_type": "n"
            },
            "fraction_radiant": {
                "field_name": "Fraction Radiant",
                "field_type": "n"
            },
            "fraction_visible": {
                "field_name": "Fraction Visible",
                "field_type": "n"
            },
            "fraction_replaceable": {
                "field_name": "Fraction Replaceable",
                "field_type": "n"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            },
            "return_air_fraction_calculated_from_plenum_temperature": {
                "field_name": "Return Air Fraction Calculated from Plenum Temperature",
                "field_type": "a"
            },
            "return_air_fraction_function_of_plenum_temperature_coefficient_1": {
                "field_name": "Return Air Fraction Function of Plenum Temperature Coefficient 1",
                "field_type": "n"
            },
            "return_air_fraction_function_of_plenum_temperature_coefficient_2": {
                "field_name": "Return Air Fraction Function of Plenum Temperature Coefficient 2",
                "field_type": "n"
            },
            "return_air_heat_gain_node_name": {
                "field_name": "Return Air Heat Gain Node Name",
                "field_type": "a"
            },
            "exhaust_air_heat_gain_node_name": {
                "field_name": "Exhaust Air Heat Gain Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_or_zonelist_or_space_or_spacelist_name",
            "schedule_name",
            "design_level_calculation_method",
            "lighting_level",
            "watts_per_zone_floor_area",
            "watts_per_person",
            "return_air_fraction",
            "fraction_radiant",
            "fraction_visible",
            "fraction_replaceable",
            "end_use_subcategory",
            "return_air_fraction_calculated_from_plenum_temperature",
            "return_air_fraction_function_of_plenum_temperature_coefficient_1",
            "return_air_fraction_function_of_plenum_temperature_coefficient_2",
            "return_air_heat_gain_node_name",
            "exhaust_air_heat_gain_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_or_zonelist_or_space_or_spacelist_name",
                "schedule_name",
                "design_level_calculation_method",
                "end_use_subcategory",
                "return_air_fraction_calculated_from_plenum_temperature",
                "return_air_heat_gain_node_name",
                "exhaust_air_heat_gain_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "lighting_level",
                "watts_per_zone_floor_area",
                "watts_per_person",
                "return_air_fraction",
                "fraction_radiant",
                "fraction_visible",
                "fraction_replaceable",
                "return_air_fraction_function_of_plenum_temperature_coefficient_1",
                "return_air_fraction_function_of_plenum_temperature_coefficient_2"
            ]
        }
    },
    "type": "object",
    "memo": "Sets internal gains for lights in the zone. If a ZoneList, SpaceList, or a Zone comprised of more than one Space is specified then this definition applies to all applicable spaces, and each instance will be named with the Space Name plus this Object Name.",
    "min_fields": 11.0
}
```
