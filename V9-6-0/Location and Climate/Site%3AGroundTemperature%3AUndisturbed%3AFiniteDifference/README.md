```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "soil_thermal_conductivity": {
                    "type": "number",
                    "units": "W/m-K",
                    "exclusiveMinimum": 0.0
                },
                "soil_density": {
                    "type": "number",
                    "units": "kg/m3",
                    "exclusiveMinimum": 0.0
                },
                "soil_specific_heat": {
                    "type": "number",
                    "units": "J/kg-K",
                    "exclusiveMinimum": 0.0
                },
                "soil_moisture_content_volume_fraction": {
                    "type": "number",
                    "units": "percent",
                    "minimum": 0.0,
                    "maximum": 100.0,
                    "default": 30.0
                },
                "soil_moisture_content_volume_fraction_at_saturation": {
                    "type": "number",
                    "units": "percent",
                    "minimum": 0.0,
                    "maximum": 100.0,
                    "default": 50.0
                },
                "evapotranspiration_ground_cover_parameter": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.5,
                    "default": 0.4,
                    "note": "This specifies the ground cover effects during evapotranspiration calculations. The value roughly represents the following cases: = 0   : concrete or other solid, non-permeable ground surface material = 0.5 : short grass, much like a manicured lawn = 1   : standard reference state (12 cm grass) = 1.5 : wild growth"
                }
            },
            "required": [
                "soil_thermal_conductivity",
                "soil_density",
                "soil_specific_heat"
            ]
        }
    },
    "group": "Location and Climate",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "UndisturbedGroundTempModels"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "soil_thermal_conductivity": {
                "field_name": "Soil Thermal Conductivity",
                "field_type": "n"
            },
            "soil_density": {
                "field_name": "Soil Density",
                "field_type": "n"
            },
            "soil_specific_heat": {
                "field_name": "Soil Specific Heat",
                "field_type": "n"
            },
            "soil_moisture_content_volume_fraction": {
                "field_name": "Soil Moisture Content Volume Fraction",
                "field_type": "n"
            },
            "soil_moisture_content_volume_fraction_at_saturation": {
                "field_name": "Soil Moisture Content Volume Fraction at Saturation",
                "field_type": "n"
            },
            "evapotranspiration_ground_cover_parameter": {
                "field_name": "Evapotranspiration Ground Cover Parameter",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "soil_thermal_conductivity",
            "soil_density",
            "soil_specific_heat",
            "soil_moisture_content_volume_fraction",
            "soil_moisture_content_volume_fraction_at_saturation",
            "evapotranspiration_ground_cover_parameter"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "soil_thermal_conductivity",
                "soil_density",
                "soil_specific_heat",
                "soil_moisture_content_volume_fraction",
                "soil_moisture_content_volume_fraction_at_saturation",
                "evapotranspiration_ground_cover_parameter"
            ]
        }
    },
    "type": "object",
    "memo": "Undisturbed ground temperature object using a detailed finite difference 1-D model",
    "min_fields": 7.0
}
```
