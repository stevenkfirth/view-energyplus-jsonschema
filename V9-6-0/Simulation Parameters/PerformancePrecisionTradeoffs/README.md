```
{
    "PerformancePrecisionTradeoffs": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "use_coil_direct_solutions": {
                        "type": "string",
                        "note": "If Yes, an analytical or empirical solution will be used to replace iterations in the coil performance calculations.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "zone_radiant_exchange_algorithm": {
                        "type": "string",
                        "note": "Determines which algorithm will be used to solve long wave radiant exchange among surfaces within a zone.",
                        "enum": [
                            "",
                            "CarrollMRT",
                            "ScriptF"
                        ],
                        "default": "ScriptF"
                    },
                    "override_mode": {
                        "type": "string",
                        "note": "The increasing mode number roughly correspond with increased speed. A description of each mode are shown in the documentation. When Advanced is selected the N1 field value is used.",
                        "enum": [
                            "",
                            "Advanced",
                            "Mode01",
                            "Mode02",
                            "Mode03",
                            "Mode04",
                            "Mode05",
                            "Mode06",
                            "Mode07",
                            "Mode08",
                            "Normal"
                        ],
                        "default": "Normal"
                    },
                    "maxzonetempdiff": {
                        "type": "number",
                        "note": "Maximum zone temperature change before HVAC timestep is shortened. Only used when Override Mode is set to Advanced",
                        "minimum": 0.1,
                        "maximum": 3.0,
                        "default": 0.3
                    },
                    "maxalloweddeltemp": {
                        "type": "number",
                        "note": "Maximum surface temperature change before HVAC timestep is shortened. Only used when Override Mode is set to Advanced",
                        "minimum": 0.002,
                        "maximum": 0.1,
                        "default": 0.002
                    },
                    "use_representative_surfaces_for_calculations": {
                        "type": "string",
                        "note": "Automatically group surfaces with similar characteristics and perform relevant calculations only once for each group.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    }
                }
            }
        },
        "group": "Simulation Parameters",
        "legacy_idd": {
            "field_info": {
                "use_coil_direct_solutions": {
                    "field_name": "Use Coil Direct Solutions",
                    "field_type": "a"
                },
                "zone_radiant_exchange_algorithm": {
                    "field_name": "Zone Radiant Exchange Algorithm",
                    "field_type": "a"
                },
                "override_mode": {
                    "field_name": "Override Mode",
                    "field_type": "a"
                },
                "maxzonetempdiff": {
                    "field_name": "MaxZoneTempDiff",
                    "field_type": "n"
                },
                "maxalloweddeltemp": {
                    "field_name": "MaxAllowedDelTemp",
                    "field_type": "n"
                },
                "use_representative_surfaces_for_calculations": {
                    "field_name": "Use Representative Surfaces for Calculations",
                    "field_type": "a"
                }
            },
            "fields": [
                "use_coil_direct_solutions",
                "zone_radiant_exchange_algorithm",
                "override_mode",
                "maxzonetempdiff",
                "maxalloweddeltemp",
                "use_representative_surfaces_for_calculations"
            ],
            "alphas": {
                "fields": [
                    "use_coil_direct_solutions",
                    "zone_radiant_exchange_algorithm",
                    "override_mode",
                    "use_representative_surfaces_for_calculations"
                ]
            },
            "numerics": {
                "fields": [
                    "maxzonetempdiff",
                    "maxalloweddeltemp"
                ]
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "This object enables users to choose certain options that speed up EnergyPlus simulation, but may lead to small decreases in accuracy of results."
    }
}
```
