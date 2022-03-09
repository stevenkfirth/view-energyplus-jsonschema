```
{
    "ZoneHVAC:LowTemperatureRadiant:VariableFlow:Design": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "fluid_to_radiant_surface_heat_transfer_model": {
                        "type": "string",
                        "note": "This parameter identifies how the heat transfer between fluid being circulated through the radiant system and the radiant system (slab) is modeled. ConvectionOnly means that only convection between the fluid and the inside surface of the pipe is modeled using a conventional equation for flow inside a pipe. ISOStandard models convection between the fluid and the inside of of the pipe and conduction through the pipe material using equations specific to ISO Standard 11855-2.",
                        "enum": [
                            "",
                            "ConvectionOnly",
                            "ISOStandard"
                        ],
                        "default": "ConvectionOnly"
                    },
                    "hydronic_tubing_inside_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.013,
                        "ip-units": "in"
                    },
                    "hydronic_tubing_outside_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "default": 0.016,
                        "ip-units": "in"
                    },
                    "hydronic_tubing_conductivity": {
                        "type": "number",
                        "note": "Conductivity of the tubing/piping material",
                        "units": "W/m-K",
                        "exclusiveMinimum": 0.0,
                        "default": 0.35
                    },
                    "temperature_control_type": {
                        "type": "string",
                        "note": "(Temperature on which unit is controlled)",
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
                    "heating_control_throttling_range": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 0.5
                    },
                    "heating_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
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
                        "note": "Enter the method used to determine the cooling design capacity for scalable sizing. CoolingDesignCapacity => selected when the design cooling capacity value is specified or auto-sized. CapacityPerFloorArea => selected when the design cooling capacity is determined from user specified cooling capacity per floor area and total floor area of cooled zone served by the hydrolic unit. FractionOfAutosizedCoolingCapacity => is selected when the design cooling capacity is determined from a user specified fraction and the auto-sized design cooling capacity of the system."
                    },
                    "cooling_design_capacity_per_floor_area": {
                        "type": "number",
                        "units": "W/m2",
                        "minimum": 0.0,
                        "note": "Enter the cooling design capacity per total floor area of cooled zones served by the unit. Required field when the cooling design capacity method field is CapacityPerFloorArea."
                    },
                    "fraction_of_autosized_cooling_design_capacity": {
                        "type": "number",
                        "minimum": 0.0,
                        "note": "Enter the fraction of auto-sized cooling design capacity. Required field when the cooling design capacity method field is FractionOfAutosizedCoolingCapacity."
                    },
                    "cooling_control_throttling_range": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 0.5
                    },
                    "cooling_control_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "condensation_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Off",
                            "SimpleOff",
                            "VariableOff"
                        ],
                        "default": "SimpleOff"
                    },
                    "condensation_control_dewpoint_offset": {
                        "type": "number",
                        "units": "C",
                        "default": 1.0
                    },
                    "changeover_delay_time_period_schedule": {
                        "type": "string",
                        "note": "Changeover delay schedule name for this system. Schedule value <= 0 allows changeover with no delay The schedule values are interpretted as hours. If this field is blank, the system allows changeover with no delay",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                }
            }
        },
        "group": "Zone HVAC Radiative/Convective Units",
        "name": {
            "type": "string",
            "reference": [
                "RadiantDesignObject"
            ]
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "fluid_to_radiant_surface_heat_transfer_model": {
                    "field_name": "Fluid to Radiant Surface Heat Transfer Model",
                    "field_type": "a"
                },
                "hydronic_tubing_inside_diameter": {
                    "field_name": "Hydronic Tubing Inside Diameter",
                    "field_type": "n"
                },
                "hydronic_tubing_outside_diameter": {
                    "field_name": "Hydronic Tubing Outside Diameter",
                    "field_type": "n"
                },
                "hydronic_tubing_conductivity": {
                    "field_name": "Hydronic Tubing Conductivity",
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
                "heating_control_throttling_range": {
                    "field_name": "Heating Control Throttling Range",
                    "field_type": "n"
                },
                "heating_control_temperature_schedule_name": {
                    "field_name": "Heating Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_design_capacity_method": {
                    "field_name": "Cooling Design Capacity Method",
                    "field_type": "a"
                },
                "cooling_design_capacity_per_floor_area": {
                    "field_name": "Cooling Design Capacity Per Floor Area",
                    "field_type": "n"
                },
                "fraction_of_autosized_cooling_design_capacity": {
                    "field_name": "Fraction of Autosized Cooling Design Capacity",
                    "field_type": "n"
                },
                "cooling_control_throttling_range": {
                    "field_name": "Cooling Control Throttling Range",
                    "field_type": "n"
                },
                "cooling_control_temperature_schedule_name": {
                    "field_name": "Cooling Control Temperature Schedule Name",
                    "field_type": "a"
                },
                "condensation_control_type": {
                    "field_name": "Condensation Control Type",
                    "field_type": "a"
                },
                "condensation_control_dewpoint_offset": {
                    "field_name": "Condensation Control Dewpoint Offset",
                    "field_type": "n"
                },
                "changeover_delay_time_period_schedule": {
                    "field_name": "Changeover Delay Time Period Schedule",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "fluid_to_radiant_surface_heat_transfer_model",
                "hydronic_tubing_inside_diameter",
                "hydronic_tubing_outside_diameter",
                "hydronic_tubing_conductivity",
                "temperature_control_type",
                "setpoint_control_type",
                "heating_design_capacity_method",
                "heating_design_capacity_per_floor_area",
                "fraction_of_autosized_heating_design_capacity",
                "heating_control_throttling_range",
                "heating_control_temperature_schedule_name",
                "cooling_design_capacity_method",
                "cooling_design_capacity_per_floor_area",
                "fraction_of_autosized_cooling_design_capacity",
                "cooling_control_throttling_range",
                "cooling_control_temperature_schedule_name",
                "condensation_control_type",
                "condensation_control_dewpoint_offset",
                "changeover_delay_time_period_schedule"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "fluid_to_radiant_surface_heat_transfer_model",
                    "temperature_control_type",
                    "setpoint_control_type",
                    "heating_design_capacity_method",
                    "heating_control_temperature_schedule_name",
                    "cooling_design_capacity_method",
                    "cooling_control_temperature_schedule_name",
                    "condensation_control_type",
                    "changeover_delay_time_period_schedule"
                ]
            },
            "numerics": {
                "fields": [
                    "hydronic_tubing_inside_diameter",
                    "hydronic_tubing_outside_diameter",
                    "hydronic_tubing_conductivity",
                    "heating_design_capacity_per_floor_area",
                    "fraction_of_autosized_heating_design_capacity",
                    "heating_control_throttling_range",
                    "cooling_design_capacity_per_floor_area",
                    "fraction_of_autosized_cooling_design_capacity",
                    "cooling_control_throttling_range",
                    "condensation_control_dewpoint_offset"
                ]
            }
        },
        "type": "object",
        "min_fields": 19.0
    }
}
```
