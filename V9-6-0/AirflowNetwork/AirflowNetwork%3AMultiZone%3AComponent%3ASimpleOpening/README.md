```
{
    "AirflowNetwork:MultiZone:Component:SimpleOpening": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "air_mass_flow_coefficient_when_opening_is_closed": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "kg/s-m",
                        "note": "Defined at 1 Pa pressure difference. Enter the coefficient used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent. Used only when opening (window or door) is closed."
                    },
                    "air_mass_flow_exponent_when_opening_is_closed": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 0.65,
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "note": "Enter the exponent used in the following equation: Mass Flow Rate = Air Mass Flow Coefficient * (dP)^Air Mass Flow Exponent. Used only when opening (window or door) is closed."
                    },
                    "minimum_density_difference_for_two_way_flow": {
                        "type": "number",
                        "units": "kg/m3",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the minimum density difference above which two-way flow may occur due to stack effect."
                    },
                    "discharge_coefficient": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "note": "The Discharge Coefficient indicates the fractional effectiveness for air flow through a window or door at that Opening Factor."
                    }
                },
                "required": [
                    "air_mass_flow_coefficient_when_opening_is_closed",
                    "minimum_density_difference_for_two_way_flow",
                    "discharge_coefficient"
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
                "minimum_density_difference_for_two_way_flow": {
                    "field_name": "Minimum Density Difference for Two-Way Flow",
                    "field_type": "n"
                },
                "discharge_coefficient": {
                    "field_name": "Discharge Coefficient",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "air_mass_flow_coefficient_when_opening_is_closed",
                "air_mass_flow_exponent_when_opening_is_closed",
                "minimum_density_difference_for_two_way_flow",
                "discharge_coefficient"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "air_mass_flow_coefficient_when_opening_is_closed",
                    "air_mass_flow_exponent_when_opening_is_closed",
                    "minimum_density_difference_for_two_way_flow",
                    "discharge_coefficient"
                ]
            }
        },
        "type": "object",
        "memo": "This object specifies the properties of air flow through windows and doors (window, door and glass door heat transfer subsurfaces) when they are closed or open.",
        "min_fields": 5.0
    }
}
```
