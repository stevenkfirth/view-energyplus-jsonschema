```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "fraction_of_surface_area_with_active_solar_cells": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "conversion_efficiency_input_mode": {
                    "type": "string",
                    "enum": [
                        "Fixed",
                        "Scheduled"
                    ]
                },
                "value_for_cell_efficiency_if_fixed": {
                    "type": "number",
                    "note": "Efficiency = (power generated [W])/(incident solar[W])",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "efficiency_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "fraction_of_surface_area_with_active_solar_cells"
            ]
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "reference": [
            "PVModules"
        ]
    },
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "fraction_of_surface_area_with_active_solar_cells": {
                "field_name": "Fraction of Surface Area with Active Solar Cells",
                "field_type": "n"
            },
            "conversion_efficiency_input_mode": {
                "field_name": "Conversion Efficiency Input Mode",
                "field_type": "a"
            },
            "value_for_cell_efficiency_if_fixed": {
                "field_name": "Value for Cell Efficiency if Fixed",
                "field_type": "n"
            },
            "efficiency_schedule_name": {
                "field_name": "Efficiency Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "fraction_of_surface_area_with_active_solar_cells",
            "conversion_efficiency_input_mode",
            "value_for_cell_efficiency_if_fixed",
            "efficiency_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "conversion_efficiency_input_mode",
                "efficiency_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "fraction_of_surface_area_with_active_solar_cells",
                "value_for_cell_efficiency_if_fixed"
            ]
        }
    },
    "type": "object",
    "memo": "Describes a simple model of photovoltaics that may be useful for early phase design analysis. In this model the user has direct access to the efficiency with which surfaces convert incident solar radiation to electricity and need not specify arrays of specific modules."
}
```
