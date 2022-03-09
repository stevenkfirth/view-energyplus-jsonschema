```
{
    "HVACTemplate:Zone:BaseboardHeat": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "note": "Zone name must match a building zone name",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "template_thermostat_name": {
                        "type": "string",
                        "note": "Enter the name of a HVACTemplate:Thermostat object. If blank, then it is assumed that standard thermostat objects have been defined for this zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "CompactHVACThermostats"
                        ]
                    },
                    "zone_heating_sizing_factor": {
                        "type": "number",
                        "note": "If blank, value from Sizing:Parameters will be used.",
                        "minimum": 0.0
                    },
                    "baseboard_heating_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Electric",
                            "HotWater"
                        ],
                        "default": "HotWater"
                    },
                    "baseboard_heating_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "baseboard_heating_capacity": {
                        "default": "Autosize",
                        "units": "W",
                        "anyOf": [
                            {
                                "type": "number"
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
                    "dedicated_outdoor_air_system_name": {
                        "type": "string",
                        "note": "Enter the name of an HVACTemplate:System:DedicatedOutdoorAir object if this zone is served by a separate dedicated outdoor air system (DOAS). Leave field blank if no DOAS serves this zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "HVACTemplateDOASSystems"
                        ]
                    },
                    "outdoor_air_method": {
                        "type": "string",
                        "note": "Flow/Person, Flow/Zone, Flow/Area, Sum, and Maximum use the values in the next three fields: Outdoor Air Flow Rate per Person, Outdoor Air Flow Rate per Zone Floor Area, and Outdoor Air Flow Rate per Zone. DetailedSpecification ignores these three Outdoor Air Flow Rate fields and instead references design specification objects named in the fields Design Specification Outdoor Air Object Name and Design Specification Zone Air Distribution Object Name.",
                        "enum": [
                            "",
                            "DetailedSpecification",
                            "Flow/Area",
                            "Flow/Person",
                            "Flow/Zone",
                            "Maximum",
                            "Sum"
                        ],
                        "default": "Flow/Person"
                    },
                    "outdoor_air_flow_rate_per_person": {
                        "type": "number",
                        "units": "m3/s",
                        "note": "Default 0.00944 is 20 cfm per person This input is used if the field Outdoor Air Method is Flow/Person, Sum, or Maximum",
                        "default": 0.00944
                    },
                    "outdoor_air_flow_rate_per_zone_floor_area": {
                        "type": "number",
                        "units": "m3/s-m2",
                        "default": 0.0,
                        "note": "This input is used if the field Outdoor Air Method is Flow/Area, Sum, or Maximum"
                    },
                    "outdoor_air_flow_rate_per_zone": {
                        "type": "number",
                        "units": "m3/s",
                        "default": 0.0,
                        "note": "This input is used if the field Outdoor Air Method is Flow/Zone, Sum, or Maximum"
                    },
                    "design_specification_outdoor_air_object_name": {
                        "type": "string",
                        "note": "This field is used only when Outdoor Air Method=DetailedSpecification.",
                        "data_type": "object_list",
                        "object_list": [
                            "DSOASpaceListNames",
                            "DesignSpecificationOutdoorAirNames"
                        ]
                    },
                    "design_specification_zone_air_distribution_object_name": {
                        "type": "string",
                        "note": "This field is used only when Outdoor Air Method=DetailedSpecification.",
                        "data_type": "object_list",
                        "object_list": [
                            "DesignSpecificationZoneAirDistributionNames"
                        ]
                    }
                },
                "required": [
                    "zone_name"
                ]
            }
        },
        "group": "HVAC Templates",
        "legacy_idd": {
            "field_info": {
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "template_thermostat_name": {
                    "field_name": "Template Thermostat Name",
                    "field_type": "a"
                },
                "zone_heating_sizing_factor": {
                    "field_name": "Zone Heating Sizing Factor",
                    "field_type": "n"
                },
                "baseboard_heating_type": {
                    "field_name": "Baseboard Heating Type",
                    "field_type": "a"
                },
                "baseboard_heating_availability_schedule_name": {
                    "field_name": "Baseboard Heating Availability Schedule Name",
                    "field_type": "a"
                },
                "baseboard_heating_capacity": {
                    "field_name": "Baseboard Heating Capacity",
                    "field_type": "n"
                },
                "dedicated_outdoor_air_system_name": {
                    "field_name": "Dedicated Outdoor Air System Name",
                    "field_type": "a"
                },
                "outdoor_air_method": {
                    "field_name": "Outdoor Air Method",
                    "field_type": "a"
                },
                "outdoor_air_flow_rate_per_person": {
                    "field_name": "Outdoor Air Flow Rate per Person",
                    "field_type": "n"
                },
                "outdoor_air_flow_rate_per_zone_floor_area": {
                    "field_name": "Outdoor Air Flow Rate per Zone Floor Area",
                    "field_type": "n"
                },
                "outdoor_air_flow_rate_per_zone": {
                    "field_name": "Outdoor Air Flow Rate per Zone",
                    "field_type": "n"
                },
                "design_specification_outdoor_air_object_name": {
                    "field_name": "Design Specification Outdoor Air Object name",
                    "field_type": "a"
                },
                "design_specification_zone_air_distribution_object_name": {
                    "field_name": "Design Specification Zone Air Distribution Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "zone_name",
                "template_thermostat_name",
                "zone_heating_sizing_factor",
                "baseboard_heating_type",
                "baseboard_heating_availability_schedule_name",
                "baseboard_heating_capacity",
                "dedicated_outdoor_air_system_name",
                "outdoor_air_method",
                "outdoor_air_flow_rate_per_person",
                "outdoor_air_flow_rate_per_zone_floor_area",
                "outdoor_air_flow_rate_per_zone",
                "design_specification_outdoor_air_object_name",
                "design_specification_zone_air_distribution_object_name"
            ],
            "alphas": {
                "fields": [
                    "zone_name",
                    "template_thermostat_name",
                    "baseboard_heating_type",
                    "baseboard_heating_availability_schedule_name",
                    "dedicated_outdoor_air_system_name",
                    "outdoor_air_method",
                    "design_specification_outdoor_air_object_name",
                    "design_specification_zone_air_distribution_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "zone_heating_sizing_factor",
                    "baseboard_heating_capacity",
                    "outdoor_air_flow_rate_per_person",
                    "outdoor_air_flow_rate_per_zone_floor_area",
                    "outdoor_air_flow_rate_per_zone"
                ]
            }
        },
        "type": "object",
        "memo": "Zone baseboard heating system.",
        "min_fields": 11.0
    }
}
```
