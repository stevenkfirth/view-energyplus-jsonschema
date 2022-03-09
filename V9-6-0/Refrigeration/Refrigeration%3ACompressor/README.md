```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "refrigeration_compressor_power_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "the input order for the Curve:Bicubic does not match the ARI 540-2004 Eq. 1 coefficient order N1 is ARI_C1, N2 is ARI_C2, N3 is ARI_C4, N4 is ARI_C3, N5 is ARI_C6, N6 is ARI_C5, N7 is ARI_C7, N8 is ARI_C10, N9 is ARI_C8, N10 is ARI_C9, N11 is Minimum Suction dewpoint temperature, N12 is Maximum Suction dewpoint temperature, N13 is Minimum Discharge dewpoint temperature, N14 is Maximum Discharge dewpoint temperature"
                },
                "refrigeration_compressor_capacity_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "the input order for the Curve:Bicubic does not match the ARI 540-2004 Eq. 1 coefficient order N1 is ARI_C1, N2 is ARI_C2, N3 is ARI_C4, N4 is ARI_C3, N5 is ARI_C6, N6 is ARI_C5, N7 is ARI_C7, N8 is ARI_C10, N9 is ARI_C8, N10 is ARI_C9, N11 is Minimum Suction dewpoint temperature, N12 is Maximum Suction dewpoint temperature, N13 is Minimum Discharge dewpoint temperature, N14 is Maximum Discharge dewpoint temperature"
                },
                "rated_superheat": {
                    "type": "number",
                    "units": "deltaC",
                    "note": "Use this input field OR the next, not both This is used if the compressor rating is based upon degrees of superheat"
                },
                "rated_return_gas_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "Use this input field OR the previous, not both This is used if the compressor rating is based upon rated return gas temperature (Rated Suction Temperature)"
                },
                "rated_liquid_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "Use this input field OR the next, not both This is used if the compressor rating is based upon rated liquid temperature at the expansion valve"
                },
                "rated_subcooling": {
                    "type": "number",
                    "units": "deltaC",
                    "note": "Use this input field OR the previous, not both This is used if the compressor rating is based upon degrees of subcooling"
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                },
                "mode_of_operation": {
                    "type": "string",
                    "retaincase": true,
                    "enum": [
                        "",
                        "Subcritical",
                        "Transcritical"
                    ],
                    "default": "Subcritical"
                },
                "transcritical_compressor_power_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "transcritical_compressor_capacity_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                }
            },
            "required": [
                "refrigeration_compressor_power_curve_name",
                "refrigeration_compressor_capacity_curve_name"
            ]
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "RefrigerationCompressorAndListNames",
            "RefrigerationCompressorNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "refrigeration_compressor_power_curve_name": {
                "field_name": "Refrigeration Compressor Power Curve Name",
                "field_type": "a"
            },
            "refrigeration_compressor_capacity_curve_name": {
                "field_name": "Refrigeration Compressor Capacity Curve Name",
                "field_type": "a"
            },
            "rated_superheat": {
                "field_name": "Rated Superheat",
                "field_type": "n"
            },
            "rated_return_gas_temperature": {
                "field_name": "Rated Return Gas Temperature",
                "field_type": "n"
            },
            "rated_liquid_temperature": {
                "field_name": "Rated Liquid Temperature",
                "field_type": "n"
            },
            "rated_subcooling": {
                "field_name": "Rated Subcooling",
                "field_type": "n"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            },
            "mode_of_operation": {
                "field_name": "Mode of Operation",
                "field_type": "a"
            },
            "transcritical_compressor_power_curve_name": {
                "field_name": "Transcritical Compressor Power Curve Name",
                "field_type": "a"
            },
            "transcritical_compressor_capacity_curve_name": {
                "field_name": "Transcritical Compressor Capacity Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "refrigeration_compressor_power_curve_name",
            "refrigeration_compressor_capacity_curve_name",
            "rated_superheat",
            "rated_return_gas_temperature",
            "rated_liquid_temperature",
            "rated_subcooling",
            "end_use_subcategory",
            "mode_of_operation",
            "transcritical_compressor_power_curve_name",
            "transcritical_compressor_capacity_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "refrigeration_compressor_power_curve_name",
                "refrigeration_compressor_capacity_curve_name",
                "end_use_subcategory",
                "mode_of_operation",
                "transcritical_compressor_power_curve_name",
                "transcritical_compressor_capacity_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "rated_superheat",
                "rated_return_gas_temperature",
                "rated_liquid_temperature",
                "rated_subcooling"
            ]
        }
    },
    "type": "object",
    "memo": "Refrigeration system compressor. Data is available for many compressors in the RefrigerationCompressor.idf dataset",
    "min_fields": 6.0
}
```
