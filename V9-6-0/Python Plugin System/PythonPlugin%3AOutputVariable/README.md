```
{
    "PythonPlugin:OutputVariable": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "python_plugin_variable_name": {
                        "type": "string",
                        "note": "Must be listed in the PythonPlugin:Variables object"
                    },
                    "type_of_data_in_variable": {
                        "type": "string",
                        "enum": [
                            "Averaged",
                            "Metered",
                            "Summed"
                        ],
                        "note": "If Metered is selected, the variable is automatically set to a \"Summed\" type, and the Resource Type, Group Type, and End-Use Subcategory fields on this object are required"
                    },
                    "update_frequency": {
                        "type": "string",
                        "enum": [
                            "SystemTimestep",
                            "ZoneTimestep"
                        ]
                    },
                    "units": {
                        "type": "string",
                        "note": "optional but will result in dimensionless units for blank EnergyPlus units are standard SI units"
                    },
                    "resource_type": {
                        "type": "string",
                        "note": "This field is optional for regular output variables with \"Type of Data in Variable\" set to either Averaged or Summed. For Metered variables, this field is required. Choose the type of fuel, water, electricity, pollution or heat rate that should be metered.",
                        "enum": [
                            "Coal",
                            "CondensateWaterCollected",
                            "Diesel",
                            "DistrictCooling",
                            "DistrictHeating",
                            "Electricity",
                            "ElectricityProducedOnSite",
                            "EnergyTransfer",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "MainsWaterSupply",
                            "NaturalGas",
                            "OnSiteWaterProduced",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane",
                            "RainWaterCollected",
                            "SolarAirHeating",
                            "SolarWaterHeating",
                            "Steam",
                            "WaterUse",
                            "WellWaterDrawn"
                        ]
                    },
                    "group_type": {
                        "type": "string",
                        "note": "This field is optional for regular output variables with \"Type of Data in Variable\" set to either Averaged or Summed. For Metered variables, this field is required. Choose a general classification, building (internal services), HVAC (air systems), or plant (hydronic systems), or system",
                        "enum": [
                            "Building",
                            "HVAC",
                            "Plant",
                            "System"
                        ]
                    },
                    "end_use_category": {
                        "type": "string",
                        "note": "This field is optional for regular output variables with \"Type of Data in Variable\" set to either Averaged or Summed. For Metered variables, this field is required. Choose how the metered output should be classified for end-use category",
                        "enum": [
                            "Baseboard",
                            "Boilers",
                            "Chillers",
                            "Cooling",
                            "CoolingCoils",
                            "ExteriorEquipment",
                            "ExteriorLights",
                            "Fans",
                            "HeatRecovery",
                            "HeatRecoveryForCooling",
                            "HeatRecoveryForHeating",
                            "HeatRejection",
                            "Heating",
                            "HeatingCoils",
                            "Humidifier",
                            "InteriorEquipment",
                            "InteriorLights",
                            "OnSiteGeneration",
                            "Pumps",
                            "Refrigeration",
                            "WaterSystems"
                        ]
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "This field is always optional. For regular output variables with \"Type of Data in Variable\" set to either Averaged or Summed, this field is completely ignored. For Metered variables, this field is optional, but allows custom categorization of the end-uses in the ABUPS End Uses by Subcategory table. Enter a user-defined subcategory for this metered output",
                        "retaincase": true
                    }
                },
                "required": [
                    "python_plugin_variable_name",
                    "type_of_data_in_variable",
                    "update_frequency"
                ]
            }
        },
        "group": "Python Plugin System",
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
                "python_plugin_variable_name": {
                    "field_name": "Python Plugin Variable Name",
                    "field_type": "a"
                },
                "type_of_data_in_variable": {
                    "field_name": "Type of Data in Variable",
                    "field_type": "a"
                },
                "update_frequency": {
                    "field_name": "Update Frequency",
                    "field_type": "a"
                },
                "units": {
                    "field_name": "Units",
                    "field_type": "a"
                },
                "resource_type": {
                    "field_name": "Resource Type",
                    "field_type": "a"
                },
                "group_type": {
                    "field_name": "Group Type",
                    "field_type": "a"
                },
                "end_use_category": {
                    "field_name": "End-Use Category",
                    "field_type": "a"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "python_plugin_variable_name",
                "type_of_data_in_variable",
                "update_frequency",
                "units",
                "resource_type",
                "group_type",
                "end_use_category",
                "end_use_subcategory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "python_plugin_variable_name",
                    "type_of_data_in_variable",
                    "update_frequency",
                    "units",
                    "resource_type",
                    "group_type",
                    "end_use_category",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object sets up an EnergyPlus output variable from a Python Plugin variable",
        "min_fields": 4.0
    }
}
```
