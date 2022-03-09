```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "dc_to_ac_size_ratio": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 1.1
                },
                "inverter_efficiency": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.96
                }
            }
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "reference": [
            "InverterList"
        ]
    },
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "dc_to_ac_size_ratio": {
                "field_name": "DC to AC Size Ratio",
                "field_type": "n"
            },
            "inverter_efficiency": {
                "field_name": "Inverter Efficiency",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "dc_to_ac_size_ratio",
            "inverter_efficiency"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "dc_to_ac_size_ratio",
                "inverter_efficiency"
            ]
        }
    },
    "type": "object",
    "memo": "Electric power inverter to convert from direct current (DC) to alternating current (AC) in an electric load center that contains Generator:PVWatts objects. It implements the PVWatts inverter performance curves.",
    "min_fields": 1.0
}
```
