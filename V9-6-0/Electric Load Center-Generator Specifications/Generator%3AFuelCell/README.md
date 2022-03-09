```
{
    "Generator:FuelCell": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "power_module_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:FuelCell:PowerModule object.",
                        "data_type": "object_list",
                        "object_list": [
                            "FCPMNames"
                        ]
                    },
                    "air_supply_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:FuelCell:AirSupply object.",
                        "data_type": "object_list",
                        "object_list": [
                            "FCAirSupNames"
                        ]
                    },
                    "fuel_supply_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:FuelSupply object.",
                        "data_type": "object_list",
                        "object_list": [
                            "GenFuelSupNames"
                        ]
                    },
                    "water_supply_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:FuelCell:WaterSupply object.",
                        "data_type": "object_list",
                        "object_list": [
                            "FCWaterSupNames"
                        ]
                    },
                    "auxiliary_heater_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:FuelCell:AuxiliaryHeater object.",
                        "data_type": "object_list",
                        "object_list": [
                            "FCAuxHeatNames"
                        ]
                    },
                    "heat_exchanger_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:FuelCell:ExhaustGasToWaterHeatExchanger object.",
                        "data_type": "object_list",
                        "object_list": [
                            "FCExhaustHXNames"
                        ]
                    },
                    "electrical_storage_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:FuelCell:ElectricalStorage object.",
                        "data_type": "object_list",
                        "object_list": [
                            "FCStorageNames"
                        ]
                    },
                    "inverter_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:FuelCell:Inverter object.",
                        "data_type": "object_list",
                        "object_list": [
                            "FCInverterNames"
                        ]
                    },
                    "stack_cooler_name": {
                        "type": "string",
                        "note": "Enter the name of a Generator:FuelCell:StackCooler object. optional, used for PEMFC",
                        "data_type": "object_list",
                        "object_list": [
                            "FCStackCoolerNames"
                        ]
                    }
                },
                "required": [
                    "power_module_name",
                    "air_supply_name",
                    "fuel_supply_name",
                    "water_supply_name",
                    "auxiliary_heater_name",
                    "heat_exchanger_name",
                    "electrical_storage_name",
                    "inverter_name"
                ]
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "GeneratorNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "power_module_name": {
                    "field_name": "Power Module Name",
                    "field_type": "a"
                },
                "air_supply_name": {
                    "field_name": "Air Supply Name",
                    "field_type": "a"
                },
                "fuel_supply_name": {
                    "field_name": "Fuel Supply Name",
                    "field_type": "a"
                },
                "water_supply_name": {
                    "field_name": "Water Supply Name",
                    "field_type": "a"
                },
                "auxiliary_heater_name": {
                    "field_name": "Auxiliary Heater Name",
                    "field_type": "a"
                },
                "heat_exchanger_name": {
                    "field_name": "Heat Exchanger Name",
                    "field_type": "a"
                },
                "electrical_storage_name": {
                    "field_name": "Electrical Storage Name",
                    "field_type": "a"
                },
                "inverter_name": {
                    "field_name": "Inverter Name",
                    "field_type": "a"
                },
                "stack_cooler_name": {
                    "field_name": "Stack Cooler Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "power_module_name",
                "air_supply_name",
                "fuel_supply_name",
                "water_supply_name",
                "auxiliary_heater_name",
                "heat_exchanger_name",
                "electrical_storage_name",
                "inverter_name",
                "stack_cooler_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "power_module_name",
                    "air_supply_name",
                    "fuel_supply_name",
                    "water_supply_name",
                    "auxiliary_heater_name",
                    "heat_exchanger_name",
                    "electrical_storage_name",
                    "inverter_name",
                    "stack_cooler_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This generator model is the FC model from IEA Annex 42"
    }
}
```
