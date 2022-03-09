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
                "air_outlet_node_name": {
                    "type": "string",
                    "note": "The outlet node of the terminal unit. This is also the zone inlet node."
                },
                "outdoor_air_inlet_node_name": {
                    "type": "string"
                },
                "recirculated_air_inlet_node_name": {
                    "type": "string"
                },
                "maximum_terminal_air_flow_rate": {
                    "units": "m3/s",
                    "note": "If autosized this is the sum of flow needed for cooling and maximum required outdoor air",
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
                    "note": "When the name of a DesignSpecification:OutdoorAir object is entered, the terminal unit will increase flow as needed to meet this outdoor air requirement. If Outdoor Air Flow per Person is non-zero, then the outdoor air requirement will be computed based mode selected in the next field. At no time will the supply air flow rate exceed the value for Maximum Air Flow Rate."
                },
                "per_person_ventilation_rate_mode": {
                    "type": "string",
                    "enum": [
                        "CurrentOccupancy",
                        "DesignOccupancy"
                    ],
                    "note": "CurrentOccupancy models demand controlled ventilation using the current number of people DesignOccupancy uses the total Number of People in the zone and is constant"
                }
            },
            "required": [
                "air_outlet_node_name",
                "outdoor_air_inlet_node_name",
                "maximum_terminal_air_flow_rate",
                "design_specification_outdoor_air_object_name"
            ]
        }
    },
    "group": "Zone HVAC Air Loop Terminal Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
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
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "outdoor_air_inlet_node_name": {
                "field_name": "Outdoor Air Inlet Node Name",
                "field_type": "a"
            },
            "recirculated_air_inlet_node_name": {
                "field_name": "Recirculated Air Inlet Node Name",
                "field_type": "a"
            },
            "maximum_terminal_air_flow_rate": {
                "field_name": "Maximum Terminal Air Flow Rate",
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
            "air_outlet_node_name",
            "outdoor_air_inlet_node_name",
            "recirculated_air_inlet_node_name",
            "maximum_terminal_air_flow_rate",
            "design_specification_outdoor_air_object_name",
            "per_person_ventilation_rate_mode"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_outlet_node_name",
                "outdoor_air_inlet_node_name",
                "recirculated_air_inlet_node_name",
                "design_specification_outdoor_air_object_name",
                "per_person_ventilation_rate_mode"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_terminal_air_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Central air system terminal unit, dual duct, variable volume with special controls. One VAV duct is controlled to supply ventilation air and the other VAV duct is controlled to meet the zone cooling load.",
    "min_fields": 7.0
}
```
