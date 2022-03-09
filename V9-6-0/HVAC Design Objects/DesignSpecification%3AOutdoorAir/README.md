```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "outdoor_air_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "AirChanges/Hour",
                        "Flow/Area",
                        "Flow/Person",
                        "Flow/Zone",
                        "IndoorAirQualityProcedure",
                        "Maximum",
                        "ProportionalControlBasedOnDesignOccupancy",
                        "ProportionalControlBasedOnOccupancySchedule",
                        "Sum"
                    ],
                    "default": "Flow/Person",
                    "note": "Flow/Person => Outdoor Air Flow per Person * Occupancy = Design Flow Rate, Flow/Area => Outdoor Air Flow per Zone Floor Area * Zone Floor Area = Design Flow Rate, Flow/Zone => Outdoor Air Flow per Zone = Design Flow Rate, AirChanges/Hour => Outdoor Air Flow Air Changes per Hour * Zone Volume adjusted for m3/s = Design Flow Rate"
                },
                "outdoor_air_flow_per_person": {
                    "type": "number",
                    "units": "m3/s-person",
                    "default": 0.00944,
                    "minimum": 0.0,
                    "note": "0.00944 m3/s is equivalent to 20 cfm per person This input is only used if the field Outdoor Air Method is Flow/Person, Sum, or Maximum For sizing, the design number of occupants is used. For outdoor air flow control, the use of design occupants or current occupants depends on the component and DCV options. AirTerminal:SingleDuct:VAV:NoReheat, AirTerminal:SingleDuct:VAV:Reheat use the DCV flag specified in Controller:MechanicalVentilation AirTerminal:DualDuct:VAV:OutdoorAir and ZoneHVAC:IdealLoadsAirSystem have their own DCV control input. ZoneHVAC:FourPipeFanCoil always uses current occupants."
                },
                "outdoor_air_flow_per_zone_floor_area": {
                    "type": "number",
                    "units": "m3/s-m2",
                    "default": 0.0,
                    "minimum": 0.0,
                    "note": "This input is only used if the field Outdoor Air Method is Flow/Area, Sum, or Maximum"
                },
                "outdoor_air_flow_per_zone": {
                    "type": "number",
                    "units": "m3/s",
                    "default": 0.0,
                    "minimum": 0.0,
                    "note": "This input is only used if the field Outdoor Air Method is Flow/Zone, Sum, or Maximum"
                },
                "outdoor_air_flow_air_changes_per_hour": {
                    "type": "number",
                    "units": "1/hr",
                    "default": 0.0,
                    "minimum": 0.0,
                    "note": "This input is only used if the field Outdoor Air Method is AirChanges/Hour, Sum, or Maximum"
                },
                "outdoor_air_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Schedule values are multiplied by the Outdoor Air Flow rate calculated using the previous four inputs. Schedule values are limited to 0 to 1. If left blank, the schedule defaults to 1.0. This schedule is ignored during sizing. All other components which reference this design specification use the current schedule value to calculate the current outdoor air requirement. This includes AirTerminal:SingleDuct:VAV:NoReheat, AirTerminal:SingleDuct:VAV:Reheat, AirTerminal:DualDuct:VAV:OutdoorAir, ZoneHVAC:FourPipeFanCoil, and ZoneHVAC:IdealLoadsAirSystem. This schedule will also be applied by Controller:MechanicalVentilation for all System Outdoor Air Methods."
                },
                "proportional_control_minimum_outdoor_air_flow_rate_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This input is only used to calculate the minimum outdoor air flow rate when the field System Outdoor Air Method = ProportionalControlBasedOnDesignOARate in Controller:MechanicalVentilation."
                }
            }
        }
    },
    "group": "HVAC Design Objects",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DesignSpecificationOutdoorAirNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "outdoor_air_method": {
                "field_name": "Outdoor Air Method",
                "field_type": "a"
            },
            "outdoor_air_flow_per_person": {
                "field_name": "Outdoor Air Flow per Person",
                "field_type": "n"
            },
            "outdoor_air_flow_per_zone_floor_area": {
                "field_name": "Outdoor Air Flow per Zone Floor Area",
                "field_type": "n"
            },
            "outdoor_air_flow_per_zone": {
                "field_name": "Outdoor Air Flow per Zone",
                "field_type": "n"
            },
            "outdoor_air_flow_air_changes_per_hour": {
                "field_name": "Outdoor Air Flow Air Changes per Hour",
                "field_type": "n"
            },
            "outdoor_air_schedule_name": {
                "field_name": "Outdoor Air Schedule Name",
                "field_type": "a"
            },
            "proportional_control_minimum_outdoor_air_flow_rate_schedule_name": {
                "field_name": "Proportional Control Minimum Outdoor Air Flow Rate Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "outdoor_air_method",
            "outdoor_air_flow_per_person",
            "outdoor_air_flow_per_zone_floor_area",
            "outdoor_air_flow_per_zone",
            "outdoor_air_flow_air_changes_per_hour",
            "outdoor_air_schedule_name",
            "proportional_control_minimum_outdoor_air_flow_rate_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "outdoor_air_method",
                "outdoor_air_schedule_name",
                "proportional_control_minimum_outdoor_air_flow_rate_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "outdoor_air_flow_per_person",
                "outdoor_air_flow_per_zone_floor_area",
                "outdoor_air_flow_per_zone",
                "outdoor_air_flow_air_changes_per_hour"
            ]
        }
    },
    "type": "object",
    "memo": "This object is used to describe general outdoor air requirements which are referenced by other objects.",
    "min_fields": 1.0
}
```
