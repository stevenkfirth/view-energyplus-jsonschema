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
                "air_inlet_node_name": {
                    "type": "string",
                    "note": "The air-inlet node name that connects the air splitter to the individual zone air distribution unit. This node should also be one of the outlet air node of an AirLoopHVAC:ZoneSplitter or AirLoopHVAC:SupplyPlenum component."
                },
                "air_outlet_node_name": {
                    "type": "string",
                    "note": "This is an air outlet node from the air distribution unit. This node name should be one of the supply air inlet node names of a zone served by this component."
                },
                "maximum_air_flow_rate": {
                    "units": "m3/s",
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
                "design_specification_outdoor_air_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DSOASpaceListNames",
                        "DesignSpecificationOutdoorAirNames"
                    ],
                    "note": "This field is used to modulate the terminal unit flow rate based on the specified outdoor air requirement. When the name of a DesignSpecification:OutdoorAir object is entered, the terminal unit will adjust flow to meet this outdoor air requirement and no more. There is no control for zone load. If Outdoor Air Flow per Person is non-zero, then the outdoor air requirement will be computed based on either the current or design occupancy as specified in the Per Person Ventilation Rate Mode field. At no time will the supply air flow rate exceed the value for Maximum Air Flow Rate. The requested flow rate may not be fully met if the system is operating with cycling fan. If this field is blank, then the terminal unit will not be controlled for outdoor air flow. This field is optional."
                },
                "per_person_ventilation_rate_mode": {
                    "type": "string",
                    "enum": [
                        "",
                        "CurrentOccupancy",
                        "DesignOccupancy"
                    ],
                    "default": "CurrentOccupancy",
                    "note": "CurrentOccupancy uses current number of people in the zone which may vary DesignOccupancy uses the total number of people in the zone and is constant"
                }
            },
            "required": [
                "air_inlet_node_name",
                "air_outlet_node_name",
                "maximum_air_flow_rate"
            ]
        }
    },
    "group": "Zone HVAC Air Loop Terminal Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AFNTerminalUnitNames",
            "AirTerminalUnitNames"
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
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "maximum_air_flow_rate": {
                "field_name": "Maximum Air Flow Rate",
                "field_type": "n"
            },
            "design_specification_outdoor_air_object_name": {
                "field_name": "Design Specification Outdoor Air Object Name",
                "field_type": "a"
            },
            "per_person_ventilation_rate_mode": {
                "field_name": "Per Person Ventilation Rate Mode",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "maximum_air_flow_rate",
            "design_specification_outdoor_air_object_name",
            "per_person_ventilation_rate_mode"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "design_specification_outdoor_air_object_name",
                "per_person_ventilation_rate_mode"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_air_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Central air system terminal unit, single duct, constant volume, without reheat coil",
    "min_fields": 5.0
}
```
