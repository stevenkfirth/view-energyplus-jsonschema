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
                    "note": "units in Schedule should be fraction applied to design level of gas equipment, generally (0.0 - 1.0)"
                },
                "design_level_calculation_method": {
                    "type": "string",
                    "note": "The entered calculation method is used to create the maximum amount of gas equipment for this set of attributes Choices: EquipmentLevel => Design Level -- simply enter power input of equipment Watts/Area or Power/Area => Power per Zone Floor Area -- enter the number to apply. Value * Floor Area = Equipment Level Watts/Person or Power/Person => Power per Person -- enter the number to apply. Value * Occupants = Equipment Level",
                    "enum": [
                        "",
                        "EquipmentLevel",
                        "Power/Area",
                        "Power/Person",
                        "Watts/Area",
                        "Watts/Person"
                    ],
                    "default": "EquipmentLevel"
                },
                "design_level": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "ip-units": "Btu/h"
                },
                "power_per_zone_floor_area": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "W/m2",
                    "ip-units": "Btu/h-ft2"
                },
                "power_per_person": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "W/person",
                    "ip-units": "Btu/h-person"
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
                "carbon_dioxide_generation_rate": {
                    "type": "number",
                    "note": "CO2 generation rate per unit of power input The default value assumes the equipment is fully vented. For unvented equipment, a suggested value is 3.45E-8 m3/s-W. This value is converted from a natural gas CO2 emission rate of 117 lbs CO2 per million Btu. The maximum value assumes to be 10 times of the recommended value.",
                    "units": "m3/s-W",
                    "ip-units": "(ft3/min)/(Btu/h)",
                    "default": 0.0,
                    "minimum": 0.0,
                    "maximum": 4e-07
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
        "is_required": true
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
            "power_per_zone_floor_area": {
                "field_name": "Power per Zone Floor Area",
                "field_type": "n"
            },
            "power_per_person": {
                "field_name": "Power per Person",
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
            "carbon_dioxide_generation_rate": {
                "field_name": "Carbon Dioxide Generation Rate",
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
            "power_per_zone_floor_area",
            "power_per_person",
            "fraction_latent",
            "fraction_radiant",
            "fraction_lost",
            "carbon_dioxide_generation_rate",
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
                "power_per_zone_floor_area",
                "power_per_person",
                "fraction_latent",
                "fraction_radiant",
                "fraction_lost",
                "carbon_dioxide_generation_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Sets internal gains and contaminant rates for gas equipment in the zone. If a ZoneList, SpaceList, or a Zone comprised of more than one Space is specified then this definition applies to all applicable spaces, and each instance will be named with the Space Name plus this Object Name.",
    "min_fields": 10.0
}
```
