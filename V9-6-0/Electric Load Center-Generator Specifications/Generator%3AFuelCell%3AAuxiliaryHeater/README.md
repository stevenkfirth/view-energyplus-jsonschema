```
{
    "Generator:FuelCell:AuxiliaryHeater": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "excess_air_ratio": {
                        "type": "number"
                    },
                    "ancillary_power_constant_term": {
                        "type": "number"
                    },
                    "ancillary_power_linear_term": {
                        "type": "number"
                    },
                    "skin_loss_u_factor_times_area_value": {
                        "type": "number",
                        "units": "W/K"
                    },
                    "skin_loss_destination": {
                        "type": "string",
                        "enum": [
                            "AirInletForFuelCell",
                            "SurroundingZone"
                        ]
                    },
                    "zone_name_to_receive_skin_losses": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "heating_capacity_units": {
                        "type": "string",
                        "enum": [
                            "Watts",
                            "kmol/s"
                        ]
                    },
                    "maximum_heating_capacity_in_watts": {
                        "type": "number",
                        "units": "W"
                    },
                    "minimum_heating_capacity_in_watts": {
                        "type": "number",
                        "units": "W"
                    },
                    "maximum_heating_capacity_in_kmol_per_second": {
                        "type": "number",
                        "units": "kmol/s"
                    },
                    "minimum_heating_capacity_in_kmol_per_second": {
                        "type": "number",
                        "units": "kmol/s"
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "FCAuxHeatNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "excess_air_ratio": {
                    "field_name": "Excess Air Ratio",
                    "field_type": "n"
                },
                "ancillary_power_constant_term": {
                    "field_name": "Ancillary Power Constant Term",
                    "field_type": "n"
                },
                "ancillary_power_linear_term": {
                    "field_name": "Ancillary Power Linear Term",
                    "field_type": "n"
                },
                "skin_loss_u_factor_times_area_value": {
                    "field_name": "Skin Loss U-Factor Times Area Value",
                    "field_type": "n"
                },
                "skin_loss_destination": {
                    "field_name": "Skin Loss Destination",
                    "field_type": "a"
                },
                "zone_name_to_receive_skin_losses": {
                    "field_name": "Zone Name to Receive Skin Losses",
                    "field_type": "a"
                },
                "heating_capacity_units": {
                    "field_name": "Heating Capacity Units",
                    "field_type": "a"
                },
                "maximum_heating_capacity_in_watts": {
                    "field_name": "Maximum Heating Capacity in Watts",
                    "field_type": "n"
                },
                "minimum_heating_capacity_in_watts": {
                    "field_name": "Minimum Heating Capacity in Watts",
                    "field_type": "n"
                },
                "maximum_heating_capacity_in_kmol_per_second": {
                    "field_name": "Maximum Heating Capacity in Kmol per Second",
                    "field_type": "n"
                },
                "minimum_heating_capacity_in_kmol_per_second": {
                    "field_name": "Minimum Heating Capacity in Kmol per Second",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "excess_air_ratio",
                "ancillary_power_constant_term",
                "ancillary_power_linear_term",
                "skin_loss_u_factor_times_area_value",
                "skin_loss_destination",
                "zone_name_to_receive_skin_losses",
                "heating_capacity_units",
                "maximum_heating_capacity_in_watts",
                "minimum_heating_capacity_in_watts",
                "maximum_heating_capacity_in_kmol_per_second",
                "minimum_heating_capacity_in_kmol_per_second"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "skin_loss_destination",
                    "zone_name_to_receive_skin_losses",
                    "heating_capacity_units"
                ]
            },
            "numerics": {
                "fields": [
                    "excess_air_ratio",
                    "ancillary_power_constant_term",
                    "ancillary_power_linear_term",
                    "skin_loss_u_factor_times_area_value",
                    "maximum_heating_capacity_in_watts",
                    "minimum_heating_capacity_in_watts",
                    "maximum_heating_capacity_in_kmol_per_second",
                    "minimum_heating_capacity_in_kmol_per_second"
                ]
            }
        },
        "type": "object",
        "memo": "Intended for modeling an auxiliary heater for a fuel cell power generator, however this portion of the model is not yet available. The program still requires one of these objects be included even though the data are not yet used (so that internal data structures can be allocated)."
    }
}
```
