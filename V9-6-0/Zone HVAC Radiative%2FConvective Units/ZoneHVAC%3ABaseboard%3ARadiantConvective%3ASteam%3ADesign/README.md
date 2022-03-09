```
{
    "ZoneHVAC:Baseboard:RadiantConvective:Steam:Design": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "heating_design_capacity_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "CapacityPerFloorArea",
                            "FractionOfAutosizedHeatingCapacity",
                            "HeatingDesignCapacity"
                        ],
                        "default": "HeatingDesignCapacity",
                        "note": "Enter the method used to determine the heating design capacity. HeatingDesignCapacity is selected when the design heating capacity value or autosize is specified. CapacityPerFloorArea is selected when the design heating capacity is determine from user specified heating capacity per floor area and zone floor area. FractionOfAutosizedHeatingCapacity is selected when the design heating capacity is determined from a user specified fraction and the auto-sized design heating capacity."
                    },
                    "heating_design_capacity_per_floor_area": {
                        "type": "number",
                        "units": "W/m2",
                        "minimum": 0.0,
                        "note": "Enter the heating design capacity per zone floor area. Required field when the heating design capacity method field is CapacityPerFloorArea."
                    },
                    "fraction_of_autosized_heating_design_capacity": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 1.0,
                        "note": "Enter the fraction of autosized heating design capacity. Required field when capacity the heating design capacity method field is FractionOfAutosizedHeatingCapacity."
                    },
                    "convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001
                    },
                    "fraction_radiant": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "fraction_of_radiant_energy_incident_on_people": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    }
                },
                "required": [
                    "fraction_radiant"
                ]
            }
        },
        "group": "Zone HVAC Radiative/Convective Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ],
            "reference": [
                "ZoneEquipmentNames",
                "validBranchEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "heating_design_capacity_method": {
                    "field_name": "Heating Design Capacity Method",
                    "field_type": "a"
                },
                "heating_design_capacity_per_floor_area": {
                    "field_name": "Heating Design Capacity Per Floor Area",
                    "field_type": "n"
                },
                "fraction_of_autosized_heating_design_capacity": {
                    "field_name": "Fraction of Autosized Heating Design Capacity",
                    "field_type": "n"
                },
                "convergence_tolerance": {
                    "field_name": "Convergence Tolerance",
                    "field_type": "n"
                },
                "fraction_radiant": {
                    "field_name": "Fraction Radiant",
                    "field_type": "n"
                },
                "fraction_of_radiant_energy_incident_on_people": {
                    "field_name": "Fraction of Radiant Energy Incident on People",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "heating_design_capacity_method",
                "heating_design_capacity_per_floor_area",
                "fraction_of_autosized_heating_design_capacity",
                "convergence_tolerance",
                "fraction_radiant",
                "fraction_of_radiant_energy_incident_on_people"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "heating_design_capacity_method"
                ]
            },
            "numerics": {
                "fields": [
                    "heating_design_capacity_per_floor_area",
                    "fraction_of_autosized_heating_design_capacity",
                    "convergence_tolerance",
                    "fraction_radiant",
                    "fraction_of_radiant_energy_incident_on_people"
                ]
            }
        },
        "type": "object",
        "min_fields": 7.0
    }
}
```
