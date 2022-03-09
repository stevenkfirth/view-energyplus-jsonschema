```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "cooling_supply_air_flow_rate_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "FlowPerCoolingCapacity",
                        "FlowPerFloorArea",
                        "FractionOfAutosizedCoolingAirflow",
                        "None",
                        "SupplyAirFlowRate"
                    ],
                    "default": "SupplyAirFlowRate",
                    "note": "Enter the method used to determine the cooling supply air volume flow rate. None is used when a cooling coil is not included in the Zone HVAC Equip or this field may be blank. SupplyAirFlowRate => selected when the magnitude of the supply air volume flow rate is specified. FlowPerFloorArea => selected when the supply air volume flow rate is determined from total floor area served by the Zone HVAC unit and Flow Per Floor Area value specified. FractionOfAutosizedCoolingAirflow => is selected when the supply air volume is determined from a user specified fraction and the autosized cooling supply air flow rate value determined by the simulation. FlowPerCoolingCapacity => is selected when the supply air volume is determined from user specified flow per Cooling Capacity and Cooling Capacity determined by the simulation."
                },
                "cooling_supply_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Enter the magnitude of supply air volume flow rate during cooling operation. Required field when Cooling Supply Air Flow Rate Method is SupplyAirFlowRate. This field may be blank if a cooling coil is not included in the Zone HVAC equipment.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "cooling_supply_air_flow_rate_per_floor_area": {
                    "type": "number",
                    "units": "m3/s-m2",
                    "minimum": 0.0,
                    "note": "Enter the cooling supply air volume flow rate per total conditioned floor area. Required field when Cooling Supply Air Flow Rate Method is FlowPerFloorArea. This field may be blank if a cooling coil is not included in the Zone HVAC equipment."
                },
                "cooling_fraction_of_autosized_cooling_supply_air_flow_rate": {
                    "type": "number",
                    "minimum": 0.0,
                    "note": "Enter the supply air volume flow rate as a fraction of the cooling supply air flow rate. Required field when Cooling Supply Air Flow Rate Method is FractionOfAutosizedCoolingAirflow. This field may be blank if a cooling coil is not included in the Zone HVAC equipment."
                },
                "cooling_supply_air_flow_rate_per_unit_cooling_capacity": {
                    "type": "number",
                    "units": "m3/s-W",
                    "minimum": 0.0,
                    "note": "Enter the cooling supply air volume flow rate unit cooling capacity. Required field when Cooling Supply Air Flow Rate Method is FlowPerCoolingCapacity. This field may be blank if a cooling coil is not included in the Zone HVAC equipment."
                },
                "no_load_supply_air_flow_rate_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "FlowPerFloorArea",
                        "FractionOfAutosizedCoolingAirflow",
                        "FractionOfAutosizedHeatingAirflow",
                        "None",
                        "SupplyAirFlowRate"
                    ],
                    "default": "SupplyAirFlowRate",
                    "note": "Enter the method used to determine the supply air volume flow rate When No Cooling or Heating is Required. None is used when a cooling or heating coil is not included in the Zone HVAC Equipment or this field may be blank. SupplyAirFlowRate => selected when the magnitude of the supply air volume flow rate is specified. FlowPerFloorArea => selected when the supply air volume flow rate is determined from total floor area served by the Zone HVAC unit and Flow Per Floor Area is specified. FractionOfAutosizedCoolingAirflow => is selected when the supply air volume is determined from a user specified fraction and the Autosized cooling supply air flow rate value determined by the simulation. FractionOfAutosizedHeatingAirflow => is selected when the supply air volume is determined from a user specified fraction and the Autosized heating supply air flow rate value determined by the simulation."
                },
                "no_load_supply_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Enter the magnitude of the supply air volume flow rate during when no cooling or heating is required. Required field when No Load Supply Air Flow Rate Method is SupplyAirFlowRate.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "no_load_supply_air_flow_rate_per_floor_area": {
                    "type": "number",
                    "units": "m3/s-m2",
                    "minimum": 0.0,
                    "note": "Enter the supply air volume flow rate per total floor area. Required field when No Load Supply Air Flow Rate Method is FlowPerFloorArea."
                },
                "no_load_fraction_of_cooling_supply_air_flow_rate": {
                    "type": "number",
                    "minimum": 0.0,
                    "note": "Enter the supply air volume flow rate as a fraction of the cooling supply air flow rate. Required field when No Load Supply Air Flow Rate Method is FractionOfAutosizedCoolingAirflow."
                },
                "no_load_fraction_of_heating_supply_air_flow_rate": {
                    "type": "number",
                    "minimum": 0.0,
                    "note": "Enter the supply air volume flow rate as a fraction of the heating supply air flow rate. Required field when No Load Supply Air Flow Rate Method is FractionOfAutosizedHeatingAirflow."
                },
                "heating_supply_air_flow_rate_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "FlowPerFloorArea",
                        "FlowPerHeatingCapacity",
                        "FractionOfAutosizedHeatingAirflow",
                        "None",
                        "SupplyAirFlowRate"
                    ],
                    "default": "SupplyAirFlowRate",
                    "note": "Enter the method used to determine the heating supply air volume flow rate. None is used when a heating coil is not included in the Zone HVAC Equipment or this field may be blank. SupplyAirFlowRate => selected when the magnitude of the heating supply air volume flow rate is specified. FlowPerFloorArea => selected when the supply air volume flow rate is determined from total floor area served by a Zone HVAC unit and user specified value of Flow Per Floor Area. FractionOfAutosizedHeatingAirflow => is selected when the supply air volume is determined from a user specified fraction and the Autosized heating supply air flow rate value determined by the simulation. FlowPerHeatingCapacity => is selected when the supply air volume is determined from user specified flow per Heating Capacity and Heating Capacity determined by the simulation."
                },
                "heating_supply_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Enter the magnitude of the supply air volume flow rate during heating operation. Required field when Heating Supply Air Flow Rate Method is SupplyAirFlowRate. This field may be blank if a heating coil is not included in the Zone HVAC equipment.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "heating_supply_air_flow_rate_per_floor_area": {
                    "type": "number",
                    "units": "m3/s-m2",
                    "minimum": 0.0,
                    "note": "Enter the heating supply air volume flow rate per total conditioned floor area. Required field when Heating Supply Air Flow Rate Method is FlowPerFloorArea. This field may be blank if a heating coil is not included in the Zone HVAC equipment."
                },
                "heating_fraction_of_heating_supply_air_flow_rate": {
                    "type": "number",
                    "minimum": 0.0,
                    "note": "Enter the supply air volume flow rate as a fraction of the heating supply air flow rate. Required field when Heating Supply Air Flow Rate Method is FractionOfAutosizedHeatingAirflow. This field may be blank if a heating coil is not included in the Zone HVAC equipment."
                },
                "heating_supply_air_flow_rate_per_unit_heating_capacity": {
                    "type": "number",
                    "units": "m3/s-W",
                    "minimum": 0.0,
                    "note": "Enter the supply air volume flow rate per unit heating capacity. Required field when Heating Supply Air Flow Rate Method is FlowPerHeatingCapacity. This field may be blank if a heating coil is not included in the Zone HVAC equipment."
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
                    "default": "None",
                    "note": "Enter the method used to determine the cooling design capacity for scalable sizing. None is used when a cooling coils is not included in the Zone HVAC Equipment or this field may be blank. If this input field is left blank, then the design cooling capacity is set to zero. CoolingDesignCapacity => selected when the design cooling capacity value is specified or auto-sized. CapacityPerFloorArea => selected when the design cooling capacity is determine from user specified cooling capacity per floor area and zone floor area. FractionOfAutosizedCoolingCapacity => is selected when the design cooling capacity is determined from a user specified fraction and the auto-sized design cooling capacity."
                },
                "cooling_design_capacity": {
                    "units": "W",
                    "note": "Enter the design cooling capacity. Required field when the cooling design capacity method CoolingDesignCapacity.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "cooling_design_capacity_per_floor_area": {
                    "type": "number",
                    "units": "W/m2",
                    "minimum": 0.0,
                    "note": "Enter the cooling design capacity per zone floor area. Required field when the cooling design capacity method field is CapacityPerFloorArea."
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
                    "default": "None",
                    "note": "Enter the method used to determine the heating design capacity for scalable sizing. None is used when a heating coil is not included in the Zone HVAC Equipment or this field may be blank. If this input field is left blank, then the design heating capacity is set to zero. HeatingDesignCapacity => selected when the design heating capacity value is specified or auto-sized. CapacityPerFloorArea => selected when the design cooling capacity is determine from user specified heating capacity per flow area and zone floor area. FractionOfAutosizedHeatingCapacity => is selected when the design heating capacity is determined from a user specified fraction and the auto-sized design heating capacity"
                },
                "heating_design_capacity": {
                    "units": "W",
                    "note": "Enter the design heating capacity. Required field when the heating design capacity method HeatingDesignCapacity.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
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
                }
            }
        }
    },
    "group": "HVAC Design Objects",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DesignSpecificationZoneHVACSizingName"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
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
            "no_load_supply_air_flow_rate_method": {
                "field_name": "No Load Supply Air Flow Rate Method",
                "field_type": "a"
            },
            "no_load_supply_air_flow_rate": {
                "field_name": "No Load Supply Air Flow Rate",
                "field_type": "n"
            },
            "no_load_supply_air_flow_rate_per_floor_area": {
                "field_name": "No Load Supply Air Flow Rate Per Floor Area",
                "field_type": "n"
            },
            "no_load_fraction_of_cooling_supply_air_flow_rate": {
                "field_name": "No Load Fraction of Cooling Supply Air Flow Rate",
                "field_type": "n"
            },
            "no_load_fraction_of_heating_supply_air_flow_rate": {
                "field_name": "No Load Fraction of Heating Supply Air Flow Rate",
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
            "heating_fraction_of_heating_supply_air_flow_rate": {
                "field_name": "Heating Fraction of Heating Supply Air Flow Rate",
                "field_type": "n"
            },
            "heating_supply_air_flow_rate_per_unit_heating_capacity": {
                "field_name": "Heating Supply Air Flow Rate Per Unit Heating Capacity",
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
            }
        },
        "fields": [
            "name",
            "cooling_supply_air_flow_rate_method",
            "cooling_supply_air_flow_rate",
            "cooling_supply_air_flow_rate_per_floor_area",
            "cooling_fraction_of_autosized_cooling_supply_air_flow_rate",
            "cooling_supply_air_flow_rate_per_unit_cooling_capacity",
            "no_load_supply_air_flow_rate_method",
            "no_load_supply_air_flow_rate",
            "no_load_supply_air_flow_rate_per_floor_area",
            "no_load_fraction_of_cooling_supply_air_flow_rate",
            "no_load_fraction_of_heating_supply_air_flow_rate",
            "heating_supply_air_flow_rate_method",
            "heating_supply_air_flow_rate",
            "heating_supply_air_flow_rate_per_floor_area",
            "heating_fraction_of_heating_supply_air_flow_rate",
            "heating_supply_air_flow_rate_per_unit_heating_capacity",
            "cooling_design_capacity_method",
            "cooling_design_capacity",
            "cooling_design_capacity_per_floor_area",
            "fraction_of_autosized_cooling_design_capacity",
            "heating_design_capacity_method",
            "heating_design_capacity",
            "heating_design_capacity_per_floor_area",
            "fraction_of_autosized_heating_design_capacity"
        ],
        "alphas": {
            "fields": [
                "name",
                "cooling_supply_air_flow_rate_method",
                "no_load_supply_air_flow_rate_method",
                "heating_supply_air_flow_rate_method",
                "cooling_design_capacity_method",
                "heating_design_capacity_method"
            ]
        },
        "numerics": {
            "fields": [
                "cooling_supply_air_flow_rate",
                "cooling_supply_air_flow_rate_per_floor_area",
                "cooling_fraction_of_autosized_cooling_supply_air_flow_rate",
                "cooling_supply_air_flow_rate_per_unit_cooling_capacity",
                "no_load_supply_air_flow_rate",
                "no_load_supply_air_flow_rate_per_floor_area",
                "no_load_fraction_of_cooling_supply_air_flow_rate",
                "no_load_fraction_of_heating_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "heating_supply_air_flow_rate_per_floor_area",
                "heating_fraction_of_heating_supply_air_flow_rate",
                "heating_supply_air_flow_rate_per_unit_heating_capacity",
                "cooling_design_capacity",
                "cooling_design_capacity_per_floor_area",
                "fraction_of_autosized_cooling_design_capacity",
                "heating_design_capacity",
                "heating_design_capacity_per_floor_area",
                "fraction_of_autosized_heating_design_capacity"
            ]
        }
    },
    "type": "object",
    "memo": "This object is used to describe general scalable zone HVAC equipment sizing which are referenced by other objects.",
    "min_fields": 1.0
}
```
