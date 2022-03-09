```
{
    "EnergyManagementSystem:MeteredOutputVariable": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "ems_variable_name": {
                        "type": "string",
                        "note": "must be an acceptable EMS variable, no spaces"
                    },
                    "update_frequency": {
                        "type": "string",
                        "enum": [
                            "SystemTimestep",
                            "ZoneTimestep"
                        ]
                    },
                    "ems_program_or_subroutine_name": {
                        "type": "string",
                        "note": "optional for global scope variables, required for local scope variables"
                    },
                    "resource_type": {
                        "type": "string",
                        "note": "choose the type of fuel, water, electricity, pollution or heat rate that should be metered.",
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
                        "note": "choose a general classification, building (internal services), HVAC (air systems), or plant (hydronic systems), or system",
                        "enum": [
                            "Building",
                            "HVAC",
                            "Plant",
                            "System"
                        ]
                    },
                    "end_use_category": {
                        "type": "string",
                        "note": "choose how the metered output should be classified for end-use category",
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
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table. enter a user-defined subcategory for this metered output",
                        "retaincase": true
                    },
                    "units": {
                        "type": "string",
                        "note": "optional but will result in dimensionless units for blank EnergyPlus units are standard SI units"
                    }
                },
                "required": [
                    "ems_variable_name",
                    "update_frequency",
                    "resource_type",
                    "group_type",
                    "end_use_category"
                ]
            }
        },
        "group": "Energy Management System (EMS)",
        "name": {
            "type": "string",
            "is_required": true,
            "retaincase": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "ems_variable_name": {
                    "field_name": "EMS Variable Name",
                    "field_type": "a"
                },
                "update_frequency": {
                    "field_name": "Update Frequency",
                    "field_type": "a"
                },
                "ems_program_or_subroutine_name": {
                    "field_name": "EMS Program or Subroutine Name",
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
                },
                "units": {
                    "field_name": "Units",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "ems_variable_name",
                "update_frequency",
                "ems_program_or_subroutine_name",
                "resource_type",
                "group_type",
                "end_use_category",
                "end_use_subcategory",
                "units"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "ems_variable_name",
                    "update_frequency",
                    "ems_program_or_subroutine_name",
                    "resource_type",
                    "group_type",
                    "end_use_category",
                    "end_use_subcategory",
                    "units"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object sets up an EnergyPlus output variable from an Erl variable",
        "min_fields": 7.0
    }
}
```
