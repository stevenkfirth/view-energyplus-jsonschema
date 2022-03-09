```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "heatexchanger_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AFNHeatExchangerNames"
                    ],
                    "reference": [
                        "AirflowNetworkComponentNames"
                    ],
                    "note": "Enter the name of an air-to-air heat exchanger in the primary Air loop."
                },
                "heatexchanger_object_type": {
                    "type": "string",
                    "enum": [
                        "HeatExchanger:AirToAir:FlatPlate",
                        "HeatExchanger:AirToAir:SensibleAndLatent",
                        "HeatExchanger:Desiccant:BalancedFlow"
                    ],
                    "note": "Select the type of heat exchanger corresponding to the name entered in the field above."
                },
                "air_path_length": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Enter the air path length (depth) for the heat exchanger."
                },
                "air_path_hydraulic_diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Enter the hydraulic diameter of this heat exchanger. The hydraulic diameter is defined as 4 multiplied by the cross section area divided by perimeter."
                }
            },
            "required": [
                "heatexchanger_name",
                "heatexchanger_object_type",
                "air_path_length",
                "air_path_hydraulic_diameter"
            ]
        }
    },
    "group": "AirflowNetwork",
    "legacy_idd": {
        "field_info": {
            "heatexchanger_name": {
                "field_name": "HeatExchanger Name",
                "field_type": "a"
            },
            "heatexchanger_object_type": {
                "field_name": "HeatExchanger Object Type",
                "field_type": "a"
            },
            "air_path_length": {
                "field_name": "Air Path Length",
                "field_type": "n"
            },
            "air_path_hydraulic_diameter": {
                "field_name": "Air Path Hydraulic Diameter",
                "field_type": "n"
            }
        },
        "fields": [
            "heatexchanger_name",
            "heatexchanger_object_type",
            "air_path_length",
            "air_path_hydraulic_diameter"
        ],
        "alphas": {
            "fields": [
                "heatexchanger_name",
                "heatexchanger_object_type"
            ]
        },
        "numerics": {
            "fields": [
                "air_path_length",
                "air_path_hydraulic_diameter"
            ]
        }
    },
    "type": "object",
    "memo": "This object defines the name of an air-to-air heat exchanger used in an air loop.",
    "min_fields": 4.0
}
```
