```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_or_zonelist_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneAndZoneListNames"
                    ]
                },
                "schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "design_flow_rate_calculation_method": {
                    "type": "string",
                    "note": "The entered calculation method is used to create the maximum amount of infiltration for this set of attributes Choices: Flow/Zone => Design Flow Rate -- simply enter Design Flow Rate Flow/Area => Flow per Zone Floor Area - Value * Floor Area (zone) = Design Flow Rate Flow/ExteriorArea => Flow per Exterior Surface Area - Value * Exterior Surface Area (zone) = Design Flow Rate Flow/ExteriorWallArea => Flow per Exterior Surface Area - Value * Exterior Wall Surface Area (zone) = Design Flow Rate AirChanges/Hour => Air Changes per Hour - Value * Floor Volume (zone) adjusted for m3/s = Design Volume Flow Rate \"Idesign\" in Equation is the result.",
                    "enum": [
                        "",
                        "AirChanges/Hour",
                        "Flow/Area",
                        "Flow/ExteriorArea",
                        "Flow/ExteriorWallArea",
                        "Flow/Zone"
                    ],
                    "default": "Flow/Zone"
                },
                "design_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0,
                    "ip-units": "ft3/min"
                },
                "flow_per_zone_floor_area": {
                    "type": "number",
                    "minimum": 0.0,
                    "units": "m3/s-m2"
                },
                "flow_per_exterior_surface_area": {
                    "type": "number",
                    "note": "use key Flow/ExteriorArea for all exterior surface area use key Flow/ExteriorWallArea to include only exterior wall area",
                    "units": "m3/s-m2",
                    "minimum": 0.0
                },
                "air_changes_per_hour": {
                    "type": "number",
                    "units": "1/hr",
                    "minimum": 0.0
                },
                "constant_term_coefficient": {
                    "type": "number",
                    "note": "\"A\" in Equation",
                    "default": 1.0
                },
                "temperature_term_coefficient": {
                    "type": "number",
                    "note": "\"B\" in Equation",
                    "default": 0.0
                },
                "velocity_term_coefficient": {
                    "type": "number",
                    "note": "\"C\" in Equation",
                    "default": 0.0
                },
                "velocity_squared_term_coefficient": {
                    "type": "number",
                    "note": "\"D\" in Equation",
                    "default": 0.0
                }
            },
            "required": [
                "zone_or_zonelist_name",
                "schedule_name"
            ]
        }
    },
    "group": "Zone Airflow",
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
            "zone_or_zonelist_name": {
                "field_name": "Zone or ZoneList Name",
                "field_type": "a"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "design_flow_rate_calculation_method": {
                "field_name": "Design Flow Rate Calculation Method",
                "field_type": "a"
            },
            "design_flow_rate": {
                "field_name": "Design Flow Rate",
                "field_type": "n"
            },
            "flow_per_zone_floor_area": {
                "field_name": "Flow per Zone Floor Area",
                "field_type": "n"
            },
            "flow_per_exterior_surface_area": {
                "field_name": "Flow per Exterior Surface Area",
                "field_type": "n"
            },
            "air_changes_per_hour": {
                "field_name": "Air Changes per Hour",
                "field_type": "n"
            },
            "constant_term_coefficient": {
                "field_name": "Constant Term Coefficient",
                "field_type": "n"
            },
            "temperature_term_coefficient": {
                "field_name": "Temperature Term Coefficient",
                "field_type": "n"
            },
            "velocity_term_coefficient": {
                "field_name": "Velocity Term Coefficient",
                "field_type": "n"
            },
            "velocity_squared_term_coefficient": {
                "field_name": "Velocity Squared Term Coefficient",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "zone_or_zonelist_name",
            "schedule_name",
            "design_flow_rate_calculation_method",
            "design_flow_rate",
            "flow_per_zone_floor_area",
            "flow_per_exterior_surface_area",
            "air_changes_per_hour",
            "constant_term_coefficient",
            "temperature_term_coefficient",
            "velocity_term_coefficient",
            "velocity_squared_term_coefficient"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_or_zonelist_name",
                "schedule_name",
                "design_flow_rate_calculation_method"
            ]
        },
        "numerics": {
            "fields": [
                "design_flow_rate",
                "flow_per_zone_floor_area",
                "flow_per_exterior_surface_area",
                "air_changes_per_hour",
                "constant_term_coefficient",
                "temperature_term_coefficient",
                "velocity_term_coefficient",
                "velocity_squared_term_coefficient"
            ]
        }
    },
    "type": "object",
    "memo": "Infiltration is specified as a design level which is modified by a Schedule fraction, temperature difference and wind speed: Infiltration=Idesign * FSchedule * (A + B*|(Tzone-Todb)| + C*WindSpd + D * WindSpd**2) If you use a ZoneList in the Zone or ZoneList name field then this definition applies to all the zones in the ZoneList.",
    "min_fields": 12.0
}
```
