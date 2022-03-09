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
                "hot_air_inlet_node_name": {
                    "type": "string"
                },
                "cold_air_inlet_node_name": {
                    "type": "string"
                },
                "maximum_damper_air_flow_rate": {
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
                "zone_minimum_air_flow_fraction": {
                    "type": "number",
                    "note": "fraction of maximum air flow",
                    "maximum": 1.0,
                    "minimum": 0.0,
                    "default": 0.2
                },
                "design_specification_outdoor_air_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DSOASpaceListNames",
                        "DesignSpecificationOutdoorAirNames"
                    ],
                    "note": "When the name of a DesignSpecification:OutdoorAir object is entered, the terminal unit will increase flow as needed to meet this outdoor air requirement. If Outdoor Air Flow per Person is non-zero, then the outdoor air requirement will be computed based on the current number of occupants in the zone. At no time will the supply air flow rate exceed the value for Maximum Air Flow Rate. If this field is blank, then the terminal unit will not be controlled for outdoor air flow."
                },
                "minimum_air_flow_turndown_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This field adjusts the design minimum flow rate by multiplying it using this schedule of fraction values. This field is used with \"Zone Minimum Air Flow Fraction\". Schedule values are fractions 0.0 to 1.0. This field adjusts the minimum airflow turndown below the design minimum air flow and is intended for use with ASHRAE Standard 170. If this field is left blank, then the turndown minimum air flow fraction value is set to 1 and the VAV air terminal uses fixed fraction specified in the field \"Zone Minimum Air Flow Fraction\"."
                }
            },
            "required": [
                "air_outlet_node_name",
                "hot_air_inlet_node_name",
                "cold_air_inlet_node_name",
                "maximum_damper_air_flow_rate"
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
            "hot_air_inlet_node_name": {
                "field_name": "Hot Air Inlet Node Name",
                "field_type": "a"
            },
            "cold_air_inlet_node_name": {
                "field_name": "Cold Air Inlet Node Name",
                "field_type": "a"
            },
            "maximum_damper_air_flow_rate": {
                "field_name": "Maximum Damper Air Flow Rate",
                "field_type": "n"
            },
            "zone_minimum_air_flow_fraction": {
                "field_name": "Zone Minimum Air Flow Fraction",
                "field_type": "n"
            },
            "design_specification_outdoor_air_object_name": {
                "field_name": "Design Specification Outdoor Air Object Name",
                "field_type": "a"
            },
            "minimum_air_flow_turndown_schedule_name": {
                "field_name": "Minimum Air Flow Turndown Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "air_outlet_node_name",
            "hot_air_inlet_node_name",
            "cold_air_inlet_node_name",
            "maximum_damper_air_flow_rate",
            "zone_minimum_air_flow_fraction",
            "design_specification_outdoor_air_object_name",
            "minimum_air_flow_turndown_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_outlet_node_name",
                "hot_air_inlet_node_name",
                "cold_air_inlet_node_name",
                "design_specification_outdoor_air_object_name",
                "minimum_air_flow_turndown_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_damper_air_flow_rate",
                "zone_minimum_air_flow_fraction"
            ]
        }
    },
    "type": "object",
    "memo": "Central air system terminal unit, dual duct, variable volume.",
    "min_fields": 7.0
}
```
