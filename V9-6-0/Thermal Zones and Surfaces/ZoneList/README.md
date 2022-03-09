```
{
    "ZoneList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zones": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "zone_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "ZoneNames"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "zone_name"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Thermal Zones and Surfaces",
        "name": {
            "type": "string",
            "note": "Name of the Zone List",
            "is_required": true,
            "reference": [
                "ZoneAndZoneListNames",
                "ZoneListNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name"
            ],
            "alphas": {
                "fields": [
                    "name"
                ],
                "extensions": [
                    "zone_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "zone_name"
            ],
            "extension": "zones"
        },
        "type": "object",
        "memo": "Defines a list of thermal zones which can be referenced as a group. The ZoneList name may be used elsewhere in the input to apply a parameter to all zones in the list. ZoneLists can be used effectively with the following objects: People, Lights, ElectricEquipment, GasEquipment, HotWaterEquipment, ZoneInfiltration:DesignFlowRate, ZoneVentilation:DesignFlowRate, Sizing:Zone, ZoneControl:Thermostat, and others.",
        "min_fields": 2.0,
        "extensible_size": 1.0
    }
}
```
