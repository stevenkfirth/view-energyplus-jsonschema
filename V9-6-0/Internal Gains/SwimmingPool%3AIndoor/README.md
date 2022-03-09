```
{
    "SwimmingPool:Indoor": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "surface_name": {
                        "type": "string",
                        "note": "Name of the floor surface where the pool is located.",
                        "data_type": "object_list",
                        "object_list": [
                            "FloorSurfaceNames"
                        ]
                    },
                    "average_depth": {
                        "type": "number",
                        "units": "m"
                    },
                    "activity_factor_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "make_up_water_supply_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cover_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cover_evaporation_factor": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "cover_convection_factor": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "cover_short_wavelength_radiation_factor": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "cover_long_wavelength_radiation_factor": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "pool_water_inlet_node": {
                        "type": "string"
                    },
                    "pool_water_outlet_node": {
                        "type": "string"
                    },
                    "pool_heating_system_maximum_water_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "minimum": 0.0
                    },
                    "pool_miscellaneous_equipment_power": {
                        "type": "number",
                        "note": "Power input per pool water flow rate",
                        "units": "W/(m3/s)",
                        "ip-units": "W/(gal/min)",
                        "minimum": 0.0
                    },
                    "setpoint_temperature_schedule": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "maximum_number_of_people": {
                        "type": "number",
                        "minimum": 0.0
                    },
                    "people_schedule": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "people_heat_gain_schedule": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "surface_name",
                    "average_depth",
                    "activity_factor_schedule_name",
                    "make_up_water_supply_schedule_name",
                    "cover_schedule_name",
                    "pool_water_inlet_node",
                    "pool_water_outlet_node",
                    "setpoint_temperature_schedule",
                    "maximum_number_of_people"
                ]
            }
        },
        "group": "Internal Gains",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ],
            "reference": [
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
                "surface_name": {
                    "field_name": "Surface Name",
                    "field_type": "a"
                },
                "average_depth": {
                    "field_name": "Average Depth",
                    "field_type": "n"
                },
                "activity_factor_schedule_name": {
                    "field_name": "Activity Factor Schedule Name",
                    "field_type": "a"
                },
                "make_up_water_supply_schedule_name": {
                    "field_name": "Make-up Water Supply Schedule Name",
                    "field_type": "a"
                },
                "cover_schedule_name": {
                    "field_name": "Cover Schedule Name",
                    "field_type": "a"
                },
                "cover_evaporation_factor": {
                    "field_name": "Cover Evaporation Factor",
                    "field_type": "n"
                },
                "cover_convection_factor": {
                    "field_name": "Cover Convection Factor",
                    "field_type": "n"
                },
                "cover_short_wavelength_radiation_factor": {
                    "field_name": "Cover Short-Wavelength Radiation Factor",
                    "field_type": "n"
                },
                "cover_long_wavelength_radiation_factor": {
                    "field_name": "Cover Long-Wavelength Radiation Factor",
                    "field_type": "n"
                },
                "pool_water_inlet_node": {
                    "field_name": "Pool Water Inlet Node",
                    "field_type": "a"
                },
                "pool_water_outlet_node": {
                    "field_name": "Pool Water Outlet Node",
                    "field_type": "a"
                },
                "pool_heating_system_maximum_water_flow_rate": {
                    "field_name": "Pool Heating System Maximum Water Flow Rate",
                    "field_type": "n"
                },
                "pool_miscellaneous_equipment_power": {
                    "field_name": "Pool Miscellaneous Equipment Power",
                    "field_type": "n"
                },
                "setpoint_temperature_schedule": {
                    "field_name": "Setpoint Temperature Schedule",
                    "field_type": "a"
                },
                "maximum_number_of_people": {
                    "field_name": "Maximum Number of People",
                    "field_type": "n"
                },
                "people_schedule": {
                    "field_name": "People Schedule",
                    "field_type": "a"
                },
                "people_heat_gain_schedule": {
                    "field_name": "People Heat Gain Schedule",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "surface_name",
                "average_depth",
                "activity_factor_schedule_name",
                "make_up_water_supply_schedule_name",
                "cover_schedule_name",
                "cover_evaporation_factor",
                "cover_convection_factor",
                "cover_short_wavelength_radiation_factor",
                "cover_long_wavelength_radiation_factor",
                "pool_water_inlet_node",
                "pool_water_outlet_node",
                "pool_heating_system_maximum_water_flow_rate",
                "pool_miscellaneous_equipment_power",
                "setpoint_temperature_schedule",
                "maximum_number_of_people",
                "people_schedule",
                "people_heat_gain_schedule"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "surface_name",
                    "activity_factor_schedule_name",
                    "make_up_water_supply_schedule_name",
                    "cover_schedule_name",
                    "pool_water_inlet_node",
                    "pool_water_outlet_node",
                    "setpoint_temperature_schedule",
                    "people_schedule",
                    "people_heat_gain_schedule"
                ]
            },
            "numerics": {
                "fields": [
                    "average_depth",
                    "cover_evaporation_factor",
                    "cover_convection_factor",
                    "cover_short_wavelength_radiation_factor",
                    "cover_long_wavelength_radiation_factor",
                    "pool_heating_system_maximum_water_flow_rate",
                    "pool_miscellaneous_equipment_power",
                    "maximum_number_of_people"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies an indoor swimming pools linked to a floor surface. The pool is assumed to cover the entire floor to which it is linked.",
        "min_fields": 16.0
    }
}
```
