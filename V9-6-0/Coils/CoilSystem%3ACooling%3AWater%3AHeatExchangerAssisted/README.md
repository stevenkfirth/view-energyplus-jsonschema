```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "heat_exchanger_object_type": {
                    "type": "string",
                    "enum": [
                        "HeatExchanger:AirToAir:FlatPlate",
                        "HeatExchanger:AirToAir:SensibleAndLatent"
                    ]
                },
                "heat_exchanger_name": {
                    "type": "string"
                },
                "cooling_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:Water",
                        "Coil:Cooling:Water:DetailedGeometry"
                    ]
                },
                "cooling_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsWaterNoHX"
                    ]
                }
            },
            "required": [
                "heat_exchanger_object_type",
                "heat_exchanger_name",
                "cooling_coil_object_type",
                "cooling_coil_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "CoolingCoilsWater",
            "validBranchEquipmentNames",
            "validOASysEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validOASysEquipmentTypes"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "heat_exchanger_object_type": {
                "field_name": "Heat Exchanger Object Type",
                "field_type": "a"
            },
            "heat_exchanger_name": {
                "field_name": "Heat Exchanger Name",
                "field_type": "a"
            },
            "cooling_coil_object_type": {
                "field_name": "Cooling Coil Object Type",
                "field_type": "a"
            },
            "cooling_coil_name": {
                "field_name": "Cooling Coil Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "heat_exchanger_object_type",
            "heat_exchanger_name",
            "cooling_coil_object_type",
            "cooling_coil_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "heat_exchanger_object_type",
                "heat_exchanger_name",
                "cooling_coil_object_type",
                "cooling_coil_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Virtual component consisting of a chilled-water cooling coil and an air-to-air heat exchanger. The air-to-air heat exchanger precools the air entering the cooling coil and reuses this energy to reheat the supply air leaving the cooling coil. This heat exchange process improves the latent removal performance of the cooling coil (lower sensible heat ratio).",
    "min_fields": 5.0
}
```
