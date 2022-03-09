```
{
    "Refrigeration:System": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "refrigerated_case_or_walkin_or_caseandwalkinlist_name": {
                        "type": "string",
                        "note": "Enter the name of a Refrigeration:Case or Refrigeration:WalkIn object. If there is more than one refrigerated case or walk-in served by this system, enter the name of a Refrigeration:CaseAndWalkInList object. Only cases and walkins served directly by the system should be included in this list. Any cases served indirectly via a secondary chiller should NOT be included in this list",
                        "data_type": "object_list",
                        "object_list": [
                            "RefrigerationCaseAndWalkInAndListNames"
                        ]
                    },
                    "refrigeration_transfer_load_or_transferload_list_name": {
                        "type": "string",
                        "note": "Enter the name of a Refrigeration:SecondarySystem object OR a Refrigeration:Condenser:Cascade object OR, a Refrigeration:TransferLoadList object. A transfer load is identified as one which moves the load from one system to another. So if you have more than one such load (including cascade condensers and secondary loops) served by the same system, use a TransferLoadList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "RefrigerationSecondarySystemAndCascadeCondenserAndTransferLoadListNames"
                        ]
                    },
                    "refrigeration_condenser_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "RefrigerationAllTypesCondenserNames"
                        ]
                    },
                    "compressor_or_compressorlist_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "RefrigerationCompressorAndListNames"
                        ]
                    },
                    "minimum_condensing_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "related to the proper operation of the thermal expansion valves and compressors"
                    },
                    "refrigeration_system_working_fluid_type": {
                        "type": "string",
                        "note": "Fluid property data for the refrigerant must be entered. The fluid property data, including the objects: FluidProperties:Name, FluidProperties:Temperatures, FluidProperties:Saturated and FluidProperties:Superheated can be copied from the FluidPropertiesRefData.idf dataset",
                        "data_type": "object_list",
                        "object_list": [
                            "FluidNames"
                        ]
                    },
                    "suction_temperature_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "ConstantSuctionTemperature",
                            "FloatSuctionTemperature"
                        ],
                        "default": "ConstantSuctionTemperature"
                    },
                    "mechanical_subcooler_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "RefrigerationSubcoolerNames"
                        ],
                        "note": "Optional Field Recipient of refrigeration capacity, that is receives cool liquid from another refrigeration system to help meet aggregate case loads"
                    },
                    "liquid_suction_heat_exchanger_subcooler_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "RefrigerationSubcoolerNames"
                        ],
                        "note": "Optional Field Liquid Suction Heat Exchanger Name, or leave blank"
                    },
                    "sum_ua_suction_piping": {
                        "type": "number",
                        "default": 0.0,
                        "units": "W/K",
                        "note": "Use only if you want to include suction piping heat gain in refrigeration load"
                    },
                    "suction_piping_zone_name": {
                        "type": "string",
                        "note": "This will be used to determine the temperature used for distribution piping heat gain and the pipe heat gains  as cooling credit for the zone. Required only if Sum UA Distribution Piping >0.0",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                        "retaincase": true,
                        "default": "General"
                    },
                    "number_of_compressor_stages": {
                        "default": 1.0,
                        "anyOf": [
                            {
                                "type": "number",
                                "enum": [
                                    1,
                                    2
                                ]
                            },
                            {
                                "type": "string",
                                "enum": [
                                    ""
                                ]
                            }
                        ]
                    },
                    "intercooler_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Flash Intercooler",
                            "None",
                            "Shell-and-Coil Intercooler"
                        ],
                        "default": "None"
                    },
                    "shell_and_coil_intercooler_effectiveness": {
                        "type": "number",
                        "default": 0.8
                    },
                    "high_stage_compressor_or_compressorlist_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "RefrigerationCompressorAndListNames"
                        ]
                    }
                },
                "required": [
                    "refrigeration_condenser_name",
                    "compressor_or_compressorlist_name",
                    "minimum_condensing_temperature",
                    "refrigeration_system_working_fluid_type"
                ]
            }
        },
        "group": "Refrigeration",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "RefrigerationSystemNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "refrigerated_case_or_walkin_or_caseandwalkinlist_name": {
                    "field_name": "Refrigerated Case or Walkin or CaseAndWalkInList Name",
                    "field_type": "a"
                },
                "refrigeration_transfer_load_or_transferload_list_name": {
                    "field_name": "Refrigeration Transfer Load or TransferLoad List Name",
                    "field_type": "a"
                },
                "refrigeration_condenser_name": {
                    "field_name": "Refrigeration Condenser Name",
                    "field_type": "a"
                },
                "compressor_or_compressorlist_name": {
                    "field_name": "Compressor or CompressorList Name",
                    "field_type": "a"
                },
                "minimum_condensing_temperature": {
                    "field_name": "Minimum Condensing Temperature",
                    "field_type": "n"
                },
                "refrigeration_system_working_fluid_type": {
                    "field_name": "Refrigeration System Working Fluid Type",
                    "field_type": "a"
                },
                "suction_temperature_control_type": {
                    "field_name": "Suction Temperature Control Type",
                    "field_type": "a"
                },
                "mechanical_subcooler_name": {
                    "field_name": "Mechanical Subcooler Name",
                    "field_type": "a"
                },
                "liquid_suction_heat_exchanger_subcooler_name": {
                    "field_name": "Liquid Suction Heat Exchanger Subcooler Name",
                    "field_type": "a"
                },
                "sum_ua_suction_piping": {
                    "field_name": "Sum UA Suction Piping",
                    "field_type": "n"
                },
                "suction_piping_zone_name": {
                    "field_name": "Suction Piping Zone Name",
                    "field_type": "a"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                },
                "number_of_compressor_stages": {
                    "field_name": "Number of Compressor Stages",
                    "field_type": "n"
                },
                "intercooler_type": {
                    "field_name": "Intercooler Type",
                    "field_type": "a"
                },
                "shell_and_coil_intercooler_effectiveness": {
                    "field_name": "Shell-and-Coil Intercooler Effectiveness",
                    "field_type": "n"
                },
                "high_stage_compressor_or_compressorlist_name": {
                    "field_name": "High-Stage Compressor or CompressorList Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "refrigerated_case_or_walkin_or_caseandwalkinlist_name",
                "refrigeration_transfer_load_or_transferload_list_name",
                "refrigeration_condenser_name",
                "compressor_or_compressorlist_name",
                "minimum_condensing_temperature",
                "refrigeration_system_working_fluid_type",
                "suction_temperature_control_type",
                "mechanical_subcooler_name",
                "liquid_suction_heat_exchanger_subcooler_name",
                "sum_ua_suction_piping",
                "suction_piping_zone_name",
                "end_use_subcategory",
                "number_of_compressor_stages",
                "intercooler_type",
                "shell_and_coil_intercooler_effectiveness",
                "high_stage_compressor_or_compressorlist_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "refrigerated_case_or_walkin_or_caseandwalkinlist_name",
                    "refrigeration_transfer_load_or_transferload_list_name",
                    "refrigeration_condenser_name",
                    "compressor_or_compressorlist_name",
                    "refrigeration_system_working_fluid_type",
                    "suction_temperature_control_type",
                    "mechanical_subcooler_name",
                    "liquid_suction_heat_exchanger_subcooler_name",
                    "suction_piping_zone_name",
                    "end_use_subcategory",
                    "intercooler_type",
                    "high_stage_compressor_or_compressorlist_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_condensing_temperature",
                    "sum_ua_suction_piping",
                    "number_of_compressor_stages",
                    "shell_and_coil_intercooler_effectiveness"
                ]
            }
        },
        "type": "object",
        "memo": "Simulates the performance of a supermarket refrigeration system when used along with other objects to define the refrigeration load(s), the compressor(s), and the condenser.",
        "min_fields": 7.0
    }
}
```
