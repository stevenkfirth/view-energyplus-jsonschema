```
{
    "AirTerminal:SingleDuct:Mixer": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zonehvac_unit_object_type": {
                        "type": "string",
                        "enum": [
                            "AirLoopHVAC:UnitarySystem",
                            "ZoneHVAC:FourPipeFanCoil",
                            "ZoneHVAC:PackagedTerminalAirConditioner",
                            "ZoneHVAC:PackagedTerminalHeatPump",
                            "ZoneHVAC:TerminalUnit:VariableRefrigerantFlow",
                            "ZoneHVAC:UnitVentilator",
                            "ZoneHVAC:WaterToAirHeatPump"
                        ],
                        "note": "The type of ZoneHVAC equipment to which this terminal mixer will be connected."
                    },
                    "zonehvac_unit_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DOAToZonalUnit"
                        ],
                        "note": "The name of ZoneHVAC equipment to which this terminal mixer will be connected."
                    },
                    "mixer_outlet_node_name": {
                        "type": "string",
                        "note": "This is the outlet air node name of the mixer. This will be the inlet air node name of the ZoneHVAC equipment if the connection type in the input field Mixer Connection Type below is InletSide, else this will be an inlet air node name of the conditioned zone if the connection type in the input field Mixer Connection Type below is SupplySide."
                    },
                    "mixer_primary_air_inlet_node_name": {
                        "type": "string",
                        "note": "The primary air (treated outdoor air) inlet node name of the mixer. This will be an outlet air node name of an AirLoopHVAC:ZoneSplitter or AirLoopHVAC:SupplyPlenum providing the connection to the DOA system."
                    },
                    "mixer_secondary_air_inlet_node_name": {
                        "type": "string",
                        "note": "The secondary air (recirculating air) inlet node name of the mixer. This will be the outlet air node name of the ZoneHVAC equipment if the connection type in the input field mixer Connection Type below is SupplySide, or else this will be an exhaust air node name of the conditioned zone if the connection type in the input field Mixer Connection Type below is InletSide."
                    },
                    "mixer_connection_type": {
                        "type": "string",
                        "enum": [
                            "InletSide",
                            "SupplySide"
                        ],
                        "note": "This input field allows user to specify the mixer connection type. Valid choices are InletSide or SupplySide. This is a required input field. If the mixer connection type selected is InletSide, then the mixer is connected on the inlet side of the ZoneHVAC equipment, or else if the mixer connection type selected is SupplySide, then the mixer is connected at the outlet side of the ZoneHVAC equipment."
                    },
                    "design_specification_outdoor_air_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DSOASpaceListNames",
                            "DesignSpecificationOutdoorAirNames"
                        ],
                        "note": "When the name of a DesignSpecification:OutdoorAir object is entered, the terminal unit will adjust flow to meet this outdoor air requirement. If Outdoor Air Flow per Person is non-zero, then the outdoor air requirement will be computed based on the current number of occupants in the zone, as for demand controlled ventilation. If this field is blank, then the terminal unit will be controlled using the DesignSpecification:OutdoorAir objec referenced in the Sizing:Zone object."
                    },
                    "per_person_ventilation_rate_mode": {
                        "type": "string",
                        "enum": [
                            "",
                            "CurrentOccupancy",
                            "DesignOccupancy"
                        ],
                        "default": "CurrentOccupancy",
                        "note": "CurrentOccupancy models demand controlled ventilation using the current number of people DesignOccupancy uses the total Number of People in the zone and is constant"
                    }
                },
                "required": [
                    "zonehvac_unit_object_type",
                    "zonehvac_unit_object_name",
                    "mixer_outlet_node_name",
                    "mixer_primary_air_inlet_node_name",
                    "mixer_secondary_air_inlet_node_name",
                    "mixer_connection_type"
                ]
            }
        },
        "group": "Zone HVAC Air Loop Terminal Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AirTerminalUnitNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zonehvac_unit_object_type": {
                    "field_name": "ZoneHVAC Unit Object Type",
                    "field_type": "a"
                },
                "zonehvac_unit_object_name": {
                    "field_name": "ZoneHVAC Unit Object Name",
                    "field_type": "a"
                },
                "mixer_outlet_node_name": {
                    "field_name": "Mixer Outlet Node Name",
                    "field_type": "a"
                },
                "mixer_primary_air_inlet_node_name": {
                    "field_name": "Mixer Primary Air Inlet Node Name",
                    "field_type": "a"
                },
                "mixer_secondary_air_inlet_node_name": {
                    "field_name": "Mixer Secondary Air Inlet Node Name",
                    "field_type": "a"
                },
                "mixer_connection_type": {
                    "field_name": "Mixer Connection Type",
                    "field_type": "a"
                },
                "design_specification_outdoor_air_object_name": {
                    "field_name": "Design Specification Outdoor Air Object Name",
                    "field_type": "a"
                },
                "per_person_ventilation_rate_mode": {
                    "field_name": "Per Person Ventilation Rate Mode",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zonehvac_unit_object_type",
                "zonehvac_unit_object_name",
                "mixer_outlet_node_name",
                "mixer_primary_air_inlet_node_name",
                "mixer_secondary_air_inlet_node_name",
                "mixer_connection_type",
                "design_specification_outdoor_air_object_name",
                "per_person_ventilation_rate_mode"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zonehvac_unit_object_type",
                    "zonehvac_unit_object_name",
                    "mixer_outlet_node_name",
                    "mixer_primary_air_inlet_node_name",
                    "mixer_secondary_air_inlet_node_name",
                    "mixer_connection_type",
                    "design_specification_outdoor_air_object_name",
                    "per_person_ventilation_rate_mode"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "The mixer air terminal unit provides a means of supplying central system air to the air inlet or outlet side of a zoneHVAC equipment such as a four pipe fan coil unit. Normally the central air would be ventilation air from a dedicated outdoor air system (DOAS)."
    }
}
```
