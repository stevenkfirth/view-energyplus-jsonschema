```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "reference": [
                        "AirFlowNetworkMultizoneZones"
                    ],
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ],
                    "note": "Enter the zone name where ventilation control is required."
                },
                "ventilation_control_mode": {
                    "type": "string",
                    "enum": [
                        "",
                        "ASHRAE55Adaptive",
                        "CEN15251Adaptive",
                        "Constant",
                        "Enthalpy",
                        "NoVent",
                        "Temperature"
                    ],
                    "default": "NoVent",
                    "note": "When Ventilation Control Mode = Temperature or Enthalpy, the following fields are used to modulate the Ventilation Open Factor for all window and door openings in the zone according to the zone's indoor-outdoor temperature or enthalpy difference. Constant: controlled by field Venting Schedule Name. NoVent: control will not open window or door during simulation (Ventilation Open Factor = 0)."
                },
                "ventilation_control_zone_temperature_setpoint_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Used only if Ventilation Control Mode = Temperature or Enthalpy."
                },
                "minimum_venting_open_factor": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "Used only if Ventilation Control Mode = Temperature or Enthalpy."
                },
                "indoor_and_outdoor_temperature_difference_lower_limit_for_maximum_venting_open_factor": {
                    "type": "number",
                    "units": "deltaC",
                    "minimum": 0.0,
                    "exclusiveMaximum": 100.0,
                    "default": 0.0,
                    "note": "Applicable only if Ventilation Control Mode = Temperature. This value must be less than the corresponding upper value (next field)."
                },
                "indoor_and_outdoor_temperature_difference_upper_limit_for_minimum_venting_open_factor": {
                    "type": "number",
                    "units": "deltaC",
                    "exclusiveMinimum": 0.0,
                    "default": 100.0,
                    "note": "Applicable only if Ventilation Control Mode = Temperature. This value must be greater than the corresponding lower value (previous field)."
                },
                "indoor_and_outdoor_enthalpy_difference_lower_limit_for_maximum_venting_open_factor": {
                    "type": "number",
                    "units": "deltaJ/kg",
                    "minimum": 0.0,
                    "exclusiveMaximum": 300000.0,
                    "default": 0.0,
                    "note": "Applicable only if Ventilation Control Mode = Enthalpy. This value must be less than the corresponding upper value (next field)."
                },
                "indoor_and_outdoor_enthalpy_difference_upper_limit_for_minimum_venting_open_factor": {
                    "type": "number",
                    "units": "deltaJ/kg",
                    "exclusiveMinimum": 0.0,
                    "default": 300000.0,
                    "note": "Applicable only if Ventilation Control Mode = Enthalpy. This value must be greater than the corresponding lower value (previous field)."
                },
                "venting_availability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Non-zero Schedule value means venting is allowed if other venting control conditions are satisfied. A zero (or negative) Schedule value means venting is not allowed under any The Schedule values should be greater than or equal to 0 and less than or equal to 1. circumstances. If this Schedule is not specified then venting is allowed if other venting control conditions are satisfied. Not used if Ventilation Control Mode = NoVent."
                },
                "single_sided_wind_pressure_coefficient_algorithm": {
                    "type": "string",
                    "enum": [
                        "",
                        "Advanced",
                        "Standard"
                    ],
                    "default": "Standard",
                    "note": "Selecting Advanced results in EnergyPlus calculating modified Wind Pressure Coefficients to account for wind direction and turbulence effects on single sided ventilation rates. Model is only valid for zones with 2 openings, both of which are on a single facade."
                },
                "facade_width": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "default": 10.0,
                    "note": "This is the whole building width along the direction of the facade of this zone."
                },
                "occupant_ventilation_control_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AirflowNetworkOccupantVentilationControlNames"
                    ],
                    "note": "Enter the name where Occupancy Ventilation Control is required."
                }
            },
            "required": [
                "zone_name"
            ]
        }
    },
    "group": "AirflowNetwork",
    "legacy_idd": {
        "field_info": {
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "ventilation_control_mode": {
                "field_name": "Ventilation Control Mode",
                "field_type": "a"
            },
            "ventilation_control_zone_temperature_setpoint_schedule_name": {
                "field_name": "Ventilation Control Zone Temperature Setpoint Schedule Name",
                "field_type": "a"
            },
            "minimum_venting_open_factor": {
                "field_name": "Minimum Venting Open Factor",
                "field_type": "n"
            },
            "indoor_and_outdoor_temperature_difference_lower_limit_for_maximum_venting_open_factor": {
                "field_name": "Indoor and Outdoor Temperature Difference Lower Limit For Maximum Venting Open Factor",
                "field_type": "n"
            },
            "indoor_and_outdoor_temperature_difference_upper_limit_for_minimum_venting_open_factor": {
                "field_name": "Indoor and Outdoor Temperature Difference Upper Limit for Minimum Venting Open Factor",
                "field_type": "n"
            },
            "indoor_and_outdoor_enthalpy_difference_lower_limit_for_maximum_venting_open_factor": {
                "field_name": "Indoor and Outdoor Enthalpy Difference Lower Limit For Maximum Venting Open Factor",
                "field_type": "n"
            },
            "indoor_and_outdoor_enthalpy_difference_upper_limit_for_minimum_venting_open_factor": {
                "field_name": "Indoor and Outdoor Enthalpy Difference Upper Limit for Minimum Venting Open Factor",
                "field_type": "n"
            },
            "venting_availability_schedule_name": {
                "field_name": "Venting Availability Schedule Name",
                "field_type": "a"
            },
            "single_sided_wind_pressure_coefficient_algorithm": {
                "field_name": "Single Sided Wind Pressure Coefficient Algorithm",
                "field_type": "a"
            },
            "facade_width": {
                "field_name": "Facade Width",
                "field_type": "n"
            },
            "occupant_ventilation_control_name": {
                "field_name": "Occupant Ventilation Control Name",
                "field_type": "a"
            }
        },
        "fields": [
            "zone_name",
            "ventilation_control_mode",
            "ventilation_control_zone_temperature_setpoint_schedule_name",
            "minimum_venting_open_factor",
            "indoor_and_outdoor_temperature_difference_lower_limit_for_maximum_venting_open_factor",
            "indoor_and_outdoor_temperature_difference_upper_limit_for_minimum_venting_open_factor",
            "indoor_and_outdoor_enthalpy_difference_lower_limit_for_maximum_venting_open_factor",
            "indoor_and_outdoor_enthalpy_difference_upper_limit_for_minimum_venting_open_factor",
            "venting_availability_schedule_name",
            "single_sided_wind_pressure_coefficient_algorithm",
            "facade_width",
            "occupant_ventilation_control_name"
        ],
        "alphas": {
            "fields": [
                "zone_name",
                "ventilation_control_mode",
                "ventilation_control_zone_temperature_setpoint_schedule_name",
                "venting_availability_schedule_name",
                "single_sided_wind_pressure_coefficient_algorithm",
                "occupant_ventilation_control_name"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_venting_open_factor",
                "indoor_and_outdoor_temperature_difference_lower_limit_for_maximum_venting_open_factor",
                "indoor_and_outdoor_temperature_difference_upper_limit_for_minimum_venting_open_factor",
                "indoor_and_outdoor_enthalpy_difference_lower_limit_for_maximum_venting_open_factor",
                "indoor_and_outdoor_enthalpy_difference_upper_limit_for_minimum_venting_open_factor",
                "facade_width"
            ]
        }
    },
    "type": "object",
    "memo": "This object is used to simultaneously control a thermal zone's window and door openings, both exterior and interior.",
    "min_fields": 8.0
}
```
