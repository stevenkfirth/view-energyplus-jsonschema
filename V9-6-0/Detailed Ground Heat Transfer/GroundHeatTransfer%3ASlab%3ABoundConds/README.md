```
{
    "GroundHeatTransfer:Slab:BoundConds": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "evtr_is_surface_evapotranspiration_modeled": {
                        "type": "string",
                        "note": "This field specifies whether or not to use the evapotransporation model. The inclusion of evapotransporation in the calculation has the greatest effect in warm dry climates, primarily on the ground surface temperature. This field can be used to turn the evapotransporation off and on to check sensitivity to it.",
                        "enum": [
                            "FALSE",
                            "TRUE"
                        ]
                    },
                    "fixbc_is_the_lower_boundary_at_a_fixed_temperature": {
                        "type": "string",
                        "note": "This field permits using a fixed temperature at the lower surface of the model instead of a zero heat flux condition. This change normally has a very small effect on the results. FALSE selects the zero flux lower boundary condition",
                        "enum": [
                            "FALSE",
                            "TRUE"
                        ]
                    },
                    "tdeepin": {
                        "type": "number",
                        "note": "User input lower boundary temperature if FIXBC is TRUE Blank for FIXBC FALSE or to use the calculated 1-D deep ground temperature.",
                        "units": "C"
                    },
                    "usrhflag_is_the_ground_surface_h_specified_by_the_user_": {
                        "type": "string",
                        "note": "This field flags the use of a user specified heat transfer coefficient on the ground surface. This condition is used primarily for testing. For normal runs (USPHflag is FALSE) and the program calculates the heat transfer coefficient using the weather conditions.",
                        "enum": [
                            "FALSE",
                            "TRUE"
                        ]
                    },
                    "userh_user_specified_ground_surface_heat_transfer_coefficient": {
                        "type": "number",
                        "note": "Used only if USRHflag is TRUE and the heat transfer coefficient value is specified in this field.",
                        "units": "W/m2-K"
                    }
                },
                "required": [
                    "evtr_is_surface_evapotranspiration_modeled",
                    "fixbc_is_the_lower_boundary_at_a_fixed_temperature",
                    "usrhflag_is_the_ground_surface_h_specified_by_the_user_"
                ]
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "evtr_is_surface_evapotranspiration_modeled": {
                    "field_name": "EVTR: Is surface evapotranspiration modeled",
                    "field_type": "a"
                },
                "fixbc_is_the_lower_boundary_at_a_fixed_temperature": {
                    "field_name": "FIXBC: is the lower boundary at a fixed temperature",
                    "field_type": "a"
                },
                "tdeepin": {
                    "field_name": "TDEEPin",
                    "field_type": "n"
                },
                "usrhflag_is_the_ground_surface_h_specified_by_the_user_": {
                    "field_name": "USRHflag: Is the ground surface h specified by the user?",
                    "field_type": "a"
                },
                "userh_user_specified_ground_surface_heat_transfer_coefficient": {
                    "field_name": "USERH: User specified ground surface heat transfer coefficient",
                    "field_type": "n"
                }
            },
            "fields": [
                "evtr_is_surface_evapotranspiration_modeled",
                "fixbc_is_the_lower_boundary_at_a_fixed_temperature",
                "tdeepin",
                "usrhflag_is_the_ground_surface_h_specified_by_the_user_",
                "userh_user_specified_ground_surface_heat_transfer_coefficient"
            ],
            "alphas": {
                "fields": [
                    "evtr_is_surface_evapotranspiration_modeled",
                    "fixbc_is_the_lower_boundary_at_a_fixed_temperature",
                    "usrhflag_is_the_ground_surface_h_specified_by_the_user_"
                ]
            },
            "numerics": {
                "fields": [
                    "tdeepin",
                    "userh_user_specified_ground_surface_heat_transfer_coefficient"
                ]
            }
        },
        "type": "object",
        "memo": "Supplies some of the boundary conditions used in the ground heat transfer calculations."
    }
}
```
