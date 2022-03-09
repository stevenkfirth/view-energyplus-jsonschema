```
{
    "ZoneControl:ContaminantController": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "carbon_dioxide_control_availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for CO2 controller. Schedule value > 0 means the CO2 controller is enabled. If this field is blank, then CO2 controller is always enabled.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "carbon_dioxide_setpoint_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values should be carbon dioxide concentration in parts per million (ppm)"
                    },
                    "minimum_carbon_dioxide_concentration_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values should be carbon dioxide concentration in parts per million (ppm) This field is used when the field System Outdoor Air Method = ProportionalControlBasedOnOccupancySchedule or ProportionalControlBasedOnDesignOccupancy, or ProportionalControlBasedOnDesignOARate in Controller:MechanicalVentilation"
                    },
                    "maximum_carbon_dioxide_concentration_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values should be carbon dioxide concentration in parts per million (ppm) This field is used when the field System Outdoor Air Method = ProportionalControlBasedOnOccupancySchedule or ProportionalControlBasedOnDesignOccupancy or ProportionalControlBasedOnDesignOARate."
                    },
                    "generic_contaminant_control_availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for generic contaminant controller. Schedule value > 0 means the generic contaminant controller is enabled. If this field is blank, then generic contaminant controller is always enabled.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "generic_contaminant_setpoint_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values should be generic contaminant concentration in parts per million (ppm) This field is used when the field System Outdoor Air Method = IndoorAirQualityProcedureGenericContaminant in Controller:MechanicalVentilation"
                    }
                },
                "required": [
                    "zone_name"
                ]
            }
        },
        "group": "Zone HVAC Controls and Thermostats",
        "name": {
            "type": "string",
            "is_required": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "carbon_dioxide_control_availability_schedule_name": {
                    "field_name": "Carbon Dioxide Control Availability Schedule Name",
                    "field_type": "a"
                },
                "carbon_dioxide_setpoint_schedule_name": {
                    "field_name": "Carbon Dioxide Setpoint Schedule Name",
                    "field_type": "a"
                },
                "minimum_carbon_dioxide_concentration_schedule_name": {
                    "field_name": "Minimum Carbon Dioxide Concentration Schedule Name",
                    "field_type": "a"
                },
                "maximum_carbon_dioxide_concentration_schedule_name": {
                    "field_name": "Maximum Carbon Dioxide Concentration Schedule Name",
                    "field_type": "a"
                },
                "generic_contaminant_control_availability_schedule_name": {
                    "field_name": "Generic Contaminant Control Availability Schedule Name",
                    "field_type": "a"
                },
                "generic_contaminant_setpoint_schedule_name": {
                    "field_name": "Generic Contaminant Setpoint Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "carbon_dioxide_control_availability_schedule_name",
                "carbon_dioxide_setpoint_schedule_name",
                "minimum_carbon_dioxide_concentration_schedule_name",
                "maximum_carbon_dioxide_concentration_schedule_name",
                "generic_contaminant_control_availability_schedule_name",
                "generic_contaminant_setpoint_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "carbon_dioxide_control_availability_schedule_name",
                    "carbon_dioxide_setpoint_schedule_name",
                    "minimum_carbon_dioxide_concentration_schedule_name",
                    "maximum_carbon_dioxide_concentration_schedule_name",
                    "generic_contaminant_control_availability_schedule_name",
                    "generic_contaminant_setpoint_schedule_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Used to control a zone to a specified indoor level of CO2 or generic contaminants, or to specify minimum CO2 concentration schedule name for a zone.",
        "min_fields": 4.0
    }
}
```
