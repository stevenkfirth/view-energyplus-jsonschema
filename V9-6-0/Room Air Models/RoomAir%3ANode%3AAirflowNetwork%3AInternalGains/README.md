```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "gains": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "internal_gain_object_type": {
                                "type": "string",
                                "enum": [
                                    "AirTerminal:SingleDuct:UserDefined",
                                    "Coil:UserDefined",
                                    "DaylightingDevice:Tubular",
                                    "ElectricEquipment",
                                    "ElectricLoadCenter:Inverter:FunctionOfPower",
                                    "ElectricLoadCenter:Inverter:LookUpTable",
                                    "ElectricLoadCenter:Inverter:Simple",
                                    "ElectricLoadCenter:Storage:Battery",
                                    "ElectricLoadCenter:Storage:Converter",
                                    "ElectricLoadCenter:Storage:LiIonNMCBattery",
                                    "ElectricLoadCenter:Storage:Simple",
                                    "ElectricLoadCenter:Transformer",
                                    "GasEquipment",
                                    "Generator:FuelCell",
                                    "Generator:MicroCHP",
                                    "HeaderedPumps:ConstantSpeed",
                                    "HeaderedPumps:VariableSpeed",
                                    "HotWaterEquipment",
                                    "Lights",
                                    "OtherEquipment",
                                    "People",
                                    "Pipe:Indoor",
                                    "PlantComponent:UserDefined",
                                    "Pump:ConstantSpeed",
                                    "Pump:VariableSpeed",
                                    "Pump:VariableSpeed:Condensate",
                                    "Refrigeration:Case",
                                    "Refrigeration:CompressorRack",
                                    "Refrigeration:SecondarySystem:Pipe",
                                    "Refrigeration:SecondarySystem:Receiver",
                                    "Refrigeration:System:Condenser:AirCooled",
                                    "Refrigeration:System:SuctionPipe",
                                    "Refrigeration:TranscriticalSystem:GasCooler:AirCooled",
                                    "Refrigeration:TranscriticalSystem:SuctionPipeLT",
                                    "Refrigeration:TranscriticalSystem:SuctionPipeMT",
                                    "Refrigeration:WalkIn",
                                    "SteamEquipment",
                                    "ThermalStorage:ChilledWater:Mixed",
                                    "ThermalStorage:ChilledWater:Stratified",
                                    "WaterHeater:Mixed",
                                    "WaterHeater:Stratified",
                                    "WaterUse:Equipment",
                                    "ZoneBaseboard:OutdoorTemperatureControlled",
                                    "ZoneContaminantSourceAndSink:CarbonDioxide",
                                    "ZoneContaminantSourceAndSink:GenericContaminant",
                                    "ZoneHVAC:ForcedAir:UserDefined"
                                ]
                            },
                            "internal_gain_object_name": {
                                "type": "string"
                            },
                            "fraction_of_gains_to_node": {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0,
                                "note": "fraction applies to sensible, latent, carbon dioxide, and generic contaminant gains or losses"
                            }
                        },
                        "type": "object"
                    }
                }
            }
        }
    },
    "group": "Room Air Models",
    "name": {
        "type": "string",
        "reference": [
            "RoomAirNodeGains"
        ]
    },
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "internal_gain_object_type": {
                "field_name": "Internal Gain Object Type",
                "field_type": "a"
            },
            "internal_gain_object_name": {
                "field_name": "Internal Gain Object Name",
                "field_type": "a"
            },
            "fraction_of_gains_to_node": {
                "field_name": "Fraction of Gains to Node",
                "field_type": "n"
            }
        },
        "fields": [
            "name"
        ],
        "alphas": {
            "fields": [
                "name"
            ],
            "extensions": [
                "internal_gain_object_type",
                "internal_gain_object_name"
            ]
        },
        "numerics": {
            "fields": [],
            "extensions": [
                "fraction_of_gains_to_node"
            ]
        },
        "extensibles": [
            "internal_gain_object_type",
            "internal_gain_object_name",
            "fraction_of_gains_to_node"
        ],
        "extension": "gains"
    },
    "type": "object",
    "memo": "define the internal gains that are associated with one particular RoomAir:Node",
    "min_fields": 4.0,
    "extensible_size": 3.0
}
```
