```
{
    "ZoneHVAC:LowTemperatureRadiant:Electric": {
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
                    "surface_name_or_radiant_surface_group_name": {
                        "type": "string",
                        "note": "Identifies surfaces that radiant system is embedded in. For a system with multiple surfaces, enter the name of a ZoneHVAC:LowTemperatureRadiant:SurfaceGroup object.",
                        "data_type": "object_list",
                        "object_list": [
                            "RadiantGroupNames",
                            "RadiantSurfaceNames"
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
                        "note": "Enter the method used to determine the maximum electrical heating design capacity. HeatingDesignCapacity = > selected when the design heating capacity value or autosize is specified. CapacityPerFloorArea = > selected when the design heating capacity is determine from user specified heating capacity per floor area and zone floor area. FractionOfAutosizedHeatingCapacity = > is selected when the design heating capacity is determined from a user specified fraction and the auto-sized design heating capacity."
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
                    "temperature_control_type": {
                        "type": "string",
                        "note": "Temperature used to control unit",
                        "enum": [
                            "",
                            "MeanAirTemperature",
                            "MeanRadiantTemperature",
                            "OperativeTemperature",
                            "OutdoorDryBulbTemperature",
                            "OutdoorWetBulbTemperature",
                            "SurfaceFaceTemperature",
                            "SurfaceInteriorTemperature"
                        ],
                        "default": "MeanAirTemperature"
                    },
                    "setpoint_control_type": {
                        "type": "string",
                        "note": "How setpoint temperature is defined",
                        "enum": [
                            "",
                            "HalfFlowPower",
                            "ZeroFlowPower"
                        ],
                        "default": "HalfFlowPower"
                    },
                    "heating_throttling_range": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "heating_setpoint_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "heating_setpoint_temperature_schedule_name"
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
                "surface_name_or_radiant_surface_group_name": {
                    "field_name": "Surface Name or Radiant Surface Group Name",
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
                "temperature_control_type": {
                    "field_name": "Temperature Control Type",
                    "field_type": "a"
                },
                "setpoint_control_type": {
                    "field_name": "Setpoint Control Type",
                    "field_type": "a"
                },
                "heating_throttling_range": {
                    "field_name": "Heating Throttling Range",
                    "field_type": "n"
                },
                "heating_setpoint_temperature_schedule_name": {
                    "field_name": "Heating Setpoint Temperature Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "surface_name_or_radiant_surface_group_name",
                "heating_design_capacity_method",
                "heating_design_capacity",
                "heating_design_capacity_per_floor_area",
                "fraction_of_autosized_heating_design_capacity",
                "temperature_control_type",
                "setpoint_control_type",
                "heating_throttling_range",
                "heating_setpoint_temperature_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "zone_name",
                    "surface_name_or_radiant_surface_group_name",
                    "heating_design_capacity_method",
                    "temperature_control_type",
                    "setpoint_control_type",
                    "heating_setpoint_temperature_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "heating_design_capacity",
                    "heating_design_capacity_per_floor_area",
                    "fraction_of_autosized_heating_design_capacity",
                    "heating_throttling_range"
                ]
            }
        },
        "type": "object",
        "memo": "Electric resistance low temperature radiant system",
        "min_fields": 12.0
    }
}
```
