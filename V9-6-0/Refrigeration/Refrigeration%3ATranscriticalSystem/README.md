```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "system_type": {
                    "type": "string",
                    "enum": [
                        "SingleStage",
                        "TwoStage"
                    ]
                },
                "medium_temperature_refrigerated_case_or_walkin_or_caseandwalkinlist_name": {
                    "type": "string",
                    "note": "Enter the name of a Refrigeration:Case or Refrigeration:WalkIn object. If there is more than one refrigerated case or walk-in served by this system, enter the name of a Refrigeration:CaseAndWalkInList object. Only medium temperature cases and walk-ins served directly by the system should be included in this list.",
                    "data_type": "object_list",
                    "object_list": [
                        "RefrigerationCaseAndWalkInAndListNames"
                    ]
                },
                "low_temperature_refrigerated_case_or_walkin_or_caseandwalkinlist_name": {
                    "type": "string",
                    "note": "Enter the name of a Refrigeration:Case or Refrigeration:WalkIn object. If there is more than one refrigerated case or walk-in served by this system, enter the name of a Refrigeration:CaseAndWalkInList object. Only low temperature cases and walkins served directly by the system should be included in this list.",
                    "data_type": "object_list",
                    "object_list": [
                        "RefrigerationCaseAndWalkInAndListNames"
                    ]
                },
                "refrigeration_gas_cooler_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "RefrigerationAllTypesGasCoolerNames"
                    ]
                },
                "high_pressure_compressor_or_compressorlist_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "RefrigerationCompressorAndListNames"
                    ]
                },
                "low_pressure_compressor_or_compressorlist_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "RefrigerationCompressorAndListNames"
                    ]
                },
                "receiver_pressure": {
                    "type": "number",
                    "default": 4000000.0,
                    "units": "Pa"
                },
                "subcooler_effectiveness": {
                    "type": "number",
                    "default": 0.4
                },
                "refrigeration_system_working_fluid_type": {
                    "type": "string",
                    "note": "Fluid property data for the refrigerant must be entered. The fluid property data, including the objects: FluidProperties:Name, FluidProperties:Temperatures, FluidProperties:Saturated and FluidProperties:Superheated can be copied from the FluidPropertiesRefData.idf dataset",
                    "data_type": "object_list",
                    "object_list": [
                        "FluidNames"
                    ]
                },
                "sum_ua_suction_piping_for_medium_temperature_loads": {
                    "type": "number",
                    "default": 0.0,
                    "units": "W/K",
                    "note": "Use only if you want to include suction piping heat gain in refrigeration load"
                },
                "medium_temperature_suction_piping_zone_name": {
                    "type": "string",
                    "note": "This will be used to determine the temperature used for distribution piping heat gain and the pipe heat gains as cooling credit for the zone. Required only if Sum UA Distribution Piping for Medium Temperature Loads > 0.0",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "sum_ua_suction_piping_for_low_temperature_loads": {
                    "type": "number",
                    "default": 0.0,
                    "units": "W/K",
                    "note": "Use only if you want to include suction piping heat gain in refrigeration load"
                },
                "low_temperature_suction_piping_zone_name": {
                    "type": "string",
                    "note": "This will be used to determine the temperature used for distribution piping heat gain and the pipe heat gains as cooling credit for the zone. Required only if Sum UA Distribution Piping for Low Temperature Loads > 0.0",
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
                }
            },
            "required": [
                "system_type",
                "medium_temperature_refrigerated_case_or_walkin_or_caseandwalkinlist_name",
                "refrigeration_gas_cooler_name",
                "high_pressure_compressor_or_compressorlist_name",
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
            "system_type": {
                "field_name": "System Type",
                "field_type": "a"
            },
            "medium_temperature_refrigerated_case_or_walkin_or_caseandwalkinlist_name": {
                "field_name": "Medium Temperature Refrigerated Case or Walkin or CaseAndWalkInList Name",
                "field_type": "a"
            },
            "low_temperature_refrigerated_case_or_walkin_or_caseandwalkinlist_name": {
                "field_name": "Low Temperature Refrigerated Case or Walkin or CaseAndWalkInList Name",
                "field_type": "a"
            },
            "refrigeration_gas_cooler_name": {
                "field_name": "Refrigeration Gas Cooler Name",
                "field_type": "a"
            },
            "high_pressure_compressor_or_compressorlist_name": {
                "field_name": "High Pressure Compressor or CompressorList Name",
                "field_type": "a"
            },
            "low_pressure_compressor_or_compressorlist_name": {
                "field_name": "Low Pressure Compressor or CompressorList Name",
                "field_type": "a"
            },
            "receiver_pressure": {
                "field_name": "Receiver Pressure",
                "field_type": "n"
            },
            "subcooler_effectiveness": {
                "field_name": "Subcooler Effectiveness",
                "field_type": "n"
            },
            "refrigeration_system_working_fluid_type": {
                "field_name": "Refrigeration System Working Fluid Type",
                "field_type": "a"
            },
            "sum_ua_suction_piping_for_medium_temperature_loads": {
                "field_name": "Sum UA Suction Piping for Medium Temperature Loads",
                "field_type": "n"
            },
            "medium_temperature_suction_piping_zone_name": {
                "field_name": "Medium Temperature Suction Piping Zone Name",
                "field_type": "a"
            },
            "sum_ua_suction_piping_for_low_temperature_loads": {
                "field_name": "Sum UA Suction Piping for Low Temperature Loads",
                "field_type": "n"
            },
            "low_temperature_suction_piping_zone_name": {
                "field_name": "Low Temperature Suction Piping Zone Name",
                "field_type": "a"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "system_type",
            "medium_temperature_refrigerated_case_or_walkin_or_caseandwalkinlist_name",
            "low_temperature_refrigerated_case_or_walkin_or_caseandwalkinlist_name",
            "refrigeration_gas_cooler_name",
            "high_pressure_compressor_or_compressorlist_name",
            "low_pressure_compressor_or_compressorlist_name",
            "receiver_pressure",
            "subcooler_effectiveness",
            "refrigeration_system_working_fluid_type",
            "sum_ua_suction_piping_for_medium_temperature_loads",
            "medium_temperature_suction_piping_zone_name",
            "sum_ua_suction_piping_for_low_temperature_loads",
            "low_temperature_suction_piping_zone_name",
            "end_use_subcategory"
        ],
        "alphas": {
            "fields": [
                "name",
                "system_type",
                "medium_temperature_refrigerated_case_or_walkin_or_caseandwalkinlist_name",
                "low_temperature_refrigerated_case_or_walkin_or_caseandwalkinlist_name",
                "refrigeration_gas_cooler_name",
                "high_pressure_compressor_or_compressorlist_name",
                "low_pressure_compressor_or_compressorlist_name",
                "refrigeration_system_working_fluid_type",
                "medium_temperature_suction_piping_zone_name",
                "low_temperature_suction_piping_zone_name",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "receiver_pressure",
                "subcooler_effectiveness",
                "sum_ua_suction_piping_for_medium_temperature_loads",
                "sum_ua_suction_piping_for_low_temperature_loads"
            ]
        }
    },
    "type": "object",
    "memo": "Detailed transcritical carbon dioxide (CO2) booster refrigeration systems used in supermarkets. The object allows for modeling either a single stage system with medium-temperature loads or a two stage system with both medium- and low-temperature loads."
}
```
