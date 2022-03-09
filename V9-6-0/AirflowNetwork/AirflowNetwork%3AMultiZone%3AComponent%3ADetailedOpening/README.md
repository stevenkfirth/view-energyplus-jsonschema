```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "air_mass_flow_coefficient_when_opening_is_closed": {
                    "type": "number",
                    "units": "kg/s-m",
                    "exclusiveMinimum": 0.0,
                    "note": "Defined at 1 Pa per meter of crack length. Enter the coefficient used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent. Used only when opening (window or door) is closed."
                },
                "air_mass_flow_exponent_when_opening_is_closed": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.5,
                    "maximum": 1.0,
                    "default": 0.65,
                    "note": "Enter the exponent used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent. Used only when opening (window or door) is closed."
                },
                "type_of_rectangular_large_vertical_opening_lvo_": {
                    "type": "string",
                    "enum": [
                        "",
                        "HorizontallyPivoted",
                        "NonPivoted"
                    ],
                    "note": "Select the type of vertical opening: Non-pivoted opening or Horizontally pivoted opening.",
                    "default": "NonPivoted"
                },
                "extra_crack_length_or_height_of_pivoting_axis": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "Extra crack length is used for LVO Non-pivoted type with multiple openable parts. Height of pivoting axis is used for LVO Horizontally pivoted type. Specifies window or door characteristics that depend on the LVO type. For Non-pivoted Type (rectangular windows and doors), this field is the extra crack length in meters due to multiple openable parts, if present. Extra here means in addition to the length of the cracks on the top, bottom and sides of the window/door. For Horizontally pivoted Type, this field gives the height of the pivoting axis measured from the bottom of the glazed part of the window (m)."
                },
                "number_of_sets_of_opening_factor_data": {
                    "type": "number",
                    "minimum": 2.0,
                    "maximum": 4.0,
                    "note": "Enter the number of the following sets of data for opening factor, discharge coefficient, width factor, height factor, and start height factor."
                },
                "opening_factor_1": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 0.0,
                    "default": 0.0,
                    "note": "This value must be specified as 0."
                },
                "discharge_coefficient_for_opening_factor_1": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.001,
                    "note": "The Discharge Coefficient indicates the fractional effectiveness for air flow through a window or door at that Opening Factor."
                },
                "width_factor_for_opening_factor_1": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Width Factor is the opening width divided by the window or door width."
                },
                "height_factor_for_opening_factor_1": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Height Factor is the opening height divided by the window or door height."
                },
                "start_height_factor_for_opening_factor_1": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Start Height Factor is the Start Height divided by the window or door height. Start Height is the distance between the bottom of the window or door and the bottom of the window or door opening. The sum of the Height Factor and the Start Height Factor must be less than 1.0 in order to have the opening within the window or door dimensions."
                },
                "opening_factor_2": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "note": "If Number of Sets of Opening Factor Data = 2, this value must be 1.0. If Number of Sets of Opening Factor Data = 3, this value must be less than 1.0. If Number of Sets of Opening Factor Data = 4, this value must be less than the value entered for Opening factor 3 and greater than the value entered for Opening factor 1."
                },
                "discharge_coefficient_for_opening_factor_2": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0,
                    "note": "The Discharge Coefficient indicates the fractional effectiveness for air flow through a window or door at that Opening Factor."
                },
                "width_factor_for_opening_factor_2": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0,
                    "note": "The Width Factor is the opening width divided by the window or door width."
                },
                "height_factor_for_opening_factor_2": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0,
                    "note": "The Height Factor is the opening height divided by the window or door height."
                },
                "start_height_factor_for_opening_factor_2": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "exclusiveMaximum": 1.0,
                    "default": 0.0,
                    "note": "The Start Height Factor is the Start Height divided by the window or door height. Start Height is the distance between the bottom of the window or door and the bottom of the window or door opening. The sum of the Height Factor and the Start Height Factor must be less than 1.0 in order to have the opening within the window or door dimensions."
                },
                "opening_factor_3": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "note": "If Number of Sets of Opening Factor Data = 3, this value must be 1.0. If Number of Sets of Opening Factor Data = 4, this value must be less than 1.0, and greater than value entered for Opening factor 2."
                },
                "discharge_coefficient_for_opening_factor_3": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Discharge Coefficient indicates the fractional effectiveness for air flow through a window or door at that Opening Factor."
                },
                "width_factor_for_opening_factor_3": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Width Factor is the opening width divided by the window or door width."
                },
                "height_factor_for_opening_factor_3": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Height Factor is the opening height divided by the window or door height."
                },
                "start_height_factor_for_opening_factor_3": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Start Height Factor is the Start Height divided by the window or door height. Start Height is the distance between the bottom of the window or door and the bottom of the window or door opening. The sum of the Height Factor and the Start Height Factor must be less than 1.0 in order to have the opening within the window or door dimensions."
                },
                "opening_factor_4": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "note": "If Number of Sets of Opening Factor Data = 4, this value must be 1.0"
                },
                "discharge_coefficient_for_opening_factor_4": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Discharge Coefficient indicates the fractional effectiveness for air flow through a window or door at that Opening Factor."
                },
                "width_factor_for_opening_factor_4": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Width Factor is the opening width divided by the window or door width."
                },
                "height_factor_for_opening_factor_4": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Height Factor is the opening height divided by the window or door height."
                },
                "start_height_factor_for_opening_factor_4": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "The Start Height Factor is the Start Height divided by the window or door height. Start Height is the distance between the bottom of the window or door and the bottom of the window or door opening. The sum of the Height Factor and the Start Height Factor must be less than 1.0 in order to have the opening within the window or door dimensions."
                }
            },
            "required": [
                "air_mass_flow_coefficient_when_opening_is_closed",
                "number_of_sets_of_opening_factor_data",
                "opening_factor_2"
            ]
        }
    },
    "group": "AirflowNetwork",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "SurfaceAirflowLeakageNames"
        ],
        "note": "Enter a unique name for this object."
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "air_mass_flow_coefficient_when_opening_is_closed": {
                "field_name": "Air Mass Flow Coefficient When Opening is Closed",
                "field_type": "n"
            },
            "air_mass_flow_exponent_when_opening_is_closed": {
                "field_name": "Air Mass Flow Exponent When Opening is Closed",
                "field_type": "n"
            },
            "type_of_rectangular_large_vertical_opening_lvo_": {
                "field_name": "Type of Rectangular Large Vertical Opening (LVO)",
                "field_type": "a"
            },
            "extra_crack_length_or_height_of_pivoting_axis": {
                "field_name": "Extra Crack Length or Height of Pivoting Axis",
                "field_type": "n"
            },
            "number_of_sets_of_opening_factor_data": {
                "field_name": "Number of Sets of Opening Factor Data",
                "field_type": "n"
            },
            "opening_factor_1": {
                "field_name": "Opening Factor 1",
                "field_type": "n"
            },
            "discharge_coefficient_for_opening_factor_1": {
                "field_name": "Discharge Coefficient for Opening Factor 1",
                "field_type": "n"
            },
            "width_factor_for_opening_factor_1": {
                "field_name": "Width Factor for Opening Factor 1",
                "field_type": "n"
            },
            "height_factor_for_opening_factor_1": {
                "field_name": "Height Factor for Opening Factor 1",
                "field_type": "n"
            },
            "start_height_factor_for_opening_factor_1": {
                "field_name": "Start Height Factor for Opening Factor 1",
                "field_type": "n"
            },
            "opening_factor_2": {
                "field_name": "Opening Factor 2",
                "field_type": "n"
            },
            "discharge_coefficient_for_opening_factor_2": {
                "field_name": "Discharge Coefficient for Opening Factor 2",
                "field_type": "n"
            },
            "width_factor_for_opening_factor_2": {
                "field_name": "Width Factor for Opening Factor 2",
                "field_type": "n"
            },
            "height_factor_for_opening_factor_2": {
                "field_name": "Height Factor for Opening Factor 2",
                "field_type": "n"
            },
            "start_height_factor_for_opening_factor_2": {
                "field_name": "Start Height Factor for Opening Factor 2",
                "field_type": "n"
            },
            "opening_factor_3": {
                "field_name": "Opening Factor 3",
                "field_type": "n"
            },
            "discharge_coefficient_for_opening_factor_3": {
                "field_name": "Discharge Coefficient for Opening Factor 3",
                "field_type": "n"
            },
            "width_factor_for_opening_factor_3": {
                "field_name": "Width Factor for Opening Factor 3",
                "field_type": "n"
            },
            "height_factor_for_opening_factor_3": {
                "field_name": "Height Factor for Opening Factor 3",
                "field_type": "n"
            },
            "start_height_factor_for_opening_factor_3": {
                "field_name": "Start Height Factor for Opening Factor 3",
                "field_type": "n"
            },
            "opening_factor_4": {
                "field_name": "Opening Factor 4",
                "field_type": "n"
            },
            "discharge_coefficient_for_opening_factor_4": {
                "field_name": "Discharge Coefficient for Opening Factor 4",
                "field_type": "n"
            },
            "width_factor_for_opening_factor_4": {
                "field_name": "Width Factor for Opening Factor 4",
                "field_type": "n"
            },
            "height_factor_for_opening_factor_4": {
                "field_name": "Height Factor for Opening Factor 4",
                "field_type": "n"
            },
            "start_height_factor_for_opening_factor_4": {
                "field_name": "Start Height Factor for Opening Factor 4",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "air_mass_flow_coefficient_when_opening_is_closed",
            "air_mass_flow_exponent_when_opening_is_closed",
            "type_of_rectangular_large_vertical_opening_lvo_",
            "extra_crack_length_or_height_of_pivoting_axis",
            "number_of_sets_of_opening_factor_data",
            "opening_factor_1",
            "discharge_coefficient_for_opening_factor_1",
            "width_factor_for_opening_factor_1",
            "height_factor_for_opening_factor_1",
            "start_height_factor_for_opening_factor_1",
            "opening_factor_2",
            "discharge_coefficient_for_opening_factor_2",
            "width_factor_for_opening_factor_2",
            "height_factor_for_opening_factor_2",
            "start_height_factor_for_opening_factor_2",
            "opening_factor_3",
            "discharge_coefficient_for_opening_factor_3",
            "width_factor_for_opening_factor_3",
            "height_factor_for_opening_factor_3",
            "start_height_factor_for_opening_factor_3",
            "opening_factor_4",
            "discharge_coefficient_for_opening_factor_4",
            "width_factor_for_opening_factor_4",
            "height_factor_for_opening_factor_4",
            "start_height_factor_for_opening_factor_4"
        ],
        "alphas": {
            "fields": [
                "name",
                "type_of_rectangular_large_vertical_opening_lvo_"
            ]
        },
        "numerics": {
            "fields": [
                "air_mass_flow_coefficient_when_opening_is_closed",
                "air_mass_flow_exponent_when_opening_is_closed",
                "extra_crack_length_or_height_of_pivoting_axis",
                "number_of_sets_of_opening_factor_data",
                "opening_factor_1",
                "discharge_coefficient_for_opening_factor_1",
                "width_factor_for_opening_factor_1",
                "height_factor_for_opening_factor_1",
                "start_height_factor_for_opening_factor_1",
                "opening_factor_2",
                "discharge_coefficient_for_opening_factor_2",
                "width_factor_for_opening_factor_2",
                "height_factor_for_opening_factor_2",
                "start_height_factor_for_opening_factor_2",
                "opening_factor_3",
                "discharge_coefficient_for_opening_factor_3",
                "width_factor_for_opening_factor_3",
                "height_factor_for_opening_factor_3",
                "start_height_factor_for_opening_factor_3",
                "opening_factor_4",
                "discharge_coefficient_for_opening_factor_4",
                "width_factor_for_opening_factor_4",
                "height_factor_for_opening_factor_4",
                "start_height_factor_for_opening_factor_4"
            ]
        }
    },
    "type": "object",
    "memo": "This object specifies the properties of airflow through windows and doors (window, door and glass door heat transfer subsurfaces) when they are closed or open.",
    "min_fields": 16.0
}
```
