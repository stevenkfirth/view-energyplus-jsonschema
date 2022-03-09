```
{
    "WaterHeater:HeatPump:WrappedCondenser": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available. Schedule values of 0 denote the heat pump compressor is off and the parasitic electric energy is also off.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "compressor_setpoint_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Defines the cut-out temperature where the heat pump compressor turns off. The heat pump compressor setpoint temperature should always be greater than the water tank's heater (element or burner) setpoint temperature."
                    },
                    "dead_band_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "exclusiveMinimum": 0.0,
                        "maximum": 20.0,
                        "default": 5.0,
                        "note": "Setpoint temperature minus the dead band temperature difference defines the cut-in temperature where the heat pump compressor turns on. The water tank's heater (element or burner) setpoint temperature should always be less than the heat pump compressor cut-in temperature."
                    },
                    "condenser_bottom_location": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Distance from the bottom of the tank to the bottom of the wrapped condenser."
                    },
                    "condenser_top_location": {
                        "type": "number",
                        "units": "m",
                        "minimum": 0.0,
                        "note": "Distance from the bottom of the tank to the top of the wrapped condenser."
                    },
                    "evaporator_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Actual air flow rate across the heat pump's air coil (evaporator). If autocalculated, the air flow rate is set equal to 5.035E-5 m3/s/W times the rated heating capacity of the heat pump's DX coil.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "inlet_air_configuration": {
                        "type": "string",
                        "enum": [
                            "OutdoorAirOnly",
                            "Schedule",
                            "ZoneAirOnly",
                            "ZoneAndOutdoorAir"
                        ],
                        "note": "Defines the configuration of the airflow path through the air coil and fan section."
                    },
                    "air_inlet_node_name": {
                        "type": "string",
                        "note": "Zone air exhaust node name if Inlet Air Configuration is ZoneAirOnly or ZoneAndOutdoorAir. Simply a unique Node Name if Inlet Air Configuration is Schedule. Otherwise, leave field blank."
                    },
                    "air_outlet_node_name": {
                        "type": "string",
                        "note": "Zone Air Inlet Node Name if Inlet Air Configuration is ZoneAirOnly or ZoneAndOutdoorAir. Simply a unique Node Name if Inlet Air Configuration is Schedule. Otherwise, leave field blank."
                    },
                    "outdoor_air_node_name": {
                        "type": "string",
                        "note": "Outdoor air node name if inlet air configuration is ZoneAndOutdoorAir or OutdoorAirOnly, otherwise leave field blank."
                    },
                    "exhaust_air_node_name": {
                        "type": "string",
                        "note": "Simply a unique Node Name if Inlet Air Configuration is ZoneAndOutdoorAir or OutdoorAirOnly, otherwise leave field blank."
                    },
                    "inlet_air_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Used only if Inlet Air Configuration is Schedule, otherwise leave blank. Schedule values should be degrees C."
                    },
                    "inlet_air_humidity_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Used only if Inlet Air Configuration is Schedule, otherwise leave blank. Schedule values are entered as a fraction (e.g. 0.5 is equal to 50%RH)"
                    },
                    "inlet_air_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "Used only if Inlet Air Configuration is ZoneAirOnly or ZoneAndOutdoorAir. Otherwise, leave field blank."
                    },
                    "tank_object_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "WaterHeater:Stratified"
                        ],
                        "default": "WaterHeater:Stratified",
                        "note": "Specify the type of water heater tank used by this heat pump water heater."
                    },
                    "tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterHeaterStratifiedNames"
                        ],
                        "note": "Needs to match the name used in the corresponding Water Heater object. Must be a WaterHeater:Stratified tank."
                    },
                    "tank_use_side_inlet_node_name": {
                        "type": "string",
                        "note": "Used only when the heat pump water heater is connected to a plant loop, otherwise leave blank. Needs to match the name used in the corresponding Water Heater object when connected to a plant loop."
                    },
                    "tank_use_side_outlet_node_name": {
                        "type": "string",
                        "note": "Used only when the heat pump water heater is connected to a plant loop, otherwise leave blank. Needs to match the name used in the corresponding Water Heater object when connected to a plant loop."
                    },
                    "dx_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Coil:WaterHeating:AirToWaterHeatPump:Wrapped"
                        ],
                        "default": "Coil:WaterHeating:AirToWaterHeatPump:Wrapped",
                        "note": "Specify the type of DX coil used by this heat pump water heater. The only valid choice is Coil:WaterHeating:AirToWaterHeatPump:Wrapped"
                    },
                    "dx_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatPumpWaterHeaterDXCoilsWrapped"
                        ],
                        "note": "Must match the name used in the corresponding Coil:WaterHeating:AirToWaterHeatPump:Wrapped object."
                    },
                    "minimum_inlet_air_temperature_for_compressor_operation": {
                        "type": "number",
                        "units": "C",
                        "default": 10.0,
                        "note": "Heat pump compressor will not operate when the inlet air dry-bulb temperature is below this value."
                    },
                    "maximum_inlet_air_temperature_for_compressor_operation": {
                        "type": "number",
                        "units": "C",
                        "default": 48.88888888889,
                        "minimum": 26.0,
                        "maximum": 94.0,
                        "note": "Heat pump compressor will not operate when the inlet air dry-bulb temperature is above this value."
                    },
                    "compressor_location": {
                        "type": "string",
                        "enum": [
                            "Outdoors",
                            "Schedule",
                            "Zone"
                        ],
                        "note": "If Zone is selected, Inlet Air Configuration must be ZoneAirOnly or ZoneAndOutdoorAir. If Schedule is selected, then you must provide a Compressor Ambient Temperature Schedule Name below."
                    },
                    "compressor_ambient_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Used only if Compressor Location is Schedule, otherwise leave field blank."
                    },
                    "fan_object_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Fan:OnOff",
                            "Fan:SystemModel"
                        ],
                        "default": "Fan:OnOff",
                        "note": "Specify the type of fan used by this heat pump water heater. The only valid choices are Fan:SystemModel or Fan:OnOff."
                    },
                    "fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansOnOff",
                            "FansSystemModel"
                        ],
                        "note": "Needs to match the name used in the corresponding Fan:SystemModel or Fan:OnOff object."
                    },
                    "fan_placement": {
                        "type": "string",
                        "enum": [
                            "",
                            "BlowThrough",
                            "DrawThrough"
                        ],
                        "default": "DrawThrough",
                        "note": "BlowThrough means the fan is located before the air coil (upstream). DrawThrough means the fan is located after the air coil (downstream)."
                    },
                    "on_cycle_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Parasitic electric power consumed when the heat pump compressor operates. Does not contribute to water heating but can impact the zone air heat balance."
                    },
                    "off_cycle_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Parasitic electric power consumed when the heat pump compressor is off. Does not contribute to water heating but can impact the zone air heat balance. Off-cycle parasitic power is 0 when the availability schedule is 0."
                    },
                    "parasitic_heat_rejection_location": {
                        "type": "string",
                        "enum": [
                            "",
                            "Outdoors",
                            "Zone"
                        ],
                        "default": "Outdoors",
                        "note": "This field determines if the parasitic electric load impacts the zone air heat balance. If Zone is selected, Inlet Air Configuration must be ZoneAirOnly or ZoneAndOutdoorAir."
                    },
                    "inlet_air_mixer_node_name": {
                        "type": "string",
                        "note": "Required only if Inlet Air Configuration is ZoneAndOutdoorAir, otherwise leave field blank."
                    },
                    "outlet_air_splitter_node_name": {
                        "type": "string",
                        "note": "Required only if Inlet Air Configuration is ZoneAndOutdoorAir, otherwise leave field blank."
                    },
                    "inlet_air_mixer_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Required only if Inlet Air Configuration is ZoneAndOutdoorAir, otherwise leave field blank. Schedule values define whether the heat pump draws its inlet air from the zone, outdoors or a combination of zone and outdoor air. A schedule value of 0 denotes inlet air is drawn only from the zone. A schedule value of 1 denotes inlet air is drawn only from outdoors. Schedule values between 0 and 1 denote a mixture of zone and outdoor air proportional to the schedule value."
                    },
                    "tank_element_control_logic": {
                        "type": "string",
                        "enum": [
                            "",
                            "MutuallyExclusive",
                            "Simultaneous"
                        ],
                        "default": "Simultaneous",
                        "note": "MutuallyExclusive means that once the tank heating element is active the heat pump is shut down until setpoint is reached. Simultaneous (default) means that both the tank heating element and heat pump are used at the same time recover the tank temperature."
                    },
                    "control_sensor_1_height_in_stratified_tank": {
                        "type": "number",
                        "note": "Used to indicate height of control sensor if Tank Object Type is WaterHeater:Stratified If left blank, it will default to the height of Heater1",
                        "units": "m",
                        "minimum": 0.0
                    },
                    "control_sensor_1_weight": {
                        "type": "number",
                        "note": "Weight to give Control Sensor 1 temperature",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "control_sensor_2_height_in_stratified_tank": {
                        "type": "number",
                        "note": "Used to indicate height of control sensor if Tank Object Type is WaterHeater:Stratified If left blank, it will default to the height of Heater2 The weight of this control sensor will be 1 - (wt. of control sensor 1)",
                        "units": "m",
                        "minimum": 0.0
                    }
                },
                "required": [
                    "compressor_setpoint_temperature_schedule_name",
                    "condenser_top_location",
                    "inlet_air_configuration",
                    "tank_name",
                    "dx_coil_name",
                    "compressor_location",
                    "fan_name"
                ]
            }
        },
        "group": "Water Heaters and Thermal Storage",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validPlantEquipmentTypes"
            ],
            "reference": [
                "ZoneEquipmentNames",
                "validBranchEquipmentNames",
                "validPlantEquipmentNames"
            ],
            "note": "Unique name for this instance of a heat pump water heater."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "compressor_setpoint_temperature_schedule_name": {
                    "field_name": "Compressor Setpoint Temperature Schedule Name",
                    "field_type": "a"
                },
                "dead_band_temperature_difference": {
                    "field_name": "Dead Band Temperature Difference",
                    "field_type": "n"
                },
                "condenser_bottom_location": {
                    "field_name": "Condenser Bottom Location",
                    "field_type": "n"
                },
                "condenser_top_location": {
                    "field_name": "Condenser Top Location",
                    "field_type": "n"
                },
                "evaporator_air_flow_rate": {
                    "field_name": "Evaporator Air Flow Rate",
                    "field_type": "n"
                },
                "inlet_air_configuration": {
                    "field_name": "Inlet Air Configuration",
                    "field_type": "a"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "outdoor_air_node_name": {
                    "field_name": "Outdoor Air Node Name",
                    "field_type": "a"
                },
                "exhaust_air_node_name": {
                    "field_name": "Exhaust Air Node Name",
                    "field_type": "a"
                },
                "inlet_air_temperature_schedule_name": {
                    "field_name": "Inlet Air Temperature Schedule Name",
                    "field_type": "a"
                },
                "inlet_air_humidity_schedule_name": {
                    "field_name": "Inlet Air Humidity Schedule Name",
                    "field_type": "a"
                },
                "inlet_air_zone_name": {
                    "field_name": "Inlet Air Zone Name",
                    "field_type": "a"
                },
                "tank_object_type": {
                    "field_name": "Tank Object Type",
                    "field_type": "a"
                },
                "tank_name": {
                    "field_name": "Tank Name",
                    "field_type": "a"
                },
                "tank_use_side_inlet_node_name": {
                    "field_name": "Tank Use Side Inlet Node Name",
                    "field_type": "a"
                },
                "tank_use_side_outlet_node_name": {
                    "field_name": "Tank Use Side Outlet Node Name",
                    "field_type": "a"
                },
                "dx_coil_object_type": {
                    "field_name": "DX Coil Object Type",
                    "field_type": "a"
                },
                "dx_coil_name": {
                    "field_name": "DX Coil Name",
                    "field_type": "a"
                },
                "minimum_inlet_air_temperature_for_compressor_operation": {
                    "field_name": "Minimum Inlet Air Temperature for Compressor Operation",
                    "field_type": "n"
                },
                "maximum_inlet_air_temperature_for_compressor_operation": {
                    "field_name": "Maximum Inlet Air Temperature for Compressor Operation",
                    "field_type": "n"
                },
                "compressor_location": {
                    "field_name": "Compressor Location",
                    "field_type": "a"
                },
                "compressor_ambient_temperature_schedule_name": {
                    "field_name": "Compressor Ambient Temperature Schedule Name",
                    "field_type": "a"
                },
                "fan_object_type": {
                    "field_name": "Fan Object Type",
                    "field_type": "a"
                },
                "fan_name": {
                    "field_name": "Fan Name",
                    "field_type": "a"
                },
                "fan_placement": {
                    "field_name": "Fan Placement",
                    "field_type": "a"
                },
                "on_cycle_parasitic_electric_load": {
                    "field_name": "On Cycle Parasitic Electric Load",
                    "field_type": "n"
                },
                "off_cycle_parasitic_electric_load": {
                    "field_name": "Off Cycle Parasitic Electric Load",
                    "field_type": "n"
                },
                "parasitic_heat_rejection_location": {
                    "field_name": "Parasitic Heat Rejection Location",
                    "field_type": "a"
                },
                "inlet_air_mixer_node_name": {
                    "field_name": "Inlet Air Mixer Node Name",
                    "field_type": "a"
                },
                "outlet_air_splitter_node_name": {
                    "field_name": "Outlet Air Splitter Node Name",
                    "field_type": "a"
                },
                "inlet_air_mixer_schedule_name": {
                    "field_name": "Inlet Air Mixer Schedule Name",
                    "field_type": "a"
                },
                "tank_element_control_logic": {
                    "field_name": "Tank Element Control Logic",
                    "field_type": "a"
                },
                "control_sensor_1_height_in_stratified_tank": {
                    "field_name": "Control Sensor 1 Height In Stratified Tank",
                    "field_type": "n"
                },
                "control_sensor_1_weight": {
                    "field_name": "Control Sensor 1 Weight",
                    "field_type": "n"
                },
                "control_sensor_2_height_in_stratified_tank": {
                    "field_name": "Control Sensor 2 Height In Stratified Tank",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "compressor_setpoint_temperature_schedule_name",
                "dead_band_temperature_difference",
                "condenser_bottom_location",
                "condenser_top_location",
                "evaporator_air_flow_rate",
                "inlet_air_configuration",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "outdoor_air_node_name",
                "exhaust_air_node_name",
                "inlet_air_temperature_schedule_name",
                "inlet_air_humidity_schedule_name",
                "inlet_air_zone_name",
                "tank_object_type",
                "tank_name",
                "tank_use_side_inlet_node_name",
                "tank_use_side_outlet_node_name",
                "dx_coil_object_type",
                "dx_coil_name",
                "minimum_inlet_air_temperature_for_compressor_operation",
                "maximum_inlet_air_temperature_for_compressor_operation",
                "compressor_location",
                "compressor_ambient_temperature_schedule_name",
                "fan_object_type",
                "fan_name",
                "fan_placement",
                "on_cycle_parasitic_electric_load",
                "off_cycle_parasitic_electric_load",
                "parasitic_heat_rejection_location",
                "inlet_air_mixer_node_name",
                "outlet_air_splitter_node_name",
                "inlet_air_mixer_schedule_name",
                "tank_element_control_logic",
                "control_sensor_1_height_in_stratified_tank",
                "control_sensor_1_weight",
                "control_sensor_2_height_in_stratified_tank"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "compressor_setpoint_temperature_schedule_name",
                    "inlet_air_configuration",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "outdoor_air_node_name",
                    "exhaust_air_node_name",
                    "inlet_air_temperature_schedule_name",
                    "inlet_air_humidity_schedule_name",
                    "inlet_air_zone_name",
                    "tank_object_type",
                    "tank_name",
                    "tank_use_side_inlet_node_name",
                    "tank_use_side_outlet_node_name",
                    "dx_coil_object_type",
                    "dx_coil_name",
                    "compressor_location",
                    "compressor_ambient_temperature_schedule_name",
                    "fan_object_type",
                    "fan_name",
                    "fan_placement",
                    "parasitic_heat_rejection_location",
                    "inlet_air_mixer_node_name",
                    "outlet_air_splitter_node_name",
                    "inlet_air_mixer_schedule_name",
                    "tank_element_control_logic"
                ]
            },
            "numerics": {
                "fields": [
                    "dead_band_temperature_difference",
                    "condenser_bottom_location",
                    "condenser_top_location",
                    "evaporator_air_flow_rate",
                    "minimum_inlet_air_temperature_for_compressor_operation",
                    "maximum_inlet_air_temperature_for_compressor_operation",
                    "on_cycle_parasitic_electric_load",
                    "off_cycle_parasitic_electric_load",
                    "control_sensor_1_height_in_stratified_tank",
                    "control_sensor_1_weight",
                    "control_sensor_2_height_in_stratified_tank"
                ]
            }
        },
        "type": "object",
        "memo": "This object models an air-source heat pump for water heating where the heating coil is wrapped around the tank, which is typical of residential HPWHs. For pumped condenser HPWHs, see WaterHeater:HeatPump:PumpedCondenser. WaterHeater:HeatPump:WrappedCondenser is a compound object that references other component objects - Coil:WaterHeating:AirToWaterHeatPump:Pumped, Fan:OnOff, WaterHeater:Mixed",
        "min_fields": 31.0
    }
}
```
