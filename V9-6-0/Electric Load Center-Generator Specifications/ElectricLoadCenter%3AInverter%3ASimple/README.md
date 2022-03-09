```
{
    "patternProperties": {
        ".*": {
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
                "zone_name": {
                    "type": "string",
                    "note": "enter name of zone to receive inverter losses as heat if blank then inverter is assumed to be outdoors",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "radiative_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "inverter_efficiency": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                }
            }
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "reference": [
            "InverterList"
        ]
    },
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "radiative_fraction": {
                "field_name": "Radiative Fraction",
                "field_type": "n"
            },
            "inverter_efficiency": {
                "field_name": "Inverter Efficiency",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "zone_name",
            "radiative_fraction",
            "inverter_efficiency"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name"
            ]
        },
        "numerics": {
            "fields": [
                "radiative_fraction",
                "inverter_efficiency"
            ]
        }
    },
    "type": "object",
    "memo": "Electric power inverter to convert from direct current (DC) to alternating current (AC) in an electric load center that contains photovoltaic modules. This input object is for the simplest inverter model and uses a fixed efficiency."
}
```
