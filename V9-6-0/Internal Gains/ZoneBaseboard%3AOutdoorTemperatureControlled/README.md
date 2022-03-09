```
{
    "ZoneBaseboard:OutdoorTemperatureControlled": {
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
                        "note": "units in Schedule should be fraction applied to capacity of the baseboard heat equipment, generally (0.0 - 1.0)"
                    },
                    "capacity_at_low_temperature": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0
                    },
                    "low_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "capacity_at_high_temperature": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "high_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "fraction_radiant": {
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
                    "schedule_name",
                    "capacity_at_low_temperature",
                    "low_temperature",
                    "capacity_at_high_temperature",
                    "high_temperature"
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
                "capacity_at_low_temperature": {
                    "field_name": "Capacity at Low Temperature",
                    "field_type": "n"
                },
                "low_temperature": {
                    "field_name": "Low Temperature",
                    "field_type": "n"
                },
                "capacity_at_high_temperature": {
                    "field_name": "Capacity at High Temperature",
                    "field_type": "n"
                },
                "high_temperature": {
                    "field_name": "High Temperature",
                    "field_type": "n"
                },
                "fraction_radiant": {
                    "field_name": "Fraction Radiant",
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
                "capacity_at_low_temperature",
                "low_temperature",
                "capacity_at_high_temperature",
                "high_temperature",
                "fraction_radiant",
                "end_use_subcategory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_or_zonelist_or_space_or_spacelist_name",
                    "schedule_name",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "capacity_at_low_temperature",
                    "low_temperature",
                    "capacity_at_high_temperature",
                    "high_temperature",
                    "fraction_radiant"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies outside temperature-controlled electric baseboard heating. If a ZoneList, SpaceList, or a Zone comprised of more than one Space is specified then this definition applies to all applicable spaces, and each instance will be named with the Space Name plus this Object Name.",
        "min_fields": 8.0
    }
}
```
