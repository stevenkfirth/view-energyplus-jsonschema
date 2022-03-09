```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "solar_transmittance": {
                    "type": "number",
                    "note": "Assumed independent of incidence angle",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "exclusiveMaximum": 1.0
                },
                "solar_reflectance": {
                    "type": "number",
                    "note": "Assumed same for both sides Assumed independent of incidence angle",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "exclusiveMaximum": 1.0
                },
                "visible_transmittance": {
                    "type": "number",
                    "note": "Assumed independent of incidence angle",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "exclusiveMaximum": 1.0
                },
                "visible_reflectance": {
                    "type": "number",
                    "note": "Assumed same for both sides Assumed independent of incidence angle",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "exclusiveMaximum": 1.0
                },
                "infrared_hemispherical_emissivity": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMaximum": 1.0,
                    "exclusiveMinimum": 0.0
                },
                "infrared_transmittance": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMaximum": 1.0,
                    "minimum": 0.0
                },
                "thickness": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "in"
                },
                "conductivity": {
                    "type": "number",
                    "units": "W/m-K",
                    "exclusiveMinimum": 0.0
                },
                "shade_to_glass_distance": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.001,
                    "maximum": 1.0,
                    "default": 0.05,
                    "ip-units": "in"
                },
                "top_opening_multiplier": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.5
                },
                "bottom_opening_multiplier": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.5
                },
                "left_side_opening_multiplier": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.5
                },
                "right_side_opening_multiplier": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.5
                },
                "airflow_permeability": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 0.8,
                    "default": 0.0
                }
            },
            "required": [
                "solar_transmittance",
                "solar_reflectance",
                "visible_transmittance",
                "visible_reflectance",
                "infrared_hemispherical_emissivity",
                "infrared_transmittance",
                "thickness",
                "conductivity"
            ]
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "MaterialName",
            "WindowShadesScreensAndBlinds"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "solar_transmittance": {
                "field_name": "Solar Transmittance",
                "field_type": "n"
            },
            "solar_reflectance": {
                "field_name": "Solar Reflectance",
                "field_type": "n"
            },
            "visible_transmittance": {
                "field_name": "Visible Transmittance",
                "field_type": "n"
            },
            "visible_reflectance": {
                "field_name": "Visible Reflectance",
                "field_type": "n"
            },
            "infrared_hemispherical_emissivity": {
                "field_name": "Infrared Hemispherical Emissivity",
                "field_type": "n"
            },
            "infrared_transmittance": {
                "field_name": "Infrared Transmittance",
                "field_type": "n"
            },
            "thickness": {
                "field_name": "Thickness",
                "field_type": "n"
            },
            "conductivity": {
                "field_name": "Conductivity",
                "field_type": "n"
            },
            "shade_to_glass_distance": {
                "field_name": "Shade to Glass Distance",
                "field_type": "n"
            },
            "top_opening_multiplier": {
                "field_name": "Top Opening Multiplier",
                "field_type": "n"
            },
            "bottom_opening_multiplier": {
                "field_name": "Bottom Opening Multiplier",
                "field_type": "n"
            },
            "left_side_opening_multiplier": {
                "field_name": "Left-Side Opening Multiplier",
                "field_type": "n"
            },
            "right_side_opening_multiplier": {
                "field_name": "Right-Side Opening Multiplier",
                "field_type": "n"
            },
            "airflow_permeability": {
                "field_name": "Airflow Permeability",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "solar_transmittance",
            "solar_reflectance",
            "visible_transmittance",
            "visible_reflectance",
            "infrared_hemispherical_emissivity",
            "infrared_transmittance",
            "thickness",
            "conductivity",
            "shade_to_glass_distance",
            "top_opening_multiplier",
            "bottom_opening_multiplier",
            "left_side_opening_multiplier",
            "right_side_opening_multiplier",
            "airflow_permeability"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "solar_transmittance",
                "solar_reflectance",
                "visible_transmittance",
                "visible_reflectance",
                "infrared_hemispherical_emissivity",
                "infrared_transmittance",
                "thickness",
                "conductivity",
                "shade_to_glass_distance",
                "top_opening_multiplier",
                "bottom_opening_multiplier",
                "left_side_opening_multiplier",
                "right_side_opening_multiplier",
                "airflow_permeability"
            ]
        }
    },
    "type": "object",
    "memo": "Specifies the properties of window shade materials. Reflectance and emissivity properties are assumed to be the same on both sides of the shade. Shades are considered to be perfect diffusers (all transmitted and reflected radiation is hemispherically-diffuse) independent of angle of incidence.",
    "min_fields": 15.0
}
```
