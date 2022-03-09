```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "rins_r_value_of_under_slab_insulation": {
                    "type": "number",
                    "note": "This field provides the thermal resistance value of the under slab insulation. It should be zero if the vertical insulation configuration is selected. typical value= 0-2.0",
                    "units": "m2-K/W",
                    "default": 0.0
                },
                "dins_width_of_strip_of_under_slab_insulation": {
                    "type": "number",
                    "note": "This specifies the width of the perimeter strip of insulation under the slab. It should be zero if for the vertical insulation configuration is selected. typical value= 0-2.0",
                    "units": "m",
                    "default": 0.0
                },
                "rvins_r_value_of_vertical_insulation": {
                    "type": "number",
                    "note": "This field specifies the thermal resistance of the vertical insulation. It should be zero if the under slab insulation configuration is selected. typical value= 0-3.0",
                    "units": "m2-K/W",
                    "default": 0.0
                },
                "zvins_depth_of_vertical_insulation": {
                    "type": "number",
                    "note": "This field specifies the depth of the vertical insulation into the ground in meters. It starts at the slab upper surface and extends into the ground. It should be zero if the under slab insulation configuration is selected. only use values= .2 .4 .6 .8 1.0 1.5 2.0 2.5 3.0",
                    "units": "m",
                    "default": 0.0
                },
                "ivins_flag_is_there_vertical_insulation": {
                    "note": "Specifies if the vertical insulation configuration is being used. values: 1=yes vertical insulation 0=no under-slab insulation",
                    "default": 0.0,
                    "anyOf": [
                        {
                            "type": "number",
                            "enum": [
                                0,
                                1
                            ]
                        },
                        {
                            "type": "string",
                            "enum": [
                                ""
                            ]
                        }
                    ]
                }
            }
        }
    },
    "group": "Detailed Ground Heat Transfer",
    "legacy_idd": {
        "field_info": {
            "rins_r_value_of_under_slab_insulation": {
                "field_name": "RINS: R value of under slab insulation",
                "field_type": "n"
            },
            "dins_width_of_strip_of_under_slab_insulation": {
                "field_name": "DINS: Width of strip of under slab insulation",
                "field_type": "n"
            },
            "rvins_r_value_of_vertical_insulation": {
                "field_name": "RVINS: R value of vertical insulation",
                "field_type": "n"
            },
            "zvins_depth_of_vertical_insulation": {
                "field_name": "ZVINS: Depth of vertical insulation",
                "field_type": "n"
            },
            "ivins_flag_is_there_vertical_insulation": {
                "field_name": "IVINS: Flag: Is there vertical insulation",
                "field_type": "n"
            }
        },
        "fields": [
            "rins_r_value_of_under_slab_insulation",
            "dins_width_of_strip_of_under_slab_insulation",
            "rvins_r_value_of_vertical_insulation",
            "zvins_depth_of_vertical_insulation",
            "ivins_flag_is_there_vertical_insulation"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "rins_r_value_of_under_slab_insulation",
                "dins_width_of_strip_of_under_slab_insulation",
                "rvins_r_value_of_vertical_insulation",
                "zvins_depth_of_vertical_insulation",
                "ivins_flag_is_there_vertical_insulation"
            ]
        }
    },
    "type": "object",
    "memo": "This object supplies the information about insulation used around the slab. There are two possible configurations: under the slab or vertical insulation around the slab.",
    "min_fields": 5.0
}
```
