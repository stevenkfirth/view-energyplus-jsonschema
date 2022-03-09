```
{
    "OutputControl:Files": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "output_csv": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "output_mtr": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_eso": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_eio": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_tabular": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_sqlite": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_json": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_audit": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_zone_sizing": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_system_sizing": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_dxf": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_bnd": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_rdd": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_mdd": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_mtd": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_end": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_shd": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_dfs": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_glhe": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_delightin": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_delighteldmp": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_delightdfdmp": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_edd": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_dbg": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_perflog": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_sln": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_sci": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_wrl": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_screen": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_extshd": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "output_tarcog": {
                        "type": "string",
                        "note": "Not Implemented Yet",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    }
                }
            }
        },
        "group": "Output Reporting",
        "legacy_idd": {
            "field_info": {
                "output_csv": {
                    "field_name": "Output CSV",
                    "field_type": "a"
                },
                "output_mtr": {
                    "field_name": "Output MTR",
                    "field_type": "a"
                },
                "output_eso": {
                    "field_name": "Output ESO",
                    "field_type": "a"
                },
                "output_eio": {
                    "field_name": "Output EIO",
                    "field_type": "a"
                },
                "output_tabular": {
                    "field_name": "Output Tabular",
                    "field_type": "a"
                },
                "output_sqlite": {
                    "field_name": "Output SQLite",
                    "field_type": "a"
                },
                "output_json": {
                    "field_name": "Output JSON",
                    "field_type": "a"
                },
                "output_audit": {
                    "field_name": "Output AUDIT",
                    "field_type": "a"
                },
                "output_zone_sizing": {
                    "field_name": "Output Zone Sizing",
                    "field_type": "a"
                },
                "output_system_sizing": {
                    "field_name": "Output System Sizing",
                    "field_type": "a"
                },
                "output_dxf": {
                    "field_name": "Output DXF",
                    "field_type": "a"
                },
                "output_bnd": {
                    "field_name": "Output BND",
                    "field_type": "a"
                },
                "output_rdd": {
                    "field_name": "Output RDD",
                    "field_type": "a"
                },
                "output_mdd": {
                    "field_name": "Output MDD",
                    "field_type": "a"
                },
                "output_mtd": {
                    "field_name": "Output MTD",
                    "field_type": "a"
                },
                "output_end": {
                    "field_name": "Output END",
                    "field_type": "a"
                },
                "output_shd": {
                    "field_name": "Output SHD",
                    "field_type": "a"
                },
                "output_dfs": {
                    "field_name": "Output DFS",
                    "field_type": "a"
                },
                "output_glhe": {
                    "field_name": "Output GLHE",
                    "field_type": "a"
                },
                "output_delightin": {
                    "field_name": "Output DelightIn",
                    "field_type": "a"
                },
                "output_delighteldmp": {
                    "field_name": "Output DelightELdmp",
                    "field_type": "a"
                },
                "output_delightdfdmp": {
                    "field_name": "Output DelightDFdmp",
                    "field_type": "a"
                },
                "output_edd": {
                    "field_name": "Output EDD",
                    "field_type": "a"
                },
                "output_dbg": {
                    "field_name": "Output DBG",
                    "field_type": "a"
                },
                "output_perflog": {
                    "field_name": "Output PerfLog",
                    "field_type": "a"
                },
                "output_sln": {
                    "field_name": "Output SLN",
                    "field_type": "a"
                },
                "output_sci": {
                    "field_name": "Output SCI",
                    "field_type": "a"
                },
                "output_wrl": {
                    "field_name": "Output WRL",
                    "field_type": "a"
                },
                "output_screen": {
                    "field_name": "Output Screen",
                    "field_type": "a"
                },
                "output_extshd": {
                    "field_name": "Output ExtShd",
                    "field_type": "a"
                },
                "output_tarcog": {
                    "field_name": "Output Tarcog",
                    "field_type": "a"
                }
            },
            "fields": [
                "output_csv",
                "output_mtr",
                "output_eso",
                "output_eio",
                "output_tabular",
                "output_sqlite",
                "output_json",
                "output_audit",
                "output_zone_sizing",
                "output_system_sizing",
                "output_dxf",
                "output_bnd",
                "output_rdd",
                "output_mdd",
                "output_mtd",
                "output_end",
                "output_shd",
                "output_dfs",
                "output_glhe",
                "output_delightin",
                "output_delighteldmp",
                "output_delightdfdmp",
                "output_edd",
                "output_dbg",
                "output_perflog",
                "output_sln",
                "output_sci",
                "output_wrl",
                "output_screen",
                "output_extshd",
                "output_tarcog"
            ],
            "alphas": {
                "fields": [
                    "output_csv",
                    "output_mtr",
                    "output_eso",
                    "output_eio",
                    "output_tabular",
                    "output_sqlite",
                    "output_json",
                    "output_audit",
                    "output_zone_sizing",
                    "output_system_sizing",
                    "output_dxf",
                    "output_bnd",
                    "output_rdd",
                    "output_mdd",
                    "output_mtd",
                    "output_end",
                    "output_shd",
                    "output_dfs",
                    "output_glhe",
                    "output_delightin",
                    "output_delighteldmp",
                    "output_delightdfdmp",
                    "output_edd",
                    "output_dbg",
                    "output_perflog",
                    "output_sln",
                    "output_sci",
                    "output_wrl",
                    "output_screen",
                    "output_extshd",
                    "output_tarcog"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Conditionally turn on/off output from EnergyPlus."
    }
}
```
