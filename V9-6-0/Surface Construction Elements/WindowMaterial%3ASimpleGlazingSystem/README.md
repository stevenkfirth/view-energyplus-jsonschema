```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "u_factor": {
                    "type": "number",
                    "note": "Enter U-Factor including film coefficients Note that the effective upper limit for U-factor is 5.8 W/m2-K",
                    "units": "W/m2-K",
                    "exclusiveMinimum": 0.0,
                    "maximum": 7.0
                },
                "solar_heat_gain_coefficient": {
                    "type": "number",
                    "note": "SHGC at Normal Incidence",
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 1.0
                },
                "visible_transmittance": {
                    "type": "number",
                    "note": "VT at Normal Incidence optional",
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 1.0
                }
            },
            "required": [
                "u_factor",
                "solar_heat_gain_coefficient"
            ]
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "GlazingMaterialName",
            "MaterialName"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "u_factor": {
                "field_name": "U-Factor",
                "field_type": "n"
            },
            "solar_heat_gain_coefficient": {
                "field_name": "Solar Heat Gain Coefficient",
                "field_type": "n"
            },
            "visible_transmittance": {
                "field_name": "Visible Transmittance",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "u_factor",
            "solar_heat_gain_coefficient",
            "visible_transmittance"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "u_factor",
                "solar_heat_gain_coefficient",
                "visible_transmittance"
            ]
        }
    },
    "type": "object",
    "memo": "Alternate method of describing windows This window material object is used to define an entire glazing system using simple performance parameters.",
    "min_fields": 3.0
}
```
