```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "water_inlet_node_name": {
                    "type": "string"
                },
                "water_outlet_node_name": {
                    "type": "string"
                },
                "rated_inlet_water_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 5.0
                },
                "rated_inlet_space_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 24.0
                },
                "rated_water_mass_flow_rate": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "kg/s",
                    "default": 0.063
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
                    "note": "Enter the cooling design capacity per total floor area of cooled zones served by the unit. Required field when the cooling design capacity method field is CapacityPerFloorArea."
                },
                "fraction_of_autosized_cooling_design_capacity": {
                    "type": "number",
                    "minimum": 0.0,
                    "note": "Enter the fraction of auto-sized cooling design capacity. Required field when the cooling design capacity method field is FractionOfAutosizedCoolingCapacity."
                },
                "maximum_chilled_water_flow_rate": {
                    "units": "m3/s",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "control_type": {
                    "type": "string",
                    "note": "Temperature on which unit is controlled",
                    "enum": [
                        "",
                        "MeanAirTemperature",
                        "MeanRadiantTemperature",
                        "OperativeTemperature",
                        "OutdoorDryBulbTemperature",
                        "OutdoorWetBulbTemperature",
                        "ZoneConvectiveLoad",
                        "ZoneTotalLoad"
                    ],
                    "default": "MeanAirTemperature"
                },
                "cooling_control_throttling_range": {
                    "type": "number",
                    "units": "deltaC",
                    "minimum": 0.5,
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
                "availability_schedule_name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "maximum_chilled_water_flow_rate",
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
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
                "field_type": "a"
            },
            "water_inlet_node_name": {
                "field_name": "Water Inlet Node Name",
                "field_type": "a"
            },
            "water_outlet_node_name": {
                "field_name": "Water Outlet Node Name",
                "field_type": "a"
            },
            "rated_inlet_water_temperature": {
                "field_name": "Rated Inlet Water Temperature",
                "field_type": "n"
            },
            "rated_inlet_space_temperature": {
                "field_name": "Rated Inlet Space Temperature",
                "field_type": "n"
            },
            "rated_water_mass_flow_rate": {
                "field_name": "Rated Water Mass Flow Rate",
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
            "maximum_chilled_water_flow_rate": {
                "field_name": "Maximum Chilled Water Flow Rate",
                "field_type": "n"
            },
            "control_type": {
                "field_name": "Control Type",
                "field_type": "a"
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
            "water_inlet_node_name",
            "water_outlet_node_name",
            "rated_inlet_water_temperature",
            "rated_inlet_space_temperature",
            "rated_water_mass_flow_rate",
            "cooling_design_capacity_method",
            "cooling_design_capacity",
            "cooling_design_capacity_per_floor_area",
            "fraction_of_autosized_cooling_design_capacity",
            "maximum_chilled_water_flow_rate",
            "control_type",
            "cooling_control_throttling_range",
            "cooling_control_temperature_schedule_name",
            "condensation_control_type",
            "condensation_control_dewpoint_offset",
            "fraction_radiant",
            "fraction_of_radiant_energy_incident_on_people"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "cooling_design_capacity_method",
                "control_type",
                "cooling_control_temperature_schedule_name",
                "condensation_control_type"
            ],
            "extensions": [
                "surface_name"
            ]
        },
        "numerics": {
            "fields": [
                "rated_inlet_water_temperature",
                "rated_inlet_space_temperature",
                "rated_water_mass_flow_rate",
                "cooling_design_capacity",
                "cooling_design_capacity_per_floor_area",
                "fraction_of_autosized_cooling_design_capacity",
                "maximum_chilled_water_flow_rate",
                "cooling_control_throttling_range",
                "condensation_control_dewpoint_offset",
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
    "min_fields": 18.0,
    "extensible_size": 2.0
}
```
