```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "reference": [
                        "AirflowNetworkComponentNames"
                    ],
                    "object_list": [
                        "AFNCoilNames"
                    ],
                    "note": "Enter the name of a cooling or heating coil in the primary Air loop."
                },
                "coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:DX",
                        "Coil:Cooling:DX:MultiSpeed",
                        "Coil:Cooling:DX:SingleSpeed",
                        "Coil:Cooling:DX:TwoSpeed",
                        "Coil:Cooling:DX:TwoStageWithHumidityControlMode",
                        "Coil:Cooling:Water",
                        "Coil:Cooling:Water:DetailedGeometry",
                        "Coil:Heating:DX:MultiSpeed",
                        "Coil:Heating:DX:SingleSpeed",
                        "Coil:Heating:Desuperheater",
                        "Coil:Heating:Electric",
                        "Coil:Heating:Fuel",
                        "Coil:Heating:Water"
                    ],
                    "note": "Select the type of coil corresponding to the name entered in the field above."
                },
                "air_path_length": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Enter the air path length (depth) for the coil."
                },
                "air_path_hydraulic_diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Enter the hydraulic diameter of this coil. The hydraulic diameter is defined as 4 multiplied by the cross section area divided by perimeter."
                }
            },
            "required": [
                "coil_name",
                "coil_object_type",
                "air_path_length",
                "air_path_hydraulic_diameter"
            ]
        }
    },
    "group": "AirflowNetwork",
    "legacy_idd": {
        "field_info": {
            "coil_name": {
                "field_name": "Coil Name",
                "field_type": "a"
            },
            "coil_object_type": {
                "field_name": "Coil Object Type",
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
            "coil_name",
            "coil_object_type",
            "air_path_length",
            "air_path_hydraulic_diameter"
        ],
        "alphas": {
            "fields": [
                "coil_name",
                "coil_object_type"
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
    "memo": "This object defines the name of a coil used in an air loop.",
    "min_fields": 4.0
}
```
