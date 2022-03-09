```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "control_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "SmartMixing"
                    ],
                    "default": "SmartMixing"
                },
                "cooling_loop_inlet_node_name": {
                    "type": "string"
                },
                "cooling_loop_outlet_node_name": {
                    "type": "string"
                },
                "source_loop_inlet_node_name": {
                    "type": "string"
                },
                "source_loop_outlet_node_name": {
                    "type": "string"
                },
                "heating_loop_inlet_node_name": {
                    "type": "string"
                },
                "heating_loop_outlet_node_name": {
                    "type": "string"
                },
                "ancillary_power": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "Power as demanded from any auxiliary controls"
                },
                "ancillary_operation_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This value from this schedule is multiplied times the Ancillary Power"
                },
                "chiller_heater_modules_performance_component_object_type_1": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_1": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_1": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_1": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_2": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_2": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_2": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_2": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_performance_component_object_type_3": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_performance_component_name_3": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_3": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_3": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_4": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_4": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_4": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_4": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_5": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_models_performance_component_name_5": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_5": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_5": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_6": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_6": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_6": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_6": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_7": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_7": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_7": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_7": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_8": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_8": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_8": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_8": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_9": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_9": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_9": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_9": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_10": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_10": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_10": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_10": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_11": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_11": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_module_control_schedule_name_11": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_11": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_12": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_12": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_12": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_12": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_13": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_13": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_13": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_13": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_14": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_14": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_14": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_14": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_15": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_15": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_15": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_15": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_16": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_16": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_16": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_16": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_17": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_17": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_17": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_17": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_18": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_18": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_control_schedule_name_18": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_18": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_19": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_19": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_19": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_19": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                },
                "chiller_heater_modules_performance_component_object_type_20": {
                    "type": "string",
                    "enum": [
                        "ChillerHeaterPerformance:Electric:EIR"
                    ]
                },
                "chiller_heater_modules_performance_component_name_20": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ChillerHeaterEIRNames"
                    ]
                },
                "chiller_heater_modules_control_schedule_name_20": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "number_of_chiller_heater_modules_20": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0
                }
            },
            "required": [
                "cooling_loop_inlet_node_name",
                "cooling_loop_outlet_node_name",
                "source_loop_inlet_node_name",
                "source_loop_outlet_node_name",
                "heating_loop_inlet_node_name",
                "heating_loop_outlet_node_name",
                "chiller_heater_modules_performance_component_object_type_1",
                "chiller_heater_modules_performance_component_name_1",
                "chiller_heater_modules_control_schedule_name_1"
            ]
        }
    },
    "group": "Plant Heating and Cooling Equipment",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validPlantEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validPlantEquipmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "control_method": {
                "field_name": "Control Method",
                "field_type": "a"
            },
            "cooling_loop_inlet_node_name": {
                "field_name": "Cooling Loop Inlet Node Name",
                "field_type": "a"
            },
            "cooling_loop_outlet_node_name": {
                "field_name": "Cooling Loop Outlet Node Name",
                "field_type": "a"
            },
            "source_loop_inlet_node_name": {
                "field_name": "Source Loop Inlet Node Name",
                "field_type": "a"
            },
            "source_loop_outlet_node_name": {
                "field_name": "Source Loop Outlet Node Name",
                "field_type": "a"
            },
            "heating_loop_inlet_node_name": {
                "field_name": "Heating Loop Inlet Node Name",
                "field_type": "a"
            },
            "heating_loop_outlet_node_name": {
                "field_name": "Heating Loop Outlet Node Name",
                "field_type": "a"
            },
            "ancillary_power": {
                "field_name": "Ancillary Power",
                "field_type": "n"
            },
            "ancillary_operation_schedule_name": {
                "field_name": "Ancillary Operation Schedule Name",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_object_type_1": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 1",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_1": {
                "field_name": "Chiller Heater Modules Performance Component Name 1",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_1": {
                "field_name": "Chiller Heater Modules Control Schedule Name 1",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_1": {
                "field_name": "Number of Chiller Heater Modules 1",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_2": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 2",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_2": {
                "field_name": "Chiller Heater Modules Performance Component Name 2",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_2": {
                "field_name": "Chiller Heater Modules Control Schedule Name 2",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_2": {
                "field_name": "Number of Chiller Heater Modules 2",
                "field_type": "n"
            },
            "chiller_heater_performance_component_object_type_3": {
                "field_name": "Chiller Heater Performance Component Object Type 3",
                "field_type": "a"
            },
            "chiller_heater_performance_component_name_3": {
                "field_name": "Chiller Heater Performance Component Name 3",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_3": {
                "field_name": "Chiller Heater Modules Control Schedule Name 3",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_3": {
                "field_name": "Number of Chiller Heater Modules 3",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_4": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 4",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_4": {
                "field_name": "Chiller Heater Modules Performance Component Name 4",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_4": {
                "field_name": "Chiller Heater Modules Control Schedule Name 4",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_4": {
                "field_name": "Number of Chiller Heater Modules 4",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_5": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 5",
                "field_type": "a"
            },
            "chiller_heater_models_performance_component_name_5": {
                "field_name": "Chiller Heater Models Performance Component Name 5",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_5": {
                "field_name": "Chiller Heater Modules Control Schedule Name 5",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_5": {
                "field_name": "Number of Chiller Heater Modules 5",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_6": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 6",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_6": {
                "field_name": "Chiller Heater Modules Performance Component Name 6",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_6": {
                "field_name": "Chiller Heater Modules Control Schedule Name 6",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_6": {
                "field_name": "Number of Chiller Heater Modules 6",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_7": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 7",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_7": {
                "field_name": "Chiller Heater Modules Performance Component Name 7",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_7": {
                "field_name": "Chiller Heater Modules Control Schedule Name 7",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_7": {
                "field_name": "Number of Chiller Heater Modules 7",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_8": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 8",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_8": {
                "field_name": "Chiller Heater Modules Performance Component Name 8",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_8": {
                "field_name": "Chiller Heater Modules Control Schedule Name 8",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_8": {
                "field_name": "Number of Chiller Heater Modules 8",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_9": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 9",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_9": {
                "field_name": "Chiller Heater Modules Performance Component Name 9",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_9": {
                "field_name": "Chiller Heater Modules Control Schedule Name 9",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_9": {
                "field_name": "Number of Chiller Heater Modules 9",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_10": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 10",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_10": {
                "field_name": "Chiller Heater Modules Performance Component Name 10",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_10": {
                "field_name": "Chiller Heater Modules Control Schedule Name 10",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_10": {
                "field_name": "Number of Chiller Heater Modules 10",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_11": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 11",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_11": {
                "field_name": "Chiller Heater Modules Performance Component Name 11",
                "field_type": "a"
            },
            "chiller_heater_module_control_schedule_name_11": {
                "field_name": "Chiller Heater Module Control Schedule Name 11",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_11": {
                "field_name": "Number of Chiller Heater Modules 11",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_12": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 12",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_12": {
                "field_name": "Chiller Heater Modules Performance Component Name 12",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_12": {
                "field_name": "Chiller Heater Modules Control Schedule Name 12",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_12": {
                "field_name": "Number of Chiller Heater Modules 12",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_13": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 13",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_13": {
                "field_name": "Chiller Heater Modules Performance Component Name 13",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_13": {
                "field_name": "Chiller Heater Modules Control Schedule Name 13",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_13": {
                "field_name": "Number of Chiller Heater Modules 13",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_14": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 14",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_14": {
                "field_name": "Chiller Heater Modules Performance Component Name 14",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_14": {
                "field_name": "Chiller Heater Modules Control Schedule Name 14",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_14": {
                "field_name": "Number of Chiller Heater Modules 14",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_15": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 15",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_15": {
                "field_name": "Chiller Heater Modules Performance Component Name 15",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_15": {
                "field_name": "Chiller Heater Modules Control Schedule Name 15",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_15": {
                "field_name": "Number of Chiller Heater Modules 15",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_16": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 16",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_16": {
                "field_name": "Chiller Heater Modules Performance Component Name 16",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_16": {
                "field_name": "Chiller Heater Modules Control Schedule Name 16",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_16": {
                "field_name": "Number of Chiller Heater Modules 16",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_17": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 17",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_17": {
                "field_name": "Chiller Heater Modules Performance Component Name 17",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_17": {
                "field_name": "Chiller Heater Modules Control Schedule Name 17",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_17": {
                "field_name": "Number of Chiller Heater Modules 17",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_18": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 18",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_18": {
                "field_name": "Chiller Heater Modules Performance Component Name 18",
                "field_type": "a"
            },
            "chiller_heater_modules_control_control_schedule_name_18": {
                "field_name": "Chiller Heater Modules Control Control Schedule Name 18",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_18": {
                "field_name": "Number of Chiller Heater Modules 18",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_19": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 19",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_19": {
                "field_name": "Chiller Heater Modules Performance Component Name 19",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_19": {
                "field_name": "Chiller Heater Modules Control Schedule Name 19",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_19": {
                "field_name": "Number of Chiller Heater Modules 19",
                "field_type": "n"
            },
            "chiller_heater_modules_performance_component_object_type_20": {
                "field_name": "Chiller Heater Modules Performance Component Object Type 20",
                "field_type": "a"
            },
            "chiller_heater_modules_performance_component_name_20": {
                "field_name": "Chiller Heater Modules Performance Component Name 20",
                "field_type": "a"
            },
            "chiller_heater_modules_control_schedule_name_20": {
                "field_name": "Chiller Heater Modules Control Schedule Name 20",
                "field_type": "a"
            },
            "number_of_chiller_heater_modules_20": {
                "field_name": "Number of Chiller Heater Modules 20",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "control_method",
            "cooling_loop_inlet_node_name",
            "cooling_loop_outlet_node_name",
            "source_loop_inlet_node_name",
            "source_loop_outlet_node_name",
            "heating_loop_inlet_node_name",
            "heating_loop_outlet_node_name",
            "ancillary_power",
            "ancillary_operation_schedule_name",
            "chiller_heater_modules_performance_component_object_type_1",
            "chiller_heater_modules_performance_component_name_1",
            "chiller_heater_modules_control_schedule_name_1",
            "number_of_chiller_heater_modules_1",
            "chiller_heater_modules_performance_component_object_type_2",
            "chiller_heater_modules_performance_component_name_2",
            "chiller_heater_modules_control_schedule_name_2",
            "number_of_chiller_heater_modules_2",
            "chiller_heater_performance_component_object_type_3",
            "chiller_heater_performance_component_name_3",
            "chiller_heater_modules_control_schedule_name_3",
            "number_of_chiller_heater_modules_3",
            "chiller_heater_modules_performance_component_object_type_4",
            "chiller_heater_modules_performance_component_name_4",
            "chiller_heater_modules_control_schedule_name_4",
            "number_of_chiller_heater_modules_4",
            "chiller_heater_modules_performance_component_object_type_5",
            "chiller_heater_models_performance_component_name_5",
            "chiller_heater_modules_control_schedule_name_5",
            "number_of_chiller_heater_modules_5",
            "chiller_heater_modules_performance_component_object_type_6",
            "chiller_heater_modules_performance_component_name_6",
            "chiller_heater_modules_control_schedule_name_6",
            "number_of_chiller_heater_modules_6",
            "chiller_heater_modules_performance_component_object_type_7",
            "chiller_heater_modules_performance_component_name_7",
            "chiller_heater_modules_control_schedule_name_7",
            "number_of_chiller_heater_modules_7",
            "chiller_heater_modules_performance_component_object_type_8",
            "chiller_heater_modules_performance_component_name_8",
            "chiller_heater_modules_control_schedule_name_8",
            "number_of_chiller_heater_modules_8",
            "chiller_heater_modules_performance_component_object_type_9",
            "chiller_heater_modules_performance_component_name_9",
            "chiller_heater_modules_control_schedule_name_9",
            "number_of_chiller_heater_modules_9",
            "chiller_heater_modules_performance_component_object_type_10",
            "chiller_heater_modules_performance_component_name_10",
            "chiller_heater_modules_control_schedule_name_10",
            "number_of_chiller_heater_modules_10",
            "chiller_heater_modules_performance_component_object_type_11",
            "chiller_heater_modules_performance_component_name_11",
            "chiller_heater_module_control_schedule_name_11",
            "number_of_chiller_heater_modules_11",
            "chiller_heater_modules_performance_component_object_type_12",
            "chiller_heater_modules_performance_component_name_12",
            "chiller_heater_modules_control_schedule_name_12",
            "number_of_chiller_heater_modules_12",
            "chiller_heater_modules_performance_component_object_type_13",
            "chiller_heater_modules_performance_component_name_13",
            "chiller_heater_modules_control_schedule_name_13",
            "number_of_chiller_heater_modules_13",
            "chiller_heater_modules_performance_component_object_type_14",
            "chiller_heater_modules_performance_component_name_14",
            "chiller_heater_modules_control_schedule_name_14",
            "number_of_chiller_heater_modules_14",
            "chiller_heater_modules_performance_component_object_type_15",
            "chiller_heater_modules_performance_component_name_15",
            "chiller_heater_modules_control_schedule_name_15",
            "number_of_chiller_heater_modules_15",
            "chiller_heater_modules_performance_component_object_type_16",
            "chiller_heater_modules_performance_component_name_16",
            "chiller_heater_modules_control_schedule_name_16",
            "number_of_chiller_heater_modules_16",
            "chiller_heater_modules_performance_component_object_type_17",
            "chiller_heater_modules_performance_component_name_17",
            "chiller_heater_modules_control_schedule_name_17",
            "number_of_chiller_heater_modules_17",
            "chiller_heater_modules_performance_component_object_type_18",
            "chiller_heater_modules_performance_component_name_18",
            "chiller_heater_modules_control_control_schedule_name_18",
            "number_of_chiller_heater_modules_18",
            "chiller_heater_modules_performance_component_object_type_19",
            "chiller_heater_modules_performance_component_name_19",
            "chiller_heater_modules_control_schedule_name_19",
            "number_of_chiller_heater_modules_19",
            "chiller_heater_modules_performance_component_object_type_20",
            "chiller_heater_modules_performance_component_name_20",
            "chiller_heater_modules_control_schedule_name_20",
            "number_of_chiller_heater_modules_20"
        ],
        "alphas": {
            "fields": [
                "name",
                "control_method",
                "cooling_loop_inlet_node_name",
                "cooling_loop_outlet_node_name",
                "source_loop_inlet_node_name",
                "source_loop_outlet_node_name",
                "heating_loop_inlet_node_name",
                "heating_loop_outlet_node_name",
                "ancillary_operation_schedule_name",
                "chiller_heater_modules_performance_component_object_type_1",
                "chiller_heater_modules_performance_component_name_1",
                "chiller_heater_modules_control_schedule_name_1",
                "chiller_heater_modules_performance_component_object_type_2",
                "chiller_heater_modules_performance_component_name_2",
                "chiller_heater_modules_control_schedule_name_2",
                "chiller_heater_performance_component_object_type_3",
                "chiller_heater_performance_component_name_3",
                "chiller_heater_modules_control_schedule_name_3",
                "chiller_heater_modules_performance_component_object_type_4",
                "chiller_heater_modules_performance_component_name_4",
                "chiller_heater_modules_control_schedule_name_4",
                "chiller_heater_modules_performance_component_object_type_5",
                "chiller_heater_models_performance_component_name_5",
                "chiller_heater_modules_control_schedule_name_5",
                "chiller_heater_modules_performance_component_object_type_6",
                "chiller_heater_modules_performance_component_name_6",
                "chiller_heater_modules_control_schedule_name_6",
                "chiller_heater_modules_performance_component_object_type_7",
                "chiller_heater_modules_performance_component_name_7",
                "chiller_heater_modules_control_schedule_name_7",
                "chiller_heater_modules_performance_component_object_type_8",
                "chiller_heater_modules_performance_component_name_8",
                "chiller_heater_modules_control_schedule_name_8",
                "chiller_heater_modules_performance_component_object_type_9",
                "chiller_heater_modules_performance_component_name_9",
                "chiller_heater_modules_control_schedule_name_9",
                "chiller_heater_modules_performance_component_object_type_10",
                "chiller_heater_modules_performance_component_name_10",
                "chiller_heater_modules_control_schedule_name_10",
                "chiller_heater_modules_performance_component_object_type_11",
                "chiller_heater_modules_performance_component_name_11",
                "chiller_heater_module_control_schedule_name_11",
                "chiller_heater_modules_performance_component_object_type_12",
                "chiller_heater_modules_performance_component_name_12",
                "chiller_heater_modules_control_schedule_name_12",
                "chiller_heater_modules_performance_component_object_type_13",
                "chiller_heater_modules_performance_component_name_13",
                "chiller_heater_modules_control_schedule_name_13",
                "chiller_heater_modules_performance_component_object_type_14",
                "chiller_heater_modules_performance_component_name_14",
                "chiller_heater_modules_control_schedule_name_14",
                "chiller_heater_modules_performance_component_object_type_15",
                "chiller_heater_modules_performance_component_name_15",
                "chiller_heater_modules_control_schedule_name_15",
                "chiller_heater_modules_performance_component_object_type_16",
                "chiller_heater_modules_performance_component_name_16",
                "chiller_heater_modules_control_schedule_name_16",
                "chiller_heater_modules_performance_component_object_type_17",
                "chiller_heater_modules_performance_component_name_17",
                "chiller_heater_modules_control_schedule_name_17",
                "chiller_heater_modules_performance_component_object_type_18",
                "chiller_heater_modules_performance_component_name_18",
                "chiller_heater_modules_control_control_schedule_name_18",
                "chiller_heater_modules_performance_component_object_type_19",
                "chiller_heater_modules_performance_component_name_19",
                "chiller_heater_modules_control_schedule_name_19",
                "chiller_heater_modules_performance_component_object_type_20",
                "chiller_heater_modules_performance_component_name_20",
                "chiller_heater_modules_control_schedule_name_20"
            ]
        },
        "numerics": {
            "fields": [
                "ancillary_power",
                "number_of_chiller_heater_modules_1",
                "number_of_chiller_heater_modules_2",
                "number_of_chiller_heater_modules_3",
                "number_of_chiller_heater_modules_4",
                "number_of_chiller_heater_modules_5",
                "number_of_chiller_heater_modules_6",
                "number_of_chiller_heater_modules_7",
                "number_of_chiller_heater_modules_8",
                "number_of_chiller_heater_modules_9",
                "number_of_chiller_heater_modules_10",
                "number_of_chiller_heater_modules_11",
                "number_of_chiller_heater_modules_12",
                "number_of_chiller_heater_modules_13",
                "number_of_chiller_heater_modules_14",
                "number_of_chiller_heater_modules_15",
                "number_of_chiller_heater_modules_16",
                "number_of_chiller_heater_modules_17",
                "number_of_chiller_heater_modules_18",
                "number_of_chiller_heater_modules_19",
                "number_of_chiller_heater_modules_20"
            ]
        }
    },
    "type": "object",
    "memo": "This chiller bank can contain multiple chiller heaters and heat pump performance objects. Its function is to encapsulate the extra controls needed to turn individual modules on/off and whether they are to operate in cooling-only, heating-only or simultaneous cooling/heating mode and whether to connect the source water to the evaporator or condenser side.",
    "min_fields": 14.0
}
```
