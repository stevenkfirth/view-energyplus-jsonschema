```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "reference_temperature_for_convection_heat_transfer": {
                    "type": "string",
                    "note": "Controls which temperature is differenced from surface temperature when using the Hc value",
                    "enum": [
                        "AdjacentAirTemperature",
                        "MeanAirTemperature",
                        "SupplyAirTemperature"
                    ]
                },
                "hc_function_of_temperature_difference_curve_name": {
                    "type": "string",
                    "note": "Curve's \"x\" is absolute value of delta-T (Surface temperature minus reference temperature, (C))",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "hc_function_of_temperature_difference_divided_by_height_curve_name": {
                    "type": "string",
                    "note": "Curve's \"x\" is absolute value of delta-T/Height (Surface temp minus Air temp)/(vertical length scale), (C/m) when used for an inside face the vertical length scale is the zone's interior height",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "hc_function_of_air_change_rate_curve_name": {
                    "type": "string",
                    "note": "Curve's \"x\" is mechanical ACH (Air Changes per hour from mechanical air system), (1/hr)",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "hc_function_of_air_system_volume_flow_rate_divided_by_zone_perimeter_length_curve_name": {
                    "type": "string",
                    "note": "Curve's \"x\" is mechanical system air flow rate (m3/s) divided by zone's length along exterior walls (m).",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                }
            }
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "name": {
        "type": "string",
        "reference": [
            "UserConvectionInsideModels",
            "UserConvectionModels"
        ]
    },
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "reference_temperature_for_convection_heat_transfer": {
                "field_name": "Reference Temperature for Convection Heat Transfer",
                "field_type": "a"
            },
            "hc_function_of_temperature_difference_curve_name": {
                "field_name": "Hc Function of Temperature Difference Curve Name",
                "field_type": "a"
            },
            "hc_function_of_temperature_difference_divided_by_height_curve_name": {
                "field_name": "Hc Function of Temperature Difference Divided by Height Curve Name",
                "field_type": "a"
            },
            "hc_function_of_air_change_rate_curve_name": {
                "field_name": "Hc Function of Air Change Rate Curve Name",
                "field_type": "a"
            },
            "hc_function_of_air_system_volume_flow_rate_divided_by_zone_perimeter_length_curve_name": {
                "field_name": "Hc Function of Air System Volume Flow Rate Divided by Zone Perimeter Length Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "reference_temperature_for_convection_heat_transfer",
            "hc_function_of_temperature_difference_curve_name",
            "hc_function_of_temperature_difference_divided_by_height_curve_name",
            "hc_function_of_air_change_rate_curve_name",
            "hc_function_of_air_system_volume_flow_rate_divided_by_zone_perimeter_length_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "reference_temperature_for_convection_heat_transfer",
                "hc_function_of_temperature_difference_curve_name",
                "hc_function_of_temperature_difference_divided_by_height_curve_name",
                "hc_function_of_air_change_rate_curve_name",
                "hc_function_of_air_system_volume_flow_rate_divided_by_zone_perimeter_length_curve_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Used to describe a custom model equation for surface convection heat transfer coefficient If more than one curve is referenced they are all used and added together."
}
```
