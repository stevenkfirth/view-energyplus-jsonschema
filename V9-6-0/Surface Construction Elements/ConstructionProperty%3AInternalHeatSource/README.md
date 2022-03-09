```
{
    "ConstructionProperty:InternalHeatSource": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "construction_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ConstructionNames"
                        ]
                    },
                    "thermal_source_present_after_layer_number": {
                        "type": "number",
                        "minimum": 1.0,
                        "note": "refers to the list of materials which follows"
                    },
                    "temperature_calculation_requested_after_layer_number": {
                        "type": "number",
                        "note": "refers to the list of materials which follows"
                    },
                    "dimensions_for_the_ctf_calculation": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 2.0,
                        "note": "1 = 1-dimensional calculation, 2 = 2-dimensional calculation"
                    },
                    "tube_spacing": {
                        "type": "number",
                        "units": "m",
                        "note": "uniform spacing between tubes or resistance wires in direction perpendicular to main intended direction of heat transfer"
                    },
                    "two_dimensional_temperature_calculation_position": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0,
                        "units": "dimensionless",
                        "note": "used in conjunction with field Temperature Calculation Requested After Layer Number this field is the location perpendicular to the main direction of heat transfer 0.0 means in line with the tubing, 1.0 means at the midpoint between two adjacent pipes this field is ignored for 1-D calculations"
                    }
                },
                "required": [
                    "thermal_source_present_after_layer_number",
                    "temperature_calculation_requested_after_layer_number",
                    "dimensions_for_the_ctf_calculation",
                    "tube_spacing"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "InternalHeatSourceNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "construction_name": {
                    "field_name": "Construction Name",
                    "field_type": "a"
                },
                "thermal_source_present_after_layer_number": {
                    "field_name": "Thermal Source Present After Layer Number",
                    "field_type": "n"
                },
                "temperature_calculation_requested_after_layer_number": {
                    "field_name": "Temperature Calculation Requested After Layer Number",
                    "field_type": "n"
                },
                "dimensions_for_the_ctf_calculation": {
                    "field_name": "Dimensions for the CTF Calculation",
                    "field_type": "n"
                },
                "tube_spacing": {
                    "field_name": "Tube Spacing",
                    "field_type": "n"
                },
                "two_dimensional_temperature_calculation_position": {
                    "field_name": "Two-Dimensional Temperature Calculation Position",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "construction_name",
                "thermal_source_present_after_layer_number",
                "temperature_calculation_requested_after_layer_number",
                "dimensions_for_the_ctf_calculation",
                "tube_spacing",
                "two_dimensional_temperature_calculation_position"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "construction_name"
                ]
            },
            "numerics": {
                "fields": [
                    "thermal_source_present_after_layer_number",
                    "temperature_calculation_requested_after_layer_number",
                    "dimensions_for_the_ctf_calculation",
                    "tube_spacing",
                    "two_dimensional_temperature_calculation_position"
                ]
            }
        },
        "type": "object",
        "memo": "Internal heat source to be attached to a construction layer"
    }
}
```
