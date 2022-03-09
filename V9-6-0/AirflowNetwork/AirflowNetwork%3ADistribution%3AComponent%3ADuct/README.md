```
{
    "AirflowNetwork:Distribution:Component:Duct": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "duct_length": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the length of the duct."
                    },
                    "hydraulic_diameter": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the hydraulic diameter of the duct. Hydraulic diameter is defined as 4 multiplied by cross section area divided by perimeter"
                    },
                    "cross_section_area": {
                        "type": "number",
                        "units": "m2",
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the cross section area of the duct."
                    },
                    "surface_roughness": {
                        "type": "number",
                        "units": "m",
                        "default": 0.0009,
                        "exclusiveMinimum": 0.0,
                        "note": "Enter the inside surface roughness of the duct."
                    },
                    "coefficient_for_local_dynamic_loss_due_to_fitting": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 0.0,
                        "minimum": 0.0,
                        "note": "Enter the coefficient used to calculate dynamic losses of fittings (e.g. elbows)."
                    },
                    "heat_transmittance_coefficient_u_factor_for_duct_wall_construction": {
                        "type": "number",
                        "note": "conduction only Default value of 0.943 is equivalent to 1.06 m2-K/W (R6) duct insulation.",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0,
                        "default": 0.943
                    },
                    "overall_moisture_transmittance_coefficient_from_air_to_air": {
                        "type": "number",
                        "units": "kg/m2",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001,
                        "note": "Enter the overall moisture transmittance coefficient including moisture film coefficients at both surfaces."
                    },
                    "outside_convection_coefficient": {
                        "type": "number",
                        "note": "optional. convection coefficient calculated automatically, unless specified",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0
                    },
                    "inside_convection_coefficient": {
                        "type": "number",
                        "note": "optional. convection coefficient calculated automatically, unless specified",
                        "units": "W/m2-K",
                        "exclusiveMinimum": 0.0
                    }
                },
                "required": [
                    "duct_length",
                    "hydraulic_diameter",
                    "cross_section_area"
                ]
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AirflowNetworkComponentNames"
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
                "duct_length": {
                    "field_name": "Duct Length",
                    "field_type": "n"
                },
                "hydraulic_diameter": {
                    "field_name": "Hydraulic Diameter",
                    "field_type": "n"
                },
                "cross_section_area": {
                    "field_name": "Cross Section Area",
                    "field_type": "n"
                },
                "surface_roughness": {
                    "field_name": "Surface Roughness",
                    "field_type": "n"
                },
                "coefficient_for_local_dynamic_loss_due_to_fitting": {
                    "field_name": "Coefficient for Local Dynamic Loss Due to Fitting",
                    "field_type": "n"
                },
                "heat_transmittance_coefficient_u_factor_for_duct_wall_construction": {
                    "field_name": "Heat Transmittance Coefficient (U-Factor) for Duct Wall Construction",
                    "field_type": "n"
                },
                "overall_moisture_transmittance_coefficient_from_air_to_air": {
                    "field_name": "Overall Moisture Transmittance Coefficient from Air to Air",
                    "field_type": "n"
                },
                "outside_convection_coefficient": {
                    "field_name": "Outside Convection Coefficient",
                    "field_type": "n"
                },
                "inside_convection_coefficient": {
                    "field_name": "Inside Convection Coefficient",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "duct_length",
                "hydraulic_diameter",
                "cross_section_area",
                "surface_roughness",
                "coefficient_for_local_dynamic_loss_due_to_fitting",
                "heat_transmittance_coefficient_u_factor_for_duct_wall_construction",
                "overall_moisture_transmittance_coefficient_from_air_to_air",
                "outside_convection_coefficient",
                "inside_convection_coefficient"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "duct_length",
                    "hydraulic_diameter",
                    "cross_section_area",
                    "surface_roughness",
                    "coefficient_for_local_dynamic_loss_due_to_fitting",
                    "heat_transmittance_coefficient_u_factor_for_duct_wall_construction",
                    "overall_moisture_transmittance_coefficient_from_air_to_air",
                    "outside_convection_coefficient",
                    "inside_convection_coefficient"
                ]
            }
        },
        "type": "object",
        "memo": "This object defines the relationship between pressure and air flow through the duct.",
        "min_fields": 8.0
    }
}
```
