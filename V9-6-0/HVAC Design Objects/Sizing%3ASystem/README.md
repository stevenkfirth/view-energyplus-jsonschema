```
{
    "Sizing:System": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "airloop_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirPrimaryLoops"
                        ]
                    },
                    "type_of_load_to_size_on": {
                        "type": "string",
                        "note": "Specifies the basis for sizing the system supply air flow rate Sensible and Total use the zone design air flow rates to size the system supply air flow rate The cooling coil will then be sized at either the peak Sensible or Total flow rate and conditions The heating coil is always sized at the peak sensible heating load. VentilationRequirement uses the system ventilation requirement",
                        "enum": [
                            "",
                            "Sensible",
                            "Total",
                            "VentilationRequirement"
                        ],
                        "default": "Sensible"
                    },
                    "design_outdoor_air_flow_rate": {
                        "default": "Autosize",
                        "units": "m3/s",
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
                    "central_heating_maximum_system_air_flow_ratio": {
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
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
                    "preheat_design_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "preheat_design_humidity_ratio": {
                        "type": "number",
                        "units": "kgWater/kgDryAir"
                    },
                    "precool_design_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "precool_design_humidity_ratio": {
                        "type": "number",
                        "units": "kgWater/kgDryAir"
                    },
                    "central_cooling_design_supply_air_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "central_heating_design_supply_air_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "type_of_zone_sum_to_use": {
                        "type": "string",
                        "enum": [
                            "",
                            "Coincident",
                            "NonCoincident"
                        ],
                        "default": "NonCoincident"
                    },
                    "100_outdoor_air_in_cooling": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "100_outdoor_air_in_heating": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "central_cooling_design_supply_air_humidity_ratio": {
                        "type": "number",
                        "default": 0.008,
                        "units": "kgWater/kgDryAir"
                    },
                    "central_heating_design_supply_air_humidity_ratio": {
                        "type": "number",
                        "default": 0.008,
                        "units": "kgWater/kgDryAir"
                    },
                    "cooling_supply_air_flow_rate_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "DesignDay",
                            "Flow/System",
                            "FlowPerCoolingCapacity",
                            "FlowPerFloorArea",
                            "FractionOfAutosizedCoolingAirflow"
                        ],
                        "default": "DesignDay"
                    },
                    "cooling_supply_air_flow_rate": {
                        "type": "number",
                        "note": "This input is used if Cooling Supply Air Flow Rate Method is Flow/System This value will *not* be multiplied by any sizing factor or by zone multipliers. If using zone multipliers, this value must be large enough to serve the multiplied zones.",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "cooling_supply_air_flow_rate_per_floor_area": {
                        "type": "number",
                        "units": "m3/s-m2",
                        "minimum": 0.0,
                        "note": "Enter the cooling supply air volume flow rate per total conditioned floor area. Required field when Cooling Supply Air Flow Rate Method is FlowPerFloorArea."
                    },
                    "cooling_fraction_of_autosized_cooling_supply_air_flow_rate": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the cooling supply air flow rate. Required field when Cooling Supply Air Flow Rate Method is FractionOfAutosizedCoolingAirflow."
                    },
                    "cooling_supply_air_flow_rate_per_unit_cooling_capacity": {
                        "type": "number",
                        "units": "m3/s-W",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate per unit cooling capacity. Required field when Cooling Supply Air Flow Rate Method is FlowPerCoolingCapacity."
                    },
                    "heating_supply_air_flow_rate_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "DesignDay",
                            "Flow/System",
                            "FlowPerFloorArea",
                            "FlowPerHeatingCapacity",
                            "FractionOfAutosizedCoolingAirflow",
                            "FractionOfAutosizedHeatingAirflow"
                        ],
                        "default": "DesignDay"
                    },
                    "heating_supply_air_flow_rate": {
                        "type": "number",
                        "note": "Required field when Heating Supply Air Flow Rate Method is Flow/System This value will *not* be multiplied by any sizing factor or by zone multipliers. If using zone multipliers, this value must be large enough to serve the multiplied zones.",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "heating_supply_air_flow_rate_per_floor_area": {
                        "type": "number",
                        "units": "m3/s-m2",
                        "minimum": 0.0,
                        "note": "Enter the heating supply air volume flow rate per total conditioned floor area. Required field when Heating Supply Air Flow Rate Method is FlowPerFloorArea."
                    },
                    "heating_fraction_of_autosized_heating_supply_air_flow_rate": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the heating supply air flow rate. Required field when Heating Supply Air Flow Rate Method is FractionOfAutosizedHeatingAirflow."
                    },
                    "heating_fraction_of_autosized_cooling_supply_air_flow_rate": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the supply air volume flow rate as a fraction of the cooling supply air flow rate. Required field when Heating Supply Air Flow Rate Method is FractionOfAutosizedCoolingAirflow."
                    },
                    "heating_supply_air_flow_rate_per_unit_heating_capacity": {
                        "type": "number",
                        "units": "m3/s-W",
                        "minimum": 0.0,
                        "note": "Enter the heating supply air volume flow rate per unit heating capacity. Required field when Heating Supply Air Flow Rate Method is FlowPerHeatingCapacity."
                    },
                    "system_outdoor_air_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "Standard62.1SimplifiedProcedure",
                            "Standard62.1VentilationRateProcedure",
                            "ZoneSum"
                        ],
                        "default": "ZoneSum"
                    },
                    "zone_maximum_outdoor_air_fraction": {
                        "type": "number",
                        "default": 1.0,
                        "exclusiveMinimum": 0.0,
                        "units": "dimensionless"
                    },
                    "cooling_design_capacity_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "CapacityPerFloorArea",
                            "CoolingDesignCapacity",
                            "FractionOfAutosizedCoolingCapacity",
                            "None"
                        ],
                        "default": "CoolingDesignCapacity",
                        "note": "Enter the method used to determine the system cooling design capacity for scalable sizing. None is used when a cooling coils is not included in an airloop or this field may be blank. If this input field is left blank, then the design cooling capacity is set to zero. CoolingDesignCapacity => selected when the design cooling capacity value is specified or auto-sized. CapacityPerFloorArea => selected when the design cooling capacity is determined from user specified cooling capacity per floor area and total floor area of cooled zones served by an airloop. FractionOfAutosizedCoolingCapacity => is selected when the design cooling capacity is determined from a user specified fraction and the auto-sized design cooling capacity of the system."
                    },
                    "cooling_design_capacity": {
                        "units": "W",
                        "default": "Autosize",
                        "note": "Enter the design cooling capacity.",
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
                    "cooling_design_capacity_per_floor_area": {
                        "type": "number",
                        "units": "W/m2",
                        "minimum": 0.0,
                        "note": "Enter the cooling design capacity per total floor area of cooled zones served by an airloop. Required field when the cooling design capacity method field is CapacityPerFloorArea."
                    },
                    "fraction_of_autosized_cooling_design_capacity": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the fraction of auto-sized cooling design capacity. Required field when the cooling design capacity method field is FractionOfAutosizedCoolingCapacity."
                    },
                    "heating_design_capacity_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "CapacityPerFloorArea",
                            "FractionOfAutosizedHeatingCapacity",
                            "HeatingDesignCapacity",
                            "None"
                        ],
                        "default": "HeatingDesignCapacity",
                        "note": "Enter the method used to determine the heating design capacity for scalable sizing. None is used when a heating coil not included in an airloop or this field may be blank. If this input field is left blank, then the design heating capacity is set to zero. HeatingDesignCapacity => selected when the design heating capacity value is specified or auto-sized. CapacityPerFloorArea => selected when the design heating capacity is determined from user specified heating capacity per flow area and total floor area of heated zones served by an airloop. FractionOfAutosizedHeatingCapacity => is selected when the design heating capacity is determined from a user specified fraction and the auto-sized design heating capacity of the system."
                    },
                    "heating_design_capacity": {
                        "units": "W",
                        "default": "Autosize",
                        "note": "Enter the design heating capacity.",
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
                        "note": "Enter the fraction of auto-sized heating design capacity. Required field when capacity the heating design capacity method field is FractionOfAutosizedHeatingCapacity."
                    },
                    "central_cooling_capacity_control_method": {
                        "type": "string",
                        "note": "Method used to control the coil's output",
                        "enum": [
                            "",
                            "Bypass",
                            "OnOff",
                            "VAV",
                            "VT"
                        ],
                        "default": "OnOff"
                    },
                    "occupant_diversity": {
                        "default": "Autosize",
                        "note": "The Occupant Diversity is used to determine a multi-zone system's outdoor air intake when the System Outdoor Air Method is  Standard62.1VentilationRateProcedure or the Standard62.1SimplifiedProcedure. If set to be autosized, it will be calculated using the information in the People objects assigned to each zone attached to this system/airloop.",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    }
                },
                "required": [
                    "airloop_name",
                    "preheat_design_temperature",
                    "preheat_design_humidity_ratio",
                    "precool_design_temperature",
                    "precool_design_humidity_ratio",
                    "central_cooling_design_supply_air_temperature",
                    "central_heating_design_supply_air_temperature"
                ]
            }
        },
        "group": "HVAC Design Objects",
        "legacy_idd": {
            "field_info": {
                "airloop_name": {
                    "field_name": "AirLoop Name",
                    "field_type": "a"
                },
                "type_of_load_to_size_on": {
                    "field_name": "Type of Load to Size On",
                    "field_type": "a"
                },
                "design_outdoor_air_flow_rate": {
                    "field_name": "Design Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "central_heating_maximum_system_air_flow_ratio": {
                    "field_name": "Central Heating Maximum System Air Flow Ratio",
                    "field_type": "n"
                },
                "preheat_design_temperature": {
                    "field_name": "Preheat Design Temperature",
                    "field_type": "n"
                },
                "preheat_design_humidity_ratio": {
                    "field_name": "Preheat Design Humidity Ratio",
                    "field_type": "n"
                },
                "precool_design_temperature": {
                    "field_name": "Precool Design Temperature",
                    "field_type": "n"
                },
                "precool_design_humidity_ratio": {
                    "field_name": "Precool Design Humidity Ratio",
                    "field_type": "n"
                },
                "central_cooling_design_supply_air_temperature": {
                    "field_name": "Central Cooling Design Supply Air Temperature",
                    "field_type": "n"
                },
                "central_heating_design_supply_air_temperature": {
                    "field_name": "Central Heating Design Supply Air Temperature",
                    "field_type": "n"
                },
                "type_of_zone_sum_to_use": {
                    "field_name": "Type of Zone Sum to Use",
                    "field_type": "a"
                },
                "100_outdoor_air_in_cooling": {
                    "field_name": "100% Outdoor Air in Cooling",
                    "field_type": "a"
                },
                "100_outdoor_air_in_heating": {
                    "field_name": "100% Outdoor Air in Heating",
                    "field_type": "a"
                },
                "central_cooling_design_supply_air_humidity_ratio": {
                    "field_name": "Central Cooling Design Supply Air Humidity Ratio",
                    "field_type": "n"
                },
                "central_heating_design_supply_air_humidity_ratio": {
                    "field_name": "Central Heating Design Supply Air Humidity Ratio",
                    "field_type": "n"
                },
                "cooling_supply_air_flow_rate_method": {
                    "field_name": "Cooling Supply Air Flow Rate Method",
                    "field_type": "a"
                },
                "cooling_supply_air_flow_rate": {
                    "field_name": "Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_supply_air_flow_rate_per_floor_area": {
                    "field_name": "Cooling Supply Air Flow Rate Per Floor Area",
                    "field_type": "n"
                },
                "cooling_fraction_of_autosized_cooling_supply_air_flow_rate": {
                    "field_name": "Cooling Fraction of Autosized Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_supply_air_flow_rate_per_unit_cooling_capacity": {
                    "field_name": "Cooling Supply Air Flow Rate Per Unit Cooling Capacity",
                    "field_type": "n"
                },
                "heating_supply_air_flow_rate_method": {
                    "field_name": "Heating Supply Air Flow Rate Method",
                    "field_type": "a"
                },
                "heating_supply_air_flow_rate": {
                    "field_name": "Heating Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_supply_air_flow_rate_per_floor_area": {
                    "field_name": "Heating Supply Air Flow Rate Per Floor Area",
                    "field_type": "n"
                },
                "heating_fraction_of_autosized_heating_supply_air_flow_rate": {
                    "field_name": "Heating Fraction of Autosized Heating Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_fraction_of_autosized_cooling_supply_air_flow_rate": {
                    "field_name": "Heating Fraction of Autosized Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_supply_air_flow_rate_per_unit_heating_capacity": {
                    "field_name": "Heating Supply Air Flow Rate Per Unit Heating Capacity",
                    "field_type": "n"
                },
                "system_outdoor_air_method": {
                    "field_name": "System Outdoor Air Method",
                    "field_type": "a"
                },
                "zone_maximum_outdoor_air_fraction": {
                    "field_name": "Zone Maximum Outdoor Air Fraction",
                    "field_type": "n"
                },
                "cooling_design_capacity_method": {
                    "field_name": "Cooling Design Capacity Method",
                    "field_type": "a"
                },
                "cooling_design_capacity": {
                    "field_name": "Cooling Design Capacity",
                    "field_type": "n"
                },
                "cooling_design_capacity_per_floor_area": {
                    "field_name": "Cooling Design Capacity Per Floor Area",
                    "field_type": "n"
                },
                "fraction_of_autosized_cooling_design_capacity": {
                    "field_name": "Fraction of Autosized Cooling Design Capacity",
                    "field_type": "n"
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
                "central_cooling_capacity_control_method": {
                    "field_name": "Central Cooling Capacity Control Method",
                    "field_type": "a"
                },
                "occupant_diversity": {
                    "field_name": "Occupant Diversity",
                    "field_type": "n"
                }
            },
            "fields": [
                "airloop_name",
                "type_of_load_to_size_on",
                "design_outdoor_air_flow_rate",
                "central_heating_maximum_system_air_flow_ratio",
                "preheat_design_temperature",
                "preheat_design_humidity_ratio",
                "precool_design_temperature",
                "precool_design_humidity_ratio",
                "central_cooling_design_supply_air_temperature",
                "central_heating_design_supply_air_temperature",
                "type_of_zone_sum_to_use",
                "100_outdoor_air_in_cooling",
                "100_outdoor_air_in_heating",
                "central_cooling_design_supply_air_humidity_ratio",
                "central_heating_design_supply_air_humidity_ratio",
                "cooling_supply_air_flow_rate_method",
                "cooling_supply_air_flow_rate",
                "cooling_supply_air_flow_rate_per_floor_area",
                "cooling_fraction_of_autosized_cooling_supply_air_flow_rate",
                "cooling_supply_air_flow_rate_per_unit_cooling_capacity",
                "heating_supply_air_flow_rate_method",
                "heating_supply_air_flow_rate",
                "heating_supply_air_flow_rate_per_floor_area",
                "heating_fraction_of_autosized_heating_supply_air_flow_rate",
                "heating_fraction_of_autosized_cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate_per_unit_heating_capacity",
                "system_outdoor_air_method",
                "zone_maximum_outdoor_air_fraction",
                "cooling_design_capacity_method",
                "cooling_design_capacity",
                "cooling_design_capacity_per_floor_area",
                "fraction_of_autosized_cooling_design_capacity",
                "heating_design_capacity_method",
                "heating_design_capacity",
                "heating_design_capacity_per_floor_area",
                "fraction_of_autosized_heating_design_capacity",
                "central_cooling_capacity_control_method",
                "occupant_diversity"
            ],
            "alphas": {
                "fields": [
                    "airloop_name",
                    "type_of_load_to_size_on",
                    "type_of_zone_sum_to_use",
                    "100_outdoor_air_in_cooling",
                    "100_outdoor_air_in_heating",
                    "cooling_supply_air_flow_rate_method",
                    "heating_supply_air_flow_rate_method",
                    "system_outdoor_air_method",
                    "cooling_design_capacity_method",
                    "heating_design_capacity_method",
                    "central_cooling_capacity_control_method"
                ]
            },
            "numerics": {
                "fields": [
                    "design_outdoor_air_flow_rate",
                    "central_heating_maximum_system_air_flow_ratio",
                    "preheat_design_temperature",
                    "preheat_design_humidity_ratio",
                    "precool_design_temperature",
                    "precool_design_humidity_ratio",
                    "central_cooling_design_supply_air_temperature",
                    "central_heating_design_supply_air_temperature",
                    "central_cooling_design_supply_air_humidity_ratio",
                    "central_heating_design_supply_air_humidity_ratio",
                    "cooling_supply_air_flow_rate",
                    "cooling_supply_air_flow_rate_per_floor_area",
                    "cooling_fraction_of_autosized_cooling_supply_air_flow_rate",
                    "cooling_supply_air_flow_rate_per_unit_cooling_capacity",
                    "heating_supply_air_flow_rate",
                    "heating_supply_air_flow_rate_per_floor_area",
                    "heating_fraction_of_autosized_heating_supply_air_flow_rate",
                    "heating_fraction_of_autosized_cooling_supply_air_flow_rate",
                    "heating_supply_air_flow_rate_per_unit_heating_capacity",
                    "zone_maximum_outdoor_air_fraction",
                    "cooling_design_capacity",
                    "cooling_design_capacity_per_floor_area",
                    "fraction_of_autosized_cooling_design_capacity",
                    "heating_design_capacity",
                    "heating_design_capacity_per_floor_area",
                    "fraction_of_autosized_heating_design_capacity",
                    "occupant_diversity"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies the input needed to perform sizing calculations for a central forced air system. System design air flow, heating capacity, and cooling capacity will be calculated using this input data.",
        "min_fields": 37.0
    }
}
```
