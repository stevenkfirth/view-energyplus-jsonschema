```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "fraction_of_convective_internal_loads_added_to_floor_air": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "fraction_of_infiltration_internal_loads_added_to_floor_air": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                }
            },
            "required": [
                "zone_name"
            ]
        }
    },
    "group": "Room Air Models",
    "legacy_idd": {
        "field_info": {
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "fraction_of_convective_internal_loads_added_to_floor_air": {
                "field_name": "Fraction of Convective Internal Loads Added to Floor Air",
                "field_type": "n"
            },
            "fraction_of_infiltration_internal_loads_added_to_floor_air": {
                "field_name": "Fraction of Infiltration Internal Loads Added to Floor Air",
                "field_type": "n"
            }
        },
        "fields": [
            "zone_name",
            "fraction_of_convective_internal_loads_added_to_floor_air",
            "fraction_of_infiltration_internal_loads_added_to_floor_air"
        ],
        "alphas": {
            "fields": [
                "zone_name"
            ]
        },
        "numerics": {
            "fields": [
                "fraction_of_convective_internal_loads_added_to_floor_air",
                "fraction_of_infiltration_internal_loads_added_to_floor_air"
            ]
        }
    },
    "type": "object",
    "memo": "The Mundt model for displacement ventilation"
}
```
