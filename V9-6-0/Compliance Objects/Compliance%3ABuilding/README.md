```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "building_rotation_for_appendix_g": {
                    "type": "number",
                    "note": "Additional degrees of rotation to be used with the requirement in ASHRAE Standard 90.1 Appendix G that states that the baseline building should be rotated in four directions.",
                    "units": "deg",
                    "default": 0.0
                }
            }
        }
    },
    "group": "Compliance Objects",
    "legacy_idd": {
        "field_info": {
            "building_rotation_for_appendix_g": {
                "field_name": "Building Rotation for Appendix G",
                "field_type": "n"
            }
        },
        "fields": [
            "building_rotation_for_appendix_g"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "building_rotation_for_appendix_g"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Building level inputs related to compliance to building standards, building codes, and beyond energy code programs.",
    "min_fields": 1.0
}
```
