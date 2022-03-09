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
                    "note": "units in schedule should be fraction applied to design level of electric equipment, generally (0.0 - 1.0)"
                },
                "design_level_calculation_method": {
                    "type": "string",
                    "note": "The entered calculation method is used to create the maximum amount of electric equipment for this set of attributes Choices: EquipmentLevel => Equipment Level -- simply enter watts of equipment Watts/Area => Watts per Zone Floor Area -- enter the number to apply. Value * Floor Area = Equipment Level Watts/Person => Watts per Person -- enter the number to apply. Value * Occupants = Equipment Level",
                    "enum": [
                        "",
                        "EquipmentLevel",
                        "Watts/Area",
                        "Watts/Person"
                    ],
                    "default": "EquipmentLevel"
                },
                "design_level": {
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
                "fraction_latent": {
                    "type": "number",
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
                "fraction_lost": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
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
            "ElectricEquipmentNames"
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
            "design_level": {
                "field_name": "Design Level",
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
            "fraction_latent": {
                "field_name": "Fraction Latent",
                "field_type": "n"
            },
            "fraction_radiant": {
                "field_name": "Fraction Radiant",
                "field_type": "n"
            },
            "fraction_lost": {
                "field_name": "Fraction Lost",
                "field_type": "n"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_or_zonelist_or_space_or_spacelist_name",
            "schedule_name",
            "design_level_calculation_method",
            "design_level",
            "watts_per_zone_floor_area",
            "watts_per_person",
            "fraction_latent",
            "fraction_radiant",
            "fraction_lost",
            "end_use_subcategory"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_or_zonelist_or_space_or_spacelist_name",
                "schedule_name",
                "design_level_calculation_method",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "design_level",
                "watts_per_zone_floor_area",
                "watts_per_person",
                "fraction_latent",
                "fraction_radiant",
                "fraction_lost"
            ]
        }
    },
    "type": "object",
    "memo": "Sets internal gains for electric equipment in the zone. If a ZoneList, SpaceList, or a Zone comprised of more than one Space is specified then this definition applies to all applicable spaces, and each instance will be named with the Space Name plus this Object Name.",
    "min_fields": 10.0
}
```
