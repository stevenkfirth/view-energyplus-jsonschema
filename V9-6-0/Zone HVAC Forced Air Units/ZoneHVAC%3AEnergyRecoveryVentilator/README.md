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
                "heat_exchanger_name": {
                    "type": "string",
                    "note": "Heat exchanger type must be HeatExchanger:AirToAir:SensibleAndLatent",
                    "data_type": "object_list",
                    "object_list": [
                        "HXAirToAirSensibleAndLatentNames"
                    ]
                },
                "supply_air_flow_rate": {
                    "units": "m3/s",
                    "note": "This flow rate must match the supply fan's air flow rate.",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "exhaust_air_flow_rate": {
                    "units": "m3/s",
                    "note": "This flow rate must match the supply fan air flow rate.",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "supply_air_fan_name": {
                    "type": "string",
                    "note": "Fan type must be Fan:OnOff or Fan:SystemModel",
                    "data_type": "object_list",
                    "object_list": [
                        "FansOnOff",
                        "FansSystemModel"
                    ]
                },
                "exhaust_air_fan_name": {
                    "type": "string",
                    "note": "Fan type must be Fan:OnOff or Fan:SystemModel",
                    "data_type": "object_list",
                    "object_list": [
                        "FansOnOff",
                        "FansSystemModel"
                    ]
                },
                "controller_name": {
                    "type": "string",
                    "note": "Enter the name of a ZoneHVAC:EnergyRecoveryVentilator:Controller object.",
                    "data_type": "object_list",
                    "object_list": [
                        "ControllerStandAloneEnergyRecoveryVentilator"
                    ]
                },
                "ventilation_rate_per_unit_floor_area": {
                    "type": "number",
                    "units": "m3/s-m2",
                    "minimum": 0.0,
                    "note": "0.000508 m3/s-m2 corresponds to 0.1 ft3/min-ft2 Used only when supply and exhaust air flow rates are autosized."
                },
                "ventilation_rate_per_occupant": {
                    "type": "number",
                    "units": "m3/s-person",
                    "minimum": 0.0,
                    "note": "0.00236 m3/s-person corresponds to 5 ft3/min-person Used only when supply and exhaust air flow rates are autosized."
                },
                "availability_manager_list_name": {
                    "type": "string",
                    "note": "Enter the name of an AvailabilityManagerAssignmentList object.",
                    "data_type": "object_list",
                    "object_list": [
                        "SystemAvailabilityManagerLists"
                    ]
                }
            },
            "required": [
                "heat_exchanger_name",
                "supply_air_flow_rate",
                "exhaust_air_flow_rate",
                "supply_air_fan_name",
                "exhaust_air_fan_name"
            ]
        }
    },
    "group": "Zone HVAC Forced Air Units",
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
            "heat_exchanger_name": {
                "field_name": "Heat Exchanger Name",
                "field_type": "a"
            },
            "supply_air_flow_rate": {
                "field_name": "Supply Air Flow Rate",
                "field_type": "n"
            },
            "exhaust_air_flow_rate": {
                "field_name": "Exhaust Air Flow Rate",
                "field_type": "n"
            },
            "supply_air_fan_name": {
                "field_name": "Supply Air Fan Name",
                "field_type": "a"
            },
            "exhaust_air_fan_name": {
                "field_name": "Exhaust Air Fan Name",
                "field_type": "a"
            },
            "controller_name": {
                "field_name": "Controller Name",
                "field_type": "a"
            },
            "ventilation_rate_per_unit_floor_area": {
                "field_name": "Ventilation Rate per Unit Floor Area",
                "field_type": "n"
            },
            "ventilation_rate_per_occupant": {
                "field_name": "Ventilation Rate per Occupant",
                "field_type": "n"
            },
            "availability_manager_list_name": {
                "field_name": "Availability Manager List Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "heat_exchanger_name",
            "supply_air_flow_rate",
            "exhaust_air_flow_rate",
            "supply_air_fan_name",
            "exhaust_air_fan_name",
            "controller_name",
            "ventilation_rate_per_unit_floor_area",
            "ventilation_rate_per_occupant",
            "availability_manager_list_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "heat_exchanger_name",
                "supply_air_fan_name",
                "exhaust_air_fan_name",
                "controller_name",
                "availability_manager_list_name"
            ]
        },
        "numerics": {
            "fields": [
                "supply_air_flow_rate",
                "exhaust_air_flow_rate",
                "ventilation_rate_per_unit_floor_area",
                "ventilation_rate_per_occupant"
            ]
        }
    },
    "type": "object",
    "memo": "This compound component models a stand-alone energy recovery ventilator (ERV) that conditions outdoor ventilation air and supplies that air directly to a zone. The ERV unit is modeled as a collection of components: air-to-air heat exchanger, supply air fan, exhaust air fan and an optional controller to avoid overheating of the supply air (economizer or free cooling operation).",
    "min_fields": 7.0
}
```
