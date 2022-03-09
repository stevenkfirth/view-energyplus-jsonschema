```
{
    "RoomAir:Node:AirflowNetwork:HVACEquipment": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "equipment_fractions": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "zonehvac_or_air_terminal_equipment_object_type": {
                                    "type": "string",
                                    "enum": [
                                        "AirLoopHVACReturnAir",
                                        "AirTerminal:DualDuct:ConstantVolume",
                                        "AirTerminal:DualDuct:VAV",
                                        "AirTerminal:DualDuct:VAV:OutdoorAir",
                                        "AirTerminal:SingleDuct:ConstantVolume:CooledBeam",
                                        "AirTerminal:SingleDuct:ConstantVolume:FourPipeInduction",
                                        "AirTerminal:SingleDuct:ConstantVolume:NoReheat",
                                        "AirTerminal:SingleDuct:ConstantVolume:Reheat",
                                        "AirTerminal:SingleDuct:ParallelPIU:Reheat",
                                        "AirTerminal:SingleDuct:SeriesPIU:Reheat",
                                        "AirTerminal:SingleDuct:VAV:HeatAndCool:NoReheat",
                                        "AirTerminal:SingleDuct:VAV:HeatAndCool:Reheat",
                                        "AirTerminal:SingleDuct:VAV:NoReheat",
                                        "AirTerminal:SingleDuct:VAV:Reheat",
                                        "AirTerminal:SingleDuct:VAV:Reheat:VariableSpeedFan",
                                        "Fan:ZoneExhaust",
                                        "WaterHeater:HeatPump",
                                        "ZoneHVAC:Baseboard:Convective:Electric",
                                        "ZoneHVAC:Baseboard:Convective:Water",
                                        "ZoneHVAC:Baseboard:RadiantConvective:Electric",
                                        "ZoneHVAC:Baseboard:RadiantConvective:Steam",
                                        "ZoneHVAC:Baseboard:RadiantConvective:Water",
                                        "ZoneHVAC:Dehumidifier:DX",
                                        "ZoneHVAC:EnergyRecoveryVentilator",
                                        "ZoneHVAC:FourPipeFanCoil",
                                        "ZoneHVAC:HighTemperatureRadiant",
                                        "ZoneHVAC:IdealLoadsAirSystem",
                                        "ZoneHVAC:OutdoorAirUnit",
                                        "ZoneHVAC:PackagedTerminalAirConditioner",
                                        "ZoneHVAC:PackagedTerminalHeatPump",
                                        "ZoneHVAC:RefrigerationChillerSet",
                                        "ZoneHVAC:TerminalUnit:VariableRefrigerantFlow",
                                        "ZoneHVAC:UnitHeater",
                                        "ZoneHVAC:UnitVentilator",
                                        "ZoneHVAC:VentilatedSlab",
                                        "ZoneHVAC:WaterToAirHeatPump",
                                        "ZoneHVAC:WindowAirConditioner"
                                    ]
                                },
                                "zonehvac_or_air_terminal_equipment_object_name": {
                                    "type": "string",
                                    "note": "for object type AirLoopHVACReturnAir, then enter zone return air node name"
                                },
                                "fraction_of_output_or_supply_air_from_hvac_equipment": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 1.0
                                },
                                "fraction_of_input_or_return_air_to_hvac_equipment": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 1.0
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
                "RoomAirNodeHVACEquipment"
            ]
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zonehvac_or_air_terminal_equipment_object_type": {
                    "field_name": "ZoneHVAC or Air Terminal Equipment Object Type",
                    "field_type": "a"
                },
                "zonehvac_or_air_terminal_equipment_object_name": {
                    "field_name": "ZoneHVAC or Air Terminal Equipment Object Name",
                    "field_type": "a"
                },
                "fraction_of_output_or_supply_air_from_hvac_equipment": {
                    "field_name": "Fraction of Output or Supply Air from HVAC Equipment",
                    "field_type": "n"
                },
                "fraction_of_input_or_return_air_to_hvac_equipment": {
                    "field_name": "Fraction of Input or Return Air to HVAC Equipment",
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
                    "zonehvac_or_air_terminal_equipment_object_type",
                    "zonehvac_or_air_terminal_equipment_object_name"
                ]
            },
            "numerics": {
                "fields": [],
                "extensions": [
                    "fraction_of_output_or_supply_air_from_hvac_equipment",
                    "fraction_of_input_or_return_air_to_hvac_equipment"
                ]
            },
            "extensibles": [
                "zonehvac_or_air_terminal_equipment_object_type",
                "zonehvac_or_air_terminal_equipment_object_name",
                "fraction_of_output_or_supply_air_from_hvac_equipment",
                "fraction_of_input_or_return_air_to_hvac_equipment"
            ],
            "extension": "equipment_fractions"
        },
        "type": "object",
        "memo": "define the zone equipment associated with one particular RoomAir:Node",
        "extensible_size": 4.0
    }
}
```
