```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfAndSubSurfNames"
                    ],
                    "note": "Enter the name of a heat transfer surface."
                },
                "leakage_component_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfaceAirflowLeakageNames"
                    ],
                    "note": "Enter the name of an Airflow Network leakage component. A leakage component is one of the following AirflowNetwork:Multizone objects: AirflowNetwork:MultiZone:Component:DetailedOpening, AirflowNetwork:MultiZone:Component:SimpleOpening, AirflowNetwork:MultiZone:Surface:Crack, AirflowNetwork:MultiZone:Surface:EffectiveLeakageArea, AirflowNetwork:MultiZone:Component:HorizontalOpening, or AirflowNetwork:MultiZone:Component:ZoneExhaustFan. When the zone exhaust fan name is entered, any surface control fields below A3 are ignored when the zone exhaust fan turns on."
                },
                "external_node_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ExternalNodeNames",
                        "OutdoorAirNodeNames"
                    ],
                    "note": "Used if Wind Pressure Coefficient Type = Input in the AirflowNetwork:SimulationControl object, otherwise this field may be left blank."
                },
                "window_door_opening_factor_or_crack_factor": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0,
                    "note": "This field specifies a multiplier for a crack, window, or door."
                },
                "ventilation_control_mode": {
                    "type": "string",
                    "enum": [
                        "",
                        "ASHRAE55Adaptive",
                        "AdjacentEnthalpy",
                        "AdjacentTemperature",
                        "CEN15251Adaptive",
                        "Constant",
                        "Enthalpy",
                        "NoVent",
                        "Temperature",
                        "ZoneLevel"
                    ],
                    "default": "ZoneLevel",
                    "note": "When Ventilation Control Mode = Temperature or Enthalpy, the following fields are used to modulate the Ventilation Open Factor for a window or door opening according to the parent zone's indoor-outdoor temperature or enthalpy difference. When Ventilation Control Mode = AdjacentTemperature or AdjacentEnthalpy, the following fields are used to modulate the Ventilation Open Factor for an interior window or door opening according to temperature or enthalpy difference between the parent zone and the adjacent zone. Constant: controlled by field Venting Schedule Name. NoVent: control will not open window or door during simulation (Ventilation Open Factor = 0). ZoneLevel: control will be controlled by AirflowNetwork:MultiZone:Zone Mode."
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
                    "note": "Applicable only if Ventilation Control Mode = Temperature",
                    "units": "deltaC",
                    "minimum": 0.0,
                    "exclusiveMaximum": 100.0,
                    "default": 0.0
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
                    "note": "Non-zero schedule value means venting is allowed if other venting control conditions are satisfied. A zero (or negative) schedule value means venting is not allowed under any circumstances. The schedule values should be greater than or equal to 0 and less than or equal to 1. If this schedule is not specified then venting is allowed if other venting control conditions are satisfied. Not used if Ventilation Control Mode = NoVent or ZoneLevel."
                },
                "occupant_ventilation_control_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AirflowNetworkOccupantVentilationControlNames"
                    ],
                    "note": "Enter the name where Occupancy Ventilation Control is required."
                },
                "equivalent_rectangle_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "BaseSurfaceAspectRatio",
                        "PolygonHeight",
                        "UserDefinedAspectRatio"
                    ],
                    "default": "PolygonHeight",
                    "note": "This field is applied to a non-rectangular window or door. The equivalent shape has the same area as a polygonal window or door."
                },
                "equivalent_rectangle_aspect_ratio": {
                    "type": "number",
                    "note": "This field is used when UserDefinedAspectRatio is entered in the Equivalent Rectangle Method field.",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                }
            },
            "required": [
                "surface_name",
                "leakage_component_name"
            ]
        }
    },
    "group": "AirflowNetwork",
    "legacy_idd": {
        "field_info": {
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "leakage_component_name": {
                "field_name": "Leakage Component Name",
                "field_type": "a"
            },
            "external_node_name": {
                "field_name": "External Node Name",
                "field_type": "a"
            },
            "window_door_opening_factor_or_crack_factor": {
                "field_name": "Window/Door Opening Factor, or Crack Factor",
                "field_type": "n"
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
            "occupant_ventilation_control_name": {
                "field_name": "Occupant Ventilation Control Name",
                "field_type": "a"
            },
            "equivalent_rectangle_method": {
                "field_name": "Equivalent Rectangle Method",
                "field_type": "a"
            },
            "equivalent_rectangle_aspect_ratio": {
                "field_name": "Equivalent Rectangle Aspect Ratio",
                "field_type": "n"
            }
        },
        "fields": [
            "surface_name",
            "leakage_component_name",
            "external_node_name",
            "window_door_opening_factor_or_crack_factor",
            "ventilation_control_mode",
            "ventilation_control_zone_temperature_setpoint_schedule_name",
            "minimum_venting_open_factor",
            "indoor_and_outdoor_temperature_difference_lower_limit_for_maximum_venting_open_factor",
            "indoor_and_outdoor_temperature_difference_upper_limit_for_minimum_venting_open_factor",
            "indoor_and_outdoor_enthalpy_difference_lower_limit_for_maximum_venting_open_factor",
            "indoor_and_outdoor_enthalpy_difference_upper_limit_for_minimum_venting_open_factor",
            "venting_availability_schedule_name",
            "occupant_ventilation_control_name",
            "equivalent_rectangle_method",
            "equivalent_rectangle_aspect_ratio"
        ],
        "alphas": {
            "fields": [
                "surface_name",
                "leakage_component_name",
                "external_node_name",
                "ventilation_control_mode",
                "ventilation_control_zone_temperature_setpoint_schedule_name",
                "venting_availability_schedule_name",
                "occupant_ventilation_control_name",
                "equivalent_rectangle_method"
            ]
        },
        "numerics": {
            "fields": [
                "window_door_opening_factor_or_crack_factor",
                "minimum_venting_open_factor",
                "indoor_and_outdoor_temperature_difference_lower_limit_for_maximum_venting_open_factor",
                "indoor_and_outdoor_temperature_difference_upper_limit_for_minimum_venting_open_factor",
                "indoor_and_outdoor_enthalpy_difference_lower_limit_for_maximum_venting_open_factor",
                "indoor_and_outdoor_enthalpy_difference_upper_limit_for_minimum_venting_open_factor",
                "equivalent_rectangle_aspect_ratio"
            ]
        }
    },
    "type": "object",
    "memo": "This object specifies the properties of a surface linkage through which air flows. Airflow Report: Node 1 as an inside face zone; Node 2 as an outside face zone or external node.",
    "min_fields": 4.0
}
```
