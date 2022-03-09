```
{
    "ZoneHVAC:HighTemperatureRadiant": {
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
                    "zone_name": {
                        "type": "string",
                        "note": "Name of zone system is serving",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
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
                        "note": "Enter the method used to determine the maximum heating power input capacity. HeatingDesignCapacity = > selected when the design heating capacity value or autosize is specified. CapacityPerFloorArea = > selected when the design heating capacity is determine from user specified heating capacity per floor area and zone floor area. FractionOfAutosizedHeatingCapacity = > is selected when the design heating capacity is determined from a user specified fraction and the auto-sized design heating capacity."
                    },
                    "heating_design_capacity": {
                        "units": "W",
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
                    "fuel_type": {
                        "type": "string",
                        "note": "Natural gas or electricity",
                        "enum": [
                            "Electricity",
                            "NaturalGas"
                        ]
                    },
                    "combustion_efficiency": {
                        "type": "number",
                        "note": "Not used for non-gas radiant heaters",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "fraction_of_input_converted_to_radiant_energy": {
                        "type": "number",
                        "note": "Radiant+latent+lost fractions must sum to 1 or less, remainder is considered convective heat",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.7
                    },
                    "fraction_of_input_converted_to_latent_energy": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "fraction_of_input_that_is_lost": {
                        "type": "number",
                        "note": "Fraction of input vented to outdoor environment",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "temperature_control_type": {
                        "type": "string",
                        "note": "Temperature type used to control unit",
                        "enum": [
                            "",
                            "MeanAirTemperature",
                            "MeanAirTemperatureSetpoint",
                            "MeanRadiantTemperature",
                            "MeanRadiantTemperatureSetpoint",
                            "OperativeTemperature",
                            "OperativeTemperatureSetpoint"
                        ],
                        "default": "OperativeTemperature"
                    },
                    "heating_throttling_range": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 2.0
                    },
                    "heating_setpoint_temperature_schedule_name": {
                        "type": "string",
                        "note": "This setpoint is an \"operative temperature\" setpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "fraction_of_radiant_energy_incident_on_people": {
                        "type": "number",
                        "note": "This will affect thermal comfort but from an energy balance standpoint this value gets added to the convective gains from the radiant heater",
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
                    "zone_name",
                    "fuel_type"
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
                "zone_name": {
                    "field_name": "Zone Name",
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
                "fuel_type": {
                    "field_name": "Fuel Type",
                    "field_type": "a"
                },
                "combustion_efficiency": {
                    "field_name": "Combustion Efficiency",
                    "field_type": "n"
                },
                "fraction_of_input_converted_to_radiant_energy": {
                    "field_name": "Fraction of Input Converted to Radiant Energy",
                    "field_type": "n"
                },
                "fraction_of_input_converted_to_latent_energy": {
                    "field_name": "Fraction of Input Converted to Latent Energy",
                    "field_type": "n"
                },
                "fraction_of_input_that_is_lost": {
                    "field_name": "Fraction of Input that Is Lost",
                    "field_type": "n"
                },
                "temperature_control_type": {
                    "field_name": "Temperature Control Type",
                    "field_type": "a"
                },
                "heating_throttling_range": {
                    "field_name": "Heating Throttling Range",
                    "field_type": "n"
                },
                "heating_setpoint_temperature_schedule_name": {
                    "field_name": "Heating Setpoint Temperature Schedule Name",
                    "field_type": "a"
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
                "zone_name",
                "heating_design_capacity_method",
                "heating_design_capacity",
                "heating_design_capacity_per_floor_area",
                "fraction_of_autosized_heating_design_capacity",
                "fuel_type",
                "combustion_efficiency",
                "fraction_of_input_converted_to_radiant_energy",
                "fraction_of_input_converted_to_latent_energy",
                "fraction_of_input_that_is_lost",
                "temperature_control_type",
                "heating_throttling_range",
                "heating_setpoint_temperature_schedule_name",
                "fraction_of_radiant_energy_incident_on_people"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "zone_name",
                    "heating_design_capacity_method",
                    "fuel_type",
                    "temperature_control_type",
                    "heating_setpoint_temperature_schedule_name"
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
                    "combustion_efficiency",
                    "fraction_of_input_converted_to_radiant_energy",
                    "fraction_of_input_converted_to_latent_energy",
                    "fraction_of_input_that_is_lost",
                    "heating_throttling_range",
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
        "min_fields": 14.0,
        "extensible_size": 2.0
    }
}
```
