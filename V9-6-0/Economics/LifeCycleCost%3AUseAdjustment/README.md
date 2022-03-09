```
{
    "LifeCycleCost:UseAdjustment": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "resource": {
                        "type": "string",
                        "enum": [
                            "Coal",
                            "Diesel",
                            "Electricity",
                            "ElectricityNet",
                            "ElectricityProduced",
                            "ElectricityPurchased",
                            "ElectricitySurplusSold",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane",
                            "Steam",
                            "Water"
                        ]
                    },
                    "multipliers": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "year_multiplier": {
                                    "type": "number",
                                    "note": "The multiplier to be applied to the end-use cost for the first year in the service period. The total utility costs for the selected end-use is multiplied by this value. For no change enter 1.0."
                                }
                            },
                            "type": "object"
                        }
                    }
                },
                "required": [
                    "resource"
                ]
            }
        },
        "group": "Economics",
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
                "resource": {
                    "field_name": "Resource",
                    "field_type": "a"
                },
                "year_multiplier": {
                    "field_name": "Year Multiplier",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "resource"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "resource"
                ]
            },
            "numerics": {
                "fields": [],
                "extensions": [
                    "year_multiplier"
                ]
            },
            "extensibles": [
                "year_multiplier"
            ],
            "extension": "multipliers"
        },
        "type": "object",
        "memo": "Used by advanced users to adjust the energy or water use costs for future years. This should not be used for compensating for inflation but should only be used to increase the costs of energy or water based on assumed changes to the actual usage, such as anticipated changes in the future function of the building. The adjustments begin at the start of the service period.",
        "extensible_size": 1.0
    }
}
```
