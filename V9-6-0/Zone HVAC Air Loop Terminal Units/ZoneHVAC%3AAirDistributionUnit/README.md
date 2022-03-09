```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "air_distribution_unit_outlet_node_name": {
                    "type": "string"
                },
                "air_terminal_object_type": {
                    "type": "string",
                    "enum": [
                        "AirTerminal:DualDuct:ConstantVolume",
                        "AirTerminal:DualDuct:VAV",
                        "AirTerminal:DualDuct:VAV:OutdoorAir",
                        "AirTerminal:SingleDuct:ConstantVolume:CooledBeam",
                        "AirTerminal:SingleDuct:ConstantVolume:FourPipeBeam",
                        "AirTerminal:SingleDuct:ConstantVolume:FourPipeInduction",
                        "AirTerminal:SingleDuct:ConstantVolume:NoReheat",
                        "AirTerminal:SingleDuct:ConstantVolume:Reheat",
                        "AirTerminal:SingleDuct:Mixer",
                        "AirTerminal:SingleDuct:ParallelPIU:Reheat",
                        "AirTerminal:SingleDuct:SeriesPIU:Reheat",
                        "AirTerminal:SingleDuct:UserDefined",
                        "AirTerminal:SingleDuct:VAV:HeatAndCool:NoReheat",
                        "AirTerminal:SingleDuct:VAV:HeatAndCool:Reheat",
                        "AirTerminal:SingleDuct:VAV:NoReheat",
                        "AirTerminal:SingleDuct:VAV:Reheat",
                        "AirTerminal:SingleDuct:VAV:Reheat:VariableSpeedFan"
                    ]
                },
                "air_terminal_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "AirTerminalUnitNames"
                    ]
                },
                "nominal_upstream_leakage_fraction": {
                    "type": "number",
                    "note": "fraction at system design Flow; leakage Flow constant, leakage fraction varies with variable system Flow Rate.",
                    "minimum": 0.0,
                    "maximum": 0.3,
                    "default": 0.0
                },
                "constant_downstream_leakage_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 0.3,
                    "default": 0.0
                },
                "design_specification_air_terminal_sizing_object_name": {
                    "type": "string",
                    "note": "This optional field is the name of a DesignSpecification:AirTerminal:Sizing object which specifies sizing adjustments to be made for this terminal unit.",
                    "data_type": "object_list",
                    "object_list": [
                        "DesignSpecificationAirTerminalSizingName"
                    ]
                }
            },
            "required": [
                "air_distribution_unit_outlet_node_name",
                "air_terminal_object_type",
                "air_terminal_name"
            ]
        }
    },
    "group": "Zone HVAC Air Loop Terminal Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ZoneEquipmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "air_distribution_unit_outlet_node_name": {
                "field_name": "Air Distribution Unit Outlet Node Name",
                "field_type": "a"
            },
            "air_terminal_object_type": {
                "field_name": "Air Terminal Object Type",
                "field_type": "a"
            },
            "air_terminal_name": {
                "field_name": "Air Terminal Name",
                "field_type": "a"
            },
            "nominal_upstream_leakage_fraction": {
                "field_name": "Nominal Upstream Leakage Fraction",
                "field_type": "n"
            },
            "constant_downstream_leakage_fraction": {
                "field_name": "Constant Downstream Leakage Fraction",
                "field_type": "n"
            },
            "design_specification_air_terminal_sizing_object_name": {
                "field_name": "Design Specification Air Terminal Sizing Object Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "air_distribution_unit_outlet_node_name",
            "air_terminal_object_type",
            "air_terminal_name",
            "nominal_upstream_leakage_fraction",
            "constant_downstream_leakage_fraction",
            "design_specification_air_terminal_sizing_object_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "air_distribution_unit_outlet_node_name",
                "air_terminal_object_type",
                "air_terminal_name",
                "design_specification_air_terminal_sizing_object_name"
            ]
        },
        "numerics": {
            "fields": [
                "nominal_upstream_leakage_fraction",
                "constant_downstream_leakage_fraction"
            ]
        }
    },
    "type": "object",
    "memo": "Central air system air distribution unit, serves as a wrapper for a specific type of air terminal unit. This object is referenced in a ZoneHVAC:EquipmentList.",
    "min_fields": 4.0
}
```
