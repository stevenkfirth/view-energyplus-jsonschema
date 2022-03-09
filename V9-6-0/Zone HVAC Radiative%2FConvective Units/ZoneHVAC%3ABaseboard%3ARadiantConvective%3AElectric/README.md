```
{
    "patternProperties": {
        "^.*\\S.*$": {
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
                "heating_design_capacity_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "CapacityPerFloorArea",
                        "FractionOfAutosizedHeatingCapacity",
                        "HeatingDesignCapacity"
                    ],
                    "default": "HeatingDesignCapacity",
                    "note": "Enter the method used to determine the heating design capacity. HeatingDesignCapacity = > selected when the design heating capacity value or autosize is specified. CapacityPerFloorArea = > selected when the design heating capacity is determine from user specified heating capacity per floor area and zone floor area. FractionOfAutosizedHeatingCapacity = > is selected when the design heating capacity is determined from a user specified fraction and the auto-sized design heating capacity."
                },
                "heating_design_capacity": {
                    "units": "W",
                    "ip-units": "W",
                    "default": "Autosize",
                    "note": "Enter the design heating capacity. Required field when the heating design capacity method HeatingDesignCapacity.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autosize"
                            ]
                        }
                    ]
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
                "efficiency": {
                    "type": "number",
                    "maximum": 1.0,
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
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
                },
                "surface_fractions": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "surface_name": {
                                "type": "string",
                                "note": "Radiant energy may be distributed to specific surfaces",
                                "data_type": "object_list",
                                "object_list": [
                                    "AllHeatTranSurfNames"
                                ]
                            },
                            "fraction_of_radiant_energy_to_surface": {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
                            }
                        },
                        "type": "object"
                    }
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
        "reference": [
            "ZoneEquipmentNames"
        ]
    },
    "additionalProperties": false,
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
            "heating_design_capacity_method": {
                "field_name": "Heating Design Capacity Method",
                "field_type": "a"
            },
            "heating_design_capacity": {
                "field_name": "Heating Design Capacity",
                "field_type": "n"
            },
            "heating_design_capacity_per_floor_area": {
                "field_name": "Heating Design Capacity Per Floor Area",
                "field_type": "n"
            },
            "fraction_of_autosized_heating_design_capacity": {
                "field_name": "Fraction of Autosized Heating Design Capacity",
                "field_type": "n"
            },
            "efficiency": {
                "field_name": "Efficiency",
                "field_type": "n"
            },
            "fraction_radiant": {
                "field_name": "Fraction Radiant",
                "field_type": "n"
            },
            "fraction_of_radiant_energy_incident_on_people": {
                "field_name": "Fraction of Radiant Energy Incident on People",
                "field_type": "n"
            },
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "fraction_of_radiant_energy_to_surface": {
                "field_name": "Fraction of Radiant Energy to Surface",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "heating_design_capacity_method",
            "heating_design_capacity",
            "heating_design_capacity_per_floor_area",
            "fraction_of_autosized_heating_design_capacity",
            "efficiency",
            "fraction_radiant",
            "fraction_of_radiant_energy_incident_on_people"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "heating_design_capacity_method"
            ],
            "extensions": [
                "surface_name"
            ]
        },
        "numerics": {
            "fields": [
                "heating_design_capacity",
                "heating_design_capacity_per_floor_area",
                "fraction_of_autosized_heating_design_capacity",
                "efficiency",
                "fraction_radiant",
                "fraction_of_radiant_energy_incident_on_people"
            ],
            "extensions": [
                "fraction_of_radiant_energy_to_surface"
            ]
        },
        "extensibles": [
            "surface_name",
            "fraction_of_radiant_energy_to_surface"
        ],
        "extension": "surface_fractions"
    },
    "type": "object",
    "memo": "The number of surfaces can be expanded beyond 100, if necessary, by adding more groups to the end of the list",
    "min_fields": 8.0,
    "extensible_size": 2.0
}
```
