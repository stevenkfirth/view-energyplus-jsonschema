```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "district_heating_efficiency": {
                    "type": "number",
                    "note": "District heating efficiency used when converted to natural gas",
                    "exclusiveMinimum": 0.0,
                    "default": 0.3
                },
                "district_cooling_cop": {
                    "type": "number",
                    "note": "District cooling COP used when converted to electricity",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.0
                },
                "steam_conversion_efficiency": {
                    "type": "number",
                    "note": "Steam conversion efficiency used to convert steam usage to natural gas",
                    "exclusiveMinimum": 0.0,
                    "default": 0.25
                },
                "total_carbon_equivalent_emission_factor_from_n2o": {
                    "type": "number",
                    "units": "kg/kg",
                    "default": 80.7272
                },
                "total_carbon_equivalent_emission_factor_from_ch4": {
                    "type": "number",
                    "units": "kg/kg",
                    "default": 6.2727
                },
                "total_carbon_equivalent_emission_factor_from_co2": {
                    "type": "number",
                    "units": "kg/kg",
                    "default": 0.2727
                }
            }
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "district_heating_efficiency": {
                "field_name": "District Heating Efficiency",
                "field_type": "n"
            },
            "district_cooling_cop": {
                "field_name": "District Cooling COP",
                "field_type": "n"
            },
            "steam_conversion_efficiency": {
                "field_name": "Steam Conversion Efficiency",
                "field_type": "n"
            },
            "total_carbon_equivalent_emission_factor_from_n2o": {
                "field_name": "Total Carbon Equivalent Emission Factor From N2O",
                "field_type": "n"
            },
            "total_carbon_equivalent_emission_factor_from_ch4": {
                "field_name": "Total Carbon Equivalent Emission Factor From CH4",
                "field_type": "n"
            },
            "total_carbon_equivalent_emission_factor_from_co2": {
                "field_name": "Total Carbon Equivalent Emission Factor From CO2",
                "field_type": "n"
            }
        },
        "fields": [
            "district_heating_efficiency",
            "district_cooling_cop",
            "steam_conversion_efficiency",
            "total_carbon_equivalent_emission_factor_from_n2o",
            "total_carbon_equivalent_emission_factor_from_ch4",
            "total_carbon_equivalent_emission_factor_from_co2"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "district_heating_efficiency",
                "district_cooling_cop",
                "steam_conversion_efficiency",
                "total_carbon_equivalent_emission_factor_from_n2o",
                "total_carbon_equivalent_emission_factor_from_ch4",
                "total_carbon_equivalent_emission_factor_from_co2"
            ]
        }
    },
    "type": "object",
    "memo": "Used to help convert district and ideal energy use to a fuel type and provide total carbon equivalent with coefficients Also used in Source=>Site conversions."
}
```
