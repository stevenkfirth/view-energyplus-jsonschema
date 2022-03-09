```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "applicability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "fan_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "CycleOnAny",
                        "CycleOnAnyCoolingOrHeatingZone",
                        "CycleOnAnyCoolingZone",
                        "CycleOnAnyHeatingZone",
                        "CycleOnAnyHeatingZoneFansOnly",
                        "CycleOnAnyZoneFansOnly",
                        "CycleOnControlZone",
                        "StayOff"
                    ],
                    "default": "StayOff",
                    "note": "When AvailabilityManager:NightCycle is used in the zone component availability manager assignment list, the key choices for Control Type would only be StayOff and CycleOnControlZone"
                },
                "thermostat_tolerance": {
                    "type": "number",
                    "default": 1.0,
                    "units": "deltaC"
                },
                "cycling_run_time_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "FixedRunTime",
                        "Thermostat",
                        "ThermostatWithMinimumRunTime"
                    ],
                    "default": "FixedRunTime"
                },
                "cycling_run_time": {
                    "type": "number",
                    "default": 3600.0,
                    "units": "s"
                },
                "control_zone_or_zone_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneAndZoneListNames"
                    ],
                    "note": "When AvailabilityManager:NightCycle is used in the zone component availability manager assignment list, the Control Zone Name should be the name of the zone in which the zone component is."
                },
                "cooling_control_zone_or_zone_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneAndZoneListNames"
                    ]
                },
                "heating_control_zone_or_zone_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneAndZoneListNames"
                    ]
                },
                "heating_zone_fans_only_zone_or_zone_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneAndZoneListNames"
                    ]
                }
            },
            "required": [
                "applicability_schedule_name",
                "fan_schedule_name"
            ]
        }
    },
    "group": "System Availability Managers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "SystemAvailabilityManagers"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "applicability_schedule_name": {
                "field_name": "Applicability Schedule Name",
                "field_type": "a"
            },
            "fan_schedule_name": {
                "field_name": "Fan Schedule Name",
                "field_type": "a"
            },
            "control_type": {
                "field_name": "Control Type",
                "field_type": "a"
            },
            "thermostat_tolerance": {
                "field_name": "Thermostat Tolerance",
                "field_type": "n"
            },
            "cycling_run_time_control_type": {
                "field_name": "Cycling Run Time Control Type",
                "field_type": "a"
            },
            "cycling_run_time": {
                "field_name": "Cycling Run Time",
                "field_type": "n"
            },
            "control_zone_or_zone_list_name": {
                "field_name": "Control Zone or Zone List Name",
                "field_type": "a"
            },
            "cooling_control_zone_or_zone_list_name": {
                "field_name": "Cooling Control Zone or Zone List Name",
                "field_type": "a"
            },
            "heating_control_zone_or_zone_list_name": {
                "field_name": "Heating Control Zone or Zone List Name",
                "field_type": "a"
            },
            "heating_zone_fans_only_zone_or_zone_list_name": {
                "field_name": "Heating Zone Fans Only Zone or Zone List Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "applicability_schedule_name",
            "fan_schedule_name",
            "control_type",
            "thermostat_tolerance",
            "cycling_run_time_control_type",
            "cycling_run_time",
            "control_zone_or_zone_list_name",
            "cooling_control_zone_or_zone_list_name",
            "heating_control_zone_or_zone_list_name",
            "heating_zone_fans_only_zone_or_zone_list_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "applicability_schedule_name",
                "fan_schedule_name",
                "control_type",
                "cycling_run_time_control_type",
                "control_zone_or_zone_list_name",
                "cooling_control_zone_or_zone_list_name",
                "heating_control_zone_or_zone_list_name",
                "heating_zone_fans_only_zone_or_zone_list_name"
            ]
        },
        "numerics": {
            "fields": [
                "thermostat_tolerance",
                "cycling_run_time"
            ]
        }
    },
    "type": "object",
    "memo": "Determines the availability of a loop or system: whether it is on or off. Depending on zone temperatures, overrides Schedules and forces system Fans on.",
    "min_fields": 6.0
}
```
