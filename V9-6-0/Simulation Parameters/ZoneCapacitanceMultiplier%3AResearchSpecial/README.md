```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_or_zonelist_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneAndZoneListNames"
                    ],
                    "note": "If this field is left blank, the multipliers are applied to all the zones not specified"
                },
                "temperature_capacity_multiplier": {
                    "type": "number",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "note": "Used to alter the capacitance of zone air with respect to heat or temperature"
                },
                "humidity_capacity_multiplier": {
                    "type": "number",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "note": "Used to alter the capacitance of zone air with respect to moisture or humidity ratio"
                },
                "carbon_dioxide_capacity_multiplier": {
                    "type": "number",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "note": "Used to alter the capacitance of zone air with respect to zone air carbon dioxide concentration"
                },
                "generic_contaminant_capacity_multiplier": {
                    "type": "number",
                    "default": 1.0,
                    "exclusiveMinimum": 0.0,
                    "note": "Used to alter the capacitance of zone air with respect to zone air generic contaminant concentration"
                }
            }
        }
    },
    "group": "Simulation Parameters",
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
            "zone_or_zonelist_name": {
                "field_name": "Zone or ZoneList Name",
                "field_type": "a"
            },
            "temperature_capacity_multiplier": {
                "field_name": "Temperature Capacity Multiplier",
                "field_type": "n"
            },
            "humidity_capacity_multiplier": {
                "field_name": "Humidity Capacity Multiplier",
                "field_type": "n"
            },
            "carbon_dioxide_capacity_multiplier": {
                "field_name": "Carbon Dioxide Capacity Multiplier",
                "field_type": "n"
            },
            "generic_contaminant_capacity_multiplier": {
                "field_name": "Generic Contaminant Capacity Multiplier",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "zone_or_zonelist_name",
            "temperature_capacity_multiplier",
            "humidity_capacity_multiplier",
            "carbon_dioxide_capacity_multiplier",
            "generic_contaminant_capacity_multiplier"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_or_zonelist_name"
            ]
        },
        "numerics": {
            "fields": [
                "temperature_capacity_multiplier",
                "humidity_capacity_multiplier",
                "carbon_dioxide_capacity_multiplier",
                "generic_contaminant_capacity_multiplier"
            ]
        }
    },
    "type": "object",
    "memo": "Multiplier altering the relative capacitance of the air compared to an empty zone",
    "min_fields": 6.0,
    "format": "singleLine"
}
```
