```
{
    "ZoneAirMassFlowConservation": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "adjust_zone_mixing_and_return_for_air_mass_flow_balance": {
                        "type": "string",
                        "note": "If \"AdjustMixingOnly\", zone mixing object flow rates are adjusted to balance the zone air mass flow and zone infiltration air flow may be increased or decreased if required in order to balance the zone air mass flow. If \"AdjustReturnOnly\", zone total return flow rate is adjusted to balance the zone air mass flow and zone infiltration air flow may be increased or decreased if required in order to balance the zone air mass flow. If \"AdjustMixingThenReturn\", first the zone mixing objects flow rates are adjusted to balance the zone air flow, second zone total return flow rate is adjusted and zone infiltration air flow may be increased or decreased if required in order to balance the zone air mass flow. If \"AdjustReturnThenMixing\", first zone total return flow rate is adjusted to balance the zone air flow, second the zone mixing object flow rates are adjusted and infiltration air flow may be increased or decreased if required in order to balance the zone air mass flow.",
                        "enum": [
                            "",
                            "AdjustMixingOnly",
                            "AdjustMixingThenReturn",
                            "AdjustReturnOnly",
                            "AdjustReturnThenMixing",
                            "None"
                        ],
                        "default": "None"
                    },
                    "infiltration_balancing_method": {
                        "type": "string",
                        "note": "This input field allows user to choose how zone infiltration flow is treated during the zone air mass flow balance calculation. AddInfiltrationFlow may add infiltration to the base flow specified in the infiltration object to balance the zone air mass flow. The additional infiltration air mass flow is not self-balanced. The base flow is assumed to be self-balanced. AdjustInfiltrationFlow may adjust the base flow calculated using the base flow specified in the infiltration object to balance the zone air mass flow. If it If no adjustment is required, then the base infiltration is assumed to be self-balanced. None will make no changes to the base infiltration flow.",
                        "enum": [
                            "",
                            "AddInfiltrationFlow",
                            "AdjustInfiltrationFlow",
                            "None"
                        ],
                        "default": "AddInfiltrationFlow"
                    },
                    "infiltration_balancing_zones": {
                        "type": "string",
                        "note": "This input field allows user to choose which zones are included in infiltration balancing. MixingSourceZonesOnly allows infiltration balancing only in zones which as source zones for mixing which also have an infiltration object defined. AllZones allows infiltration balancing in any zone which has an infiltration object defined.",
                        "enum": [
                            "",
                            "AllZones",
                            "MixingSourceZonesOnly"
                        ],
                        "default": "MixingSourceZonesOnly"
                    }
                }
            }
        },
        "group": "Simulation Parameters",
        "legacy_idd": {
            "field_info": {
                "adjust_zone_mixing_and_return_for_air_mass_flow_balance": {
                    "field_name": "Adjust Zone Mixing and Return For Air Mass Flow Balance",
                    "field_type": "a"
                },
                "infiltration_balancing_method": {
                    "field_name": "Infiltration Balancing Method",
                    "field_type": "a"
                },
                "infiltration_balancing_zones": {
                    "field_name": "Infiltration Balancing Zones",
                    "field_type": "a"
                }
            },
            "fields": [
                "adjust_zone_mixing_and_return_for_air_mass_flow_balance",
                "infiltration_balancing_method",
                "infiltration_balancing_zones"
            ],
            "alphas": {
                "fields": [
                    "adjust_zone_mixing_and_return_for_air_mass_flow_balance",
                    "infiltration_balancing_method",
                    "infiltration_balancing_zones"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Enforces the zone air mass flow balance by either adjusting zone mixing object flow only, adjusting zone total return flow only, zone mixing and the zone total return flows, or adjusting the zone total return and zone mixing object flows. Zone infiltration flow air flow is increased or decreased depending user selection in the infiltration treatment method. If either of zone mixing or zone return flow adjusting methods or infiltration is active, then the zone air mass flow balance calculation will attempt to enforce conservation of mass for each zone. If flow balancing method is \"None\" and infiltration is \"None\", then the zone air mass flow calculation defaults to assume self-balanced simple flow mixing and infiltration objects.",
        "min_fields": 3.0
    }
}
```
