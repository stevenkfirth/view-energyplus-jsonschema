```
{
    "Site:GroundReflectance:SnowModifier": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "ground_reflected_solar_modifier": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 1.0,
                        "note": "Value for modifying the \"normal\" ground reflectance when Snow is on ground when calculating the \"Ground Reflected Solar Radiation Value\" a value of 1.0 here uses the \"normal\" ground reflectance Ground Reflected Solar = (BeamSolar*CosSunZenith + DiffuseSolar)*GroundReflectance This would be further modified by the Snow Ground Reflectance Modifier when Snow was on the ground When Snow on ground, effective GroundReflectance is normal GroundReflectance*\"Ground Reflectance Snow Modifier\" Ground Reflectance achieved in this manner will be restricted to [0.0,1.0]"
                    },
                    "daylighting_ground_reflected_solar_modifier": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 1.0,
                        "note": "Value for modifying the \"normal\" daylighting ground reflectance when Snow is on ground when calculating the \"Ground Reflected Solar Radiation Value\" a value of 1.0 here uses the \"normal\" ground reflectance Ground Reflected Solar = (BeamSolar*CosSunZenith + DiffuseSolar)*GroundReflectance This would be further modified by the Snow Ground Reflectance Modifier when Snow was on the ground When Snow on ground, effective GroundReflectance is normal GroundReflectance*\"Daylighting Ground Reflectance Snow Modifier\" Ground Reflectance achieved in this manner will be restricted to [0.0,1.0]"
                    }
                }
            }
        },
        "group": "Location and Climate",
        "legacy_idd": {
            "field_info": {
                "ground_reflected_solar_modifier": {
                    "field_name": "Ground Reflected Solar Modifier",
                    "field_type": "n"
                },
                "daylighting_ground_reflected_solar_modifier": {
                    "field_name": "Daylighting Ground Reflected Solar Modifier",
                    "field_type": "n"
                }
            },
            "fields": [
                "ground_reflected_solar_modifier",
                "daylighting_ground_reflected_solar_modifier"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "ground_reflected_solar_modifier",
                    "daylighting_ground_reflected_solar_modifier"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies ground reflectance multipliers when snow resident on the ground. These multipliers are applied to the \"normal\" ground reflectances specified in Site:GroundReflectance."
    }
}
```
