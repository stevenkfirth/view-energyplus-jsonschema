```
{
    "Generator:FuelCell:ElectricalStorage": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "choice_of_model": {
                        "type": "string",
                        "enum": [
                            "SimpleEfficiencyWithConstraints"
                        ]
                    },
                    "nominal_charging_energetic_efficiency": {
                        "type": "number",
                        "maximum": 1.0,
                        "minimum": 0.0
                    },
                    "nominal_discharging_energetic_efficiency": {
                        "type": "number",
                        "maximum": 1.0,
                        "minimum": 0.0
                    },
                    "simple_maximum_capacity": {
                        "type": "number",
                        "units": "J"
                    },
                    "simple_maximum_power_draw": {
                        "type": "number",
                        "units": "W"
                    },
                    "simple_maximum_power_store": {
                        "type": "number",
                        "units": "W"
                    },
                    "initial_charge_state": {
                        "type": "number",
                        "units": "J"
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "FCStorageNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "choice_of_model": {
                    "field_name": "Choice of Model",
                    "field_type": "a"
                },
                "nominal_charging_energetic_efficiency": {
                    "field_name": "Nominal Charging Energetic Efficiency",
                    "field_type": "n"
                },
                "nominal_discharging_energetic_efficiency": {
                    "field_name": "Nominal Discharging Energetic Efficiency",
                    "field_type": "n"
                },
                "simple_maximum_capacity": {
                    "field_name": "Simple Maximum Capacity",
                    "field_type": "n"
                },
                "simple_maximum_power_draw": {
                    "field_name": "Simple Maximum Power Draw",
                    "field_type": "n"
                },
                "simple_maximum_power_store": {
                    "field_name": "Simple Maximum Power Store",
                    "field_type": "n"
                },
                "initial_charge_state": {
                    "field_name": "Initial Charge State",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "choice_of_model",
                "nominal_charging_energetic_efficiency",
                "nominal_discharging_energetic_efficiency",
                "simple_maximum_capacity",
                "simple_maximum_power_draw",
                "simple_maximum_power_store",
                "initial_charge_state"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "choice_of_model"
                ]
            },
            "numerics": {
                "fields": [
                    "nominal_charging_energetic_efficiency",
                    "nominal_discharging_energetic_efficiency",
                    "simple_maximum_capacity",
                    "simple_maximum_power_draw",
                    "simple_maximum_power_store",
                    "initial_charge_state"
                ]
            }
        },
        "type": "object",
        "memo": "Used to describe the electrical storage subsystem for a fuel cell power generator. The electrical storage model is a very simple \"constrained bucket\" model. Note that this electrical storage is embedded within the FC device."
    }
}
```
