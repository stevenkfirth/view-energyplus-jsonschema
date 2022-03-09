```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "load_distribution_scheme": {
                    "type": "string",
                    "enum": [
                        "",
                        "SequentialLoad",
                        "SequentialUniformPLR",
                        "UniformLoad",
                        "UniformPLR"
                    ],
                    "default": "SequentialLoad"
                },
                "equipment": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "zone_equipment_object_type": {
                                "type": "string",
                                "enum": [
                                    "AirLoopHVAC:UnitarySystem",
                                    "Fan:ZoneExhaust",
                                    "HeatExchanger:AirToAir:FlatPlate",
                                    "WaterHeater:HeatPump:PumpedCondenser",
                                    "WaterHeater:HeatPump:WrappedCondenser",
                                    "ZoneHVAC:AirDistributionUnit",
                                    "ZoneHVAC:Baseboard:Convective:Electric",
                                    "ZoneHVAC:Baseboard:Convective:Water",
                                    "ZoneHVAC:Baseboard:RadiantConvective:Electric",
                                    "ZoneHVAC:Baseboard:RadiantConvective:Steam",
                                    "ZoneHVAC:Baseboard:RadiantConvective:Water",
                                    "ZoneHVAC:CoolingPanel:RadiantConvective:Water",
                                    "ZoneHVAC:Dehumidifier:DX",
                                    "ZoneHVAC:EnergyRecoveryVentilator",
                                    "ZoneHVAC:EvaporativeCoolerUnit",
                                    "ZoneHVAC:ForcedAir:UserDefined",
                                    "ZoneHVAC:FourPipeFanCoil",
                                    "ZoneHVAC:HighTemperatureRadiant",
                                    "ZoneHVAC:HybridUnitaryHVAC",
                                    "ZoneHVAC:IdealLoadsAirSystem",
                                    "ZoneHVAC:LowTemperatureRadiant:ConstantFlow",
                                    "ZoneHVAC:LowTemperatureRadiant:Electric",
                                    "ZoneHVAC:LowTemperatureRadiant:VariableFlow",
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
                            "zone_equipment_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "ZoneEquipmentNames"
                                ]
                            },
                            "zone_equipment_cooling_sequence": {
                                "type": "number",
                                "minimum": 0.0,
                                "note": "Specifies the zone equipment simulation order when the zone thermostat requests cooling"
                            },
                            "zone_equipment_heating_or_no_load_sequence": {
                                "type": "number",
                                "minimum": 0.0,
                                "note": "Specifies the zone equipment simulation order when the zone thermostat requests heating or no load"
                            },
                            "zone_equipment_sequential_cooling_fraction_schedule_name": {
                                "type": "string",
                                "note": "The fraction of the remaining cooling load this equipment will attempt to serve if the load distribution scheme is SequentialLoad, otherwise ignored.",
                                "data_type": "object_list",
                                "object_list": [
                                    "ScheduleNames"
                                ]
                            },
                            "zone_equipment_sequential_heating_fraction_schedule_name": {
                                "type": "string",
                                "note": "The fraction of the remaining heating load this equipment will attempt to serve if the load distribution scheme is SequentialLoad, otherwise ignored.",
                                "data_type": "object_list",
                                "object_list": [
                                    "ScheduleNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "zone_equipment_cooling_sequence",
                            "zone_equipment_heating_or_no_load_sequence",
                            "zone_equipment_name",
                            "zone_equipment_object_type"
                        ]
                    }
                }
            }
        }
    },
    "group": "Zone HVAC Equipment Connections",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ZoneEquipmentLists"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "load_distribution_scheme": {
                "field_name": "Load Distribution Scheme",
                "field_type": "a"
            },
            "zone_equipment_object_type": {
                "field_name": "Zone Equipment Object Type",
                "field_type": "a"
            },
            "zone_equipment_name": {
                "field_name": "Zone Equipment Name",
                "field_type": "a"
            },
            "zone_equipment_cooling_sequence": {
                "field_name": "Zone Equipment Cooling Sequence",
                "field_type": "n"
            },
            "zone_equipment_heating_or_no_load_sequence": {
                "field_name": "Zone Equipment Heating or No-Load Sequence",
                "field_type": "n"
            },
            "zone_equipment_sequential_cooling_fraction_schedule_name": {
                "field_name": "Zone Equipment Sequential Cooling Fraction Schedule Name",
                "field_type": "a"
            },
            "zone_equipment_sequential_heating_fraction_schedule_name": {
                "field_name": "Zone Equipment Sequential Heating Fraction Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "load_distribution_scheme"
        ],
        "alphas": {
            "fields": [
                "name",
                "load_distribution_scheme"
            ],
            "extensions": [
                "zone_equipment_object_type",
                "zone_equipment_name",
                "zone_equipment_sequential_cooling_fraction_schedule_name",
                "zone_equipment_sequential_heating_fraction_schedule_name"
            ]
        },
        "numerics": {
            "fields": [],
            "extensions": [
                "zone_equipment_cooling_sequence",
                "zone_equipment_heating_or_no_load_sequence"
            ]
        },
        "extensibles": [
            "zone_equipment_object_type",
            "zone_equipment_name",
            "zone_equipment_cooling_sequence",
            "zone_equipment_heating_or_no_load_sequence",
            "zone_equipment_sequential_cooling_fraction_schedule_name",
            "zone_equipment_sequential_heating_fraction_schedule_name"
        ],
        "extension": "equipment"
    },
    "type": "object",
    "memo": "List equipment in simulation order. Note that an ZoneHVAC:AirDistributionUnit object must be listed in this statement if there is a forced air system serving the zone from the air loop. Equipment is simulated in the order specified by Zone Equipment Cooling Sequence and Zone Equipment Heating or No-Load Sequence, depending on the thermostat request. For equipment of similar type, assign sequence 1 to the first system intended to serve that type of load. For situations where one or more equipment types has limited capacity or limited control, order the sequence so that the most controllable piece of equipment runs last. For example, with a dedicated outdoor air system (DOAS), the air terminal for the DOAS should be assigned Heating Sequence = 1 and Cooling Sequence = 1. Any other equipment should be assigned sequence 2 or higher so that it will see the net load after the DOAS air is added to the zone.",
    "min_fields": 8.0,
    "extensible_size": 6.0
}
```
