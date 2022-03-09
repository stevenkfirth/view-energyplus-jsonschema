```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "room_air_modeling_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AirflowNetwork",
                        "CrossVentilation",
                        "Mixing",
                        "OneNodeDisplacementVentilation",
                        "ThreeNodeDisplacementVentilation",
                        "UnderFloorAirDistributionExterior",
                        "UnderFloorAirDistributionInterior",
                        "UserDefined"
                    ],
                    "default": "Mixing",
                    "note": "Mixing = Complete mixing air model UserDefined = UserDefined Room Air Temperature Patterns needs RoomAir:TemperaturePattern:UserDefined object referencing this Zone OneNodeDisplacementVentilation = Mundt roomair model for displacement ventilation with single floor air node needs RoomAirSettings:OneNodeDisplacementVentilation object referencing this Zone ThreeNodeDisplacementVentilation = RoomAir modeling using UCSD three-node displacement ventilation model needs RoomAirSettings:ThreeNodeDisplacementVentilation object referencing this Zone CrossVentilation = RoomAir modeling using UCSD two-zone cross ventilation model needs RoomAirSettings:CrossVentilation object referencing this Zone UnderFloorAirDistributionInterior = 2-Node UFAD model for interior zones needs RoomAirSettings:UnderFloorAirDistributionInterior object referencing this Zone UnderFloorAirDistributionExterior = RoomAir modeling using 2-Node UFAD model for exterior zones needs RoomAirSettings:UnderFloorAirDistributionExterior object referencing this Zone AirflowNetwork = RoomAir modeling using AirflowNetwork needs RoomAirSettings:AirflowNetwork object referencing this Zone"
                },
                "air_temperature_coupling_strategy": {
                    "type": "string",
                    "enum": [
                        "",
                        "Direct",
                        "Indirect"
                    ],
                    "default": "Direct"
                }
            },
            "required": [
                "zone_name"
            ]
        }
    },
    "group": "Room Air Models",
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "room_air_modeling_type": {
                "field_name": "Room-Air Modeling Type",
                "field_type": "a"
            },
            "air_temperature_coupling_strategy": {
                "field_name": "Air Temperature Coupling Strategy",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_name",
            "room_air_modeling_type",
            "air_temperature_coupling_strategy"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_name",
                "room_air_modeling_type",
                "air_temperature_coupling_strategy"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Selects the type of room air model to be used in a given zone. If no RoomAirModelType object is specified then the default Mixing model (all zone air at the same temperature) will be used.",
    "min_fields": 4.0
}
```
