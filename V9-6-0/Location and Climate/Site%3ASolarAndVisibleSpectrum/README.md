```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "spectrum_data_method": {
                    "type": "string",
                    "note": "The method specifies which of the solar and visible spectrum data to use in the calculations. Choices: Default - existing hard-wired spectrum data in EnergyPlus. UserDefined - user specified spectrum data referenced by the next two fields",
                    "enum": [
                        "",
                        "Default",
                        "UserDefined"
                    ],
                    "default": "Default"
                },
                "solar_spectrum_data_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SpectrumDataNames"
                    ]
                },
                "visible_spectrum_data_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SpectrumDataNames"
                    ]
                }
            }
        }
    },
    "group": "Location and Climate",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "spectrum_data_method": {
                "field_name": "Spectrum Data Method",
                "field_type": "a"
            },
            "solar_spectrum_data_object_name": {
                "field_name": "Solar Spectrum Data Object Name",
                "field_type": "a"
            },
            "visible_spectrum_data_object_name": {
                "field_name": "Visible Spectrum Data Object Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "spectrum_data_method",
            "solar_spectrum_data_object_name",
            "visible_spectrum_data_object_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "spectrum_data_method",
                "solar_spectrum_data_object_name",
                "visible_spectrum_data_object_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "If this object is omitted, the default solar and visible spectrum data will be used."
}
```
