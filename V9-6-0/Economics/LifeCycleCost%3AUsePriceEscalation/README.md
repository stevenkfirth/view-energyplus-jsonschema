```
{
    "LifeCycleCost:UsePriceEscalation": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "lcc_price_escalation_name": {
                        "type": "string",
                        "note": "The identifier used for the object. The name usually identifies the location (such as the state or region or country or census area) that the escalations apply to. In addition the name should identify the building class such as residential or commercial or industrial and the use type such as electricity or natural gas or water."
                    },
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
                    "escalation_start_year": {
                        "type": "number",
                        "minimum": 1900.0,
                        "maximum": 2100.0,
                        "note": "This field and the Escalation Start Month define the time that corresponds to Year 1 Escalation such as 2010 when the escalation rates are applied. This field and the Escalation Start Month define the time that escalation begins."
                    },
                    "escalation_start_month": {
                        "type": "string",
                        "enum": [
                            "",
                            "April",
                            "August",
                            "December",
                            "February",
                            "January",
                            "July",
                            "June",
                            "March",
                            "May",
                            "November",
                            "October",
                            "September"
                        ],
                        "default": "January",
                        "note": "This field and the Escalation Start Year define the time that corresponds to Year 1 Escalation such as 2010 when the escalation rates are applied. This field and the Escalation Start Year define the time that escalation begins."
                    },
                    "escalations": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "year_escalation": {
                                    "type": "number",
                                    "note": "The escalation in price of the energy or water use for the first year expressed as a decimal."
                                }
                            },
                            "type": "object"
                        }
                    }
                },
                "required": [
                    "lcc_price_escalation_name",
                    "resource"
                ]
            }
        },
        "group": "Economics",
        "legacy_idd": {
            "field_info": {
                "lcc_price_escalation_name": {
                    "field_name": "LCC Price Escalation Name",
                    "field_type": "a"
                },
                "resource": {
                    "field_name": "Resource",
                    "field_type": "a"
                },
                "escalation_start_year": {
                    "field_name": "Escalation Start Year",
                    "field_type": "n"
                },
                "escalation_start_month": {
                    "field_name": "Escalation Start Month",
                    "field_type": "a"
                },
                "year_escalation": {
                    "field_name": "Year Escalation",
                    "field_type": "n"
                }
            },
            "fields": [
                "lcc_price_escalation_name",
                "resource",
                "escalation_start_year",
                "escalation_start_month"
            ],
            "alphas": {
                "fields": [
                    "lcc_price_escalation_name",
                    "resource",
                    "escalation_start_month"
                ]
            },
            "numerics": {
                "fields": [
                    "escalation_start_year"
                ],
                "extensions": [
                    "year_escalation"
                ]
            },
            "extensibles": [
                "year_escalation"
            ],
            "extension": "escalations"
        },
        "type": "object",
        "memo": "Life cycle cost escalation factors. The values for this object may be found in the annual supplement to NIST Handbook 135 in Tables Ca-1 to Ca-5 and are included in an EnergyPlus dataset file.",
        "extensible_size": 1.0
    }
}
```
