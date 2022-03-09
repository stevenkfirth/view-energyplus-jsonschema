```
{
    "AirConditioner:VariableRefrigerantFlow": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available. Enter the name of a schedule that defines the availability of the unit. Schedule values of 0 denote the unit is off. All other values denote the unit is available. If this field is left blank, the unit is available the entire simulation.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "gross_rated_total_cooling_capacity": {
                        "units": "W",
                        "note": "Enter the total cooling capacity in watts at rated conditions or set to autosize. Total cooling capacity not accounting for the effect of supply air fan heat",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.3,
                        "note": "Enter the coefficient of performance at rated conditions or leave blank to use default. COP includes compressor and condenser fan electrical energy input COP does not include supply fan heat or supply fan electric power input"
                    },
                    "minimum_condenser_inlet_node_temperature_in_cooling_mode": {
                        "type": "number",
                        "units": "C",
                        "default": -6.0,
                        "note": "For cooling mode operation, enter the minimum inlet outdoor air dry-bulb temperature for air-cooled units or minimum inlet water temperature for water-cooled units. Cooling is disabled below this temperature."
                    },
                    "maximum_condenser_inlet_node_temperature_in_cooling_mode": {
                        "type": "number",
                        "units": "C",
                        "default": 43.0,
                        "note": "For cooling mode operation, enter the maximum inlet outdoor air dry-bulb temperature for air-cooled units or maximum inlet water temperature for water-cooled units. Cooling is disabled above this temperature."
                    },
                    "cooling_capacity_ratio_modifier_function_of_low_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Enter a curve name that represents full load cooling capacity ratio as a function of outdoor dry-bulb temperature and indoor wet-bulb temperature. Up to two curves are allowed if the performance cannot be represented by a single curve. The following two fields are used if two curves are required."
                    },
                    "cooling_capacity_ratio_boundary_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve object is used to allow separate low and high cooling capacity ratio performance curves. This curve represents a line passing through the points where performance changes. The curve calculates outdoor dry-bulb temperature given weighted average indoor wet-bulb temperature. If a single performance curve is used, leave this field blank."
                    },
                    "cooling_capacity_ratio_modifier_function_of_high_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "This curve object is used to describe the high outdoor temperature performance curve used to describe cooling capacity ratio. This curve is used when a single performance curve does not accurately describe cooling capacity ratio as a function of temperature. If a single performance curve is used, leave this field blank."
                    },
                    "cooling_energy_input_ratio_modifier_function_of_low_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Enter a curve name that represents cooling energy ratio as a function of outdoor dry-bulb temperature and indoor wet-bulb temperature"
                    },
                    "cooling_energy_input_ratio_boundary_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve object is used to allow separate low and high cooling energy input ratio performance curves. This curve represents a line passing through the points where performance changes. The curve calculates outdoor dry-bulb temperature given weighted average indoor wet-bulb temperature. If a single performance curve is used, leave this field blank."
                    },
                    "cooling_energy_input_ratio_modifier_function_of_high_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "This curve object is used to describe the high outdoor temperature performance curve used to describe cooling energy ratio. This curve is used when a single performance curve does not accurately describe cooling energy ratio as a function of temperature"
                    },
                    "cooling_energy_input_ratio_modifier_function_of_low_part_load_ratio_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Enter a curve name that represents cooling energy ratio as a function of part-load ratio for part-load ratios less than or equal to 1. If this field is left blank, the model assumes energy is proportional to part-load ratio."
                    },
                    "cooling_energy_input_ratio_modifier_function_of_high_part_load_ratio_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Enter a curve name that represents cooling energy ratio as a function of part-load ratio for part-load ratios greater than 1. Part-load ratios can exceed 1 in variable speed compression systems. If this field is left blank, the model assumes energy is proportional to part-load ratio."
                    },
                    "cooling_combination_ratio_correction_factor_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve defines how rated capacity changes when the total indoor terminal unit cooling capacity is greater than the Gross Rated Total Cooling Capacity defined in this object. If this field is left blank, the model assumes total indoor terminal unit cooling capacity is equal to the Gross Rated Total Cooling Capacity defined above."
                    },
                    "cooling_part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve defines the cycling losses when the heat pump compressor cycles on and off below the Minimum Heat Pump Part-Load Ratio specified in the field below."
                    },
                    "gross_rated_heating_capacity": {
                        "units": "W",
                        "note": "Enter the heating capacity in watts at rated conditions or set to autosize. Heating capacity not accounting for the effect of supply air fan heat",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "rated_heating_capacity_sizing_ratio": {
                        "type": "number",
                        "units": "W/W",
                        "minimum": 1.0,
                        "default": 1.0,
                        "note": "If the Gross Rated Heating Capacity is autosized, the heating capacity is sized to be equal to the cooling capacity multiplied by this sizing ratio. The zone terminal unit heating coils are also sized using this ratio unless the sizing ratio input in the ZoneHVAC:TerminalUnit:VariableRefrigerantFlow object is entered."
                    },
                    "gross_rated_heating_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "note": "COP includes compressor and condenser fan electrical energy input COP does not include supply fan heat or supply fan electrical energy input",
                        "default": 3.4
                    },
                    "minimum_condenser_inlet_node_temperature_in_heating_mode": {
                        "type": "number",
                        "units": "C",
                        "default": -20.0,
                        "note": "For heating mode operation, enter the minimum inlet outdoor air dry-bulb temperature for air-cooled units or minimum inlet water temperature for water-cooled units. Heating is disabled below this temperature."
                    },
                    "maximum_condenser_inlet_node_temperature_in_heating_mode": {
                        "type": "number",
                        "units": "C",
                        "default": 16.0,
                        "note": "For heating mode operation, enter the maximum inlet outdoor air dry-bulb temperature for air-cooled units or maximum inlet water temperature for water-cooled units. Heating is disabled below this temperature."
                    },
                    "heating_capacity_ratio_modifier_function_of_low_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Enter a curve name that represents full load heating capacity ratio as a function of outdoor wet-bulb temperature and indoor dry-bulb temperature. Outdoor dry-bulb temperature may be used if wet-bulb temperature data is unavailable. See Heating Performance Curve Outdoor Temperature Type input below to determine which outdoor temperature type to use. Up to two curves are allowed if the performance cannot be represented by a single curve. The following two fields are used if two curves are required."
                    },
                    "heating_capacity_ratio_boundary_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve object is used to allow separate low and high heating capacity ratio performance curves. This curve represents a line passing through the points where performance changes. The curve calculates outdoor dry-bulb or wet-bulb temperature given weighted average indoor dry-bulb temperature. See Heating Performance Curve Outdoor Temperature Type input below to determine which outdoor temperature type to use. If a single performance curve is used, leave this field blank."
                    },
                    "heating_capacity_ratio_modifier_function_of_high_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "This curve object is used to describe the high outdoor temperature performance curve used to describe heating capacity ratio. This curve is used when a single performance curve does not accurately describe heating capacity ratio as a function of temperature. If a single performance curve is used, leave this field blank."
                    },
                    "heating_energy_input_ratio_modifier_function_of_low_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Enter a curve name that represents heating energy ratio as a function of outdoor wet-bulb temperature and indoor dry-bulb temperature Outdoor dry-bulb temperature may be used if wet-bulb temperature data is unavailable. See Heating Performance Curve Outdoor Temperature Type input below to determine which outdoor temperature type to use."
                    },
                    "heating_energy_input_ratio_boundary_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve object is used to allow separate low and high heating energy input ratio performance curves. This curve represents a line passing through the points where performance changes. The curve calculates outdoor dry-bulb or wet-bulb temperature given weighted average indoor dry-bulb temperature. See Heating Performance Curve Outdoor Temperature Type input below to determine which outdoor temperature type to use. If a single performance curve is used, leave this field blank."
                    },
                    "heating_energy_input_ratio_modifier_function_of_high_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "This curve object is used to allow separate performance curves for heating energy. If a single performance curve is used, leave this field blank."
                    },
                    "heating_performance_curve_outdoor_temperature_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "DryBulbTemperature",
                            "WetBulbTemperature"
                        ],
                        "default": "WetBulbTemperature",
                        "note": "Determines temperature type for heating capacity curves and heating energy curves. This input determines whether the outdoor air dry-bulb or wet-bulb temperature is used to evaluate these curves."
                    },
                    "heating_energy_input_ratio_modifier_function_of_low_part_load_ratio_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve represents the heating energy input ratio for part-load ratios less than 1."
                    },
                    "heating_energy_input_ratio_modifier_function_of_high_part_load_ratio_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve represents the heating energy input ratio for part-load ratios greater than 1."
                    },
                    "heating_combination_ratio_correction_factor_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve defines how rated capacity changes when the total indoor terminal unit heating capacity is greater than the Gross Rated Heating Capacity defined in this object. If this field is left blank, the model assumes total indoor terminal unit heating capacity is equal to the Gross Rated Heating Capacity defined above."
                    },
                    "heating_part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "This curve defines the cycling losses when the heat pump compressor cycles on and off below the Minimum Heat Pump Part-Load Ratio specified in the following field."
                    },
                    "minimum_heat_pump_part_load_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "note": "Enter the minimum heat pump part-load ratio (PLR). When the cooling or heating PLR is below this value, the heat pump compressor will cycle to meet the cooling or heating demand.",
                        "default": 0.15
                    },
                    "zone_name_for_master_thermostat_location": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "Enter the name of the zone where the master thermostat is located."
                    },
                    "master_thermostat_priority_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "LoadPriority",
                            "MasterThermostatPriority",
                            "Scheduled",
                            "ThermostatOffsetPriority",
                            "ZonePriority"
                        ],
                        "default": "MasterThermostatPriority",
                        "note": "Choose a thermostat control logic scheme. If these control types fail to control zone temperature within a reasonable limit, consider using multiple VRF systems. This field is not used when all terminal units are set point controlled."
                    },
                    "thermostat_priority_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "this field is required if Master Thermostat Priority Control Type is Scheduled. Schedule values of 0 denote cooling, 1 for heating, and all other values disable the system."
                    },
                    "zone_terminal_unit_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneTerminalUnitListNames"
                        ],
                        "note": "Enter the name of a ZoneTerminalUnitList. This list connects zone terminal units to this heat pump."
                    },
                    "heat_pump_waste_heat_recovery": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "This field enables heat recovery operation within this VRF outdoor unit."
                    },
                    "equivalent_piping_length_used_for_piping_correction_factor_in_cooling_mode": {
                        "type": "number",
                        "units": "m",
                        "note": "Enter the equivalent length of the farthest terminal unit from the condenser"
                    },
                    "vertical_height_used_for_piping_correction_factor": {
                        "type": "number",
                        "units": "m",
                        "note": "Enter the height difference between the highest and lowest terminal unit"
                    },
                    "piping_correction_factor_for_length_in_cooling_mode_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions",
                            "UnivariateFunctions"
                        ],
                        "note": "PCF = a0 + a1*L + a2*L^2 + a3*L^3 + a4*H PCF = a0 + a1*L + a2*L^2 + a3*CR + a4*CR^2 + a5*(L)(CR) where L = length and CR = combination ratio specifies coefficients for a0, a1, a2, and a3 in the PCF equation"
                    },
                    "piping_correction_factor_for_height_in_cooling_mode_coefficient": {
                        "type": "number",
                        "units": "1/m",
                        "default": 0.0,
                        "note": "PCF = a0 + a1*L + a2*L^2 + a3*L^3 + a4*H PCF = a0 + a1*L + a2*L^2 + a3*CR + a4*CR^2 + a5*(L)(CR) + a6*H where L = length, H = height, and CR = combination ratio specifies coefficient a4 (or a6 for biquadratic) in the PCF equation"
                    },
                    "equivalent_piping_length_used_for_piping_correction_factor_in_heating_mode": {
                        "type": "number",
                        "units": "m",
                        "note": "Enter the equivalent length of the farthest terminal unit from the condenser"
                    },
                    "piping_correction_factor_for_length_in_heating_mode_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions",
                            "UnivariateFunctions"
                        ],
                        "note": "PCF = a0 + a1*L + a2*L^2 + a3*L^3 + a4*H PCF = a0 + a1*L + a2*L^2 + a3*CR + a4*CR^2 + a5*(L)(CR) + a6*H where L = length and CR = combination ratio specifies coefficients for a0, a1, a2, and a3 (or a0-a5 for biquadratic) in the PCF equation"
                    },
                    "piping_correction_factor_for_height_in_heating_mode_coefficient": {
                        "type": "number",
                        "units": "1/m",
                        "default": 0.0,
                        "note": "PCF = a0 + a1*L + a2*L^2 + a3*L^3 + a4*H PCF = a0 + a1*L + a2*L^2 + a3*CR + a4*CR^2 + a5*(L)(CR) + a6*H where L = length, H = height, and CR = combination ratio specifies coefficient a4 (or a6 for biquadratic) in the PCF equation"
                    },
                    "crankcase_heater_power_per_compressor": {
                        "type": "number",
                        "units": "W",
                        "default": 33.0,
                        "note": "Enter the value of the resistive heater located in the compressor(s). This heater is used to warm the refrigerant and oil when the compressor is off."
                    },
                    "number_of_compressors": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 2.0,
                        "note": "Enter the total number of compressor. This input is used only for crankcase heater calculations."
                    },
                    "ratio_of_compressor_size_to_total_compressor_capacity": {
                        "type": "number",
                        "units": "W/W",
                        "default": 0.5,
                        "note": "Enter the ratio of the first stage compressor to total compressor capacity. All other compressors are assumed to be equally sized. This inputs is used only for crankcase heater calculations."
                    },
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater": {
                        "type": "number",
                        "units": "C",
                        "default": 5.0,
                        "note": "Enter the maximum outdoor temperature above which the crankcase heaters are disabled."
                    },
                    "defrost_strategy": {
                        "type": "string",
                        "enum": [
                            "",
                            "Resistive",
                            "ReverseCycle"
                        ],
                        "default": "Resistive",
                        "note": "Select a defrost strategy. Reverse cycle reverses the operating mode from heating to cooling to melt frost formation on the condenser coil. The resistive strategy uses a resistive heater to melt the frost."
                    },
                    "defrost_control": {
                        "type": "string",
                        "enum": [
                            "",
                            "OnDemand",
                            "Timed"
                        ],
                        "default": "Timed",
                        "note": "Choose a defrost control type. Either use a fixed Timed defrost period or select OnDemand to defrost only when necessary."
                    },
                    "defrost_energy_input_ratio_modifier_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "A valid performance curve must be used if reversecycle defrost strategy is selected."
                    },
                    "defrost_time_period_fraction": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "default": 0.058333,
                        "note": "Fraction of time in defrost mode. Only applicable if timed defrost control is specified."
                    },
                    "resistive_defrost_heater_capacity": {
                        "units": "W",
                        "default": 0.0,
                        "note": "Enter the size of the resistive defrost heating element. Only applicable if resistive defrost strategy is specified",
                        "ip-units": "W",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "maximum_outdoor_dry_bulb_temperature_for_defrost_operation": {
                        "type": "number",
                        "units": "C",
                        "default": 5.0,
                        "note": "Enter the maximum outdoor temperature above which defrost operation is disabled."
                    },
                    "condenser_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "AirCooled",
                            "EvaporativelyCooled",
                            "WaterCooled"
                        ],
                        "default": "AirCooled",
                        "note": "Select either an air-cooled, evaporatively-cooled or water-cooled condenser."
                    },
                    "condenser_inlet_node_name": {
                        "type": "string",
                        "note": "Choose an outside air node name or leave this field blank to use weather data. If this field is blank, the Condenser Type is assumed to be AirCooled. This input must be specified if Condenser Type = WaterCooled."
                    },
                    "condenser_outlet_node_name": {
                        "type": "string",
                        "note": "Enter a water outlet node name if Condenser Type = WaterCooled. Leave this field blank if Condenser Type = Air or EvaporativelyCooled."
                    },
                    "water_condenser_volume_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "note": "Only used when Condenser Type = WaterCooled.",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "evaporative_condenser_effectiveness": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9,
                        "note": "Enter the effectiveness of the evaporatively cooled condenser. This field is only used when the Condenser Type = EvaporativelyCooled."
                    },
                    "evaporative_condenser_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Used to calculate evaporative condenser water use. This field is only used when the Condenser Type = EvaporativelyCooled.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "evaporative_condenser_pump_rated_power_consumption": {
                        "units": "W",
                        "default": 0.0,
                        "note": "Rated power consumed by the evaporative condenser's water pump. This field is only used when the Condenser Type = EvaporativelyCooled.",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "supply_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ],
                        "note": "A separate storage tank may be used to supply an evaporatively cooled condenser."
                    },
                    "basin_heater_capacity": {
                        "type": "number",
                        "units": "W/K",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled and for periods when the basin heater is available (field Basin Heater Operating Schedule Name). For this situation, the heater maintains the basin water temperature at the basin heater setpoint temperature when the outdoor air temperature falls below the setpoint temperature. The basin heater only operates when the DX coil is off."
                    },
                    "basin_heater_setpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "minimum": 2.0,
                        "default": 2.0,
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled. Enter the outdoor dry-bulb temperature when the basin heater turns on."
                    },
                    "basin_heater_operating_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled. Schedule values greater than 0 allow the basin heater to operate whenever the outdoor air dry-bulb temperature is below the basin heater setpoint temperature. If a schedule name is not entered, the basin heater is allowed to operate throughout the entire simulation."
                    },
                    "fuel_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Diesel",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane"
                        ],
                        "default": "Electricity"
                    },
                    "minimum_condenser_inlet_node_temperature_in_heat_recovery_mode": {
                        "type": "number",
                        "units": "C",
                        "note": "For heat recovery mode operation, enter the minimum inlet outdoor air dry-bulb temperature for air-cooled units or minimum inlet water temperature for water-cooled units. Heat recovery is disabled below this temperature."
                    },
                    "maximum_condenser_inlet_node_temperature_in_heat_recovery_mode": {
                        "type": "number",
                        "units": "C",
                        "note": "For heat recovery mode operation, enter the maximum inlet outdoor air dry-bulb temperature for air-cooled units or maximum inlet water temperature for water-cooled units. Heat recovery is disabled above this temperature."
                    },
                    "heat_recovery_cooling_capacity_modifier_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Enter the name of a performance curve which represents the change in cooling capacity when heat recovery is active A default constant of 0.9 is used if this input is blank"
                    },
                    "initial_heat_recovery_cooling_capacity_fraction": {
                        "type": "number",
                        "units": "W/W",
                        "default": 0.5,
                        "note": "Enter the fractional capacity available at the start of heat recovery mode. The capacity exponentially approaches the steady-state value according to the inputs for Heat Recovery Cooling Capacity Modifier and Heat Recovery Cooling Capacity Time Constant"
                    },
                    "heat_recovery_cooling_capacity_time_constant": {
                        "type": "number",
                        "units": "hr",
                        "default": 0.15,
                        "note": "Enter the time constant used to model the transition from cooling only mode to heat recovery mode"
                    },
                    "heat_recovery_cooling_energy_modifier_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Enter the name of a performance curve which represents the change in cooling energy when heat recovery is active A default constant of 1.1 is used if this input is blank"
                    },
                    "initial_heat_recovery_cooling_energy_fraction": {
                        "type": "number",
                        "units": "W/W",
                        "default": 1.0,
                        "note": "Enter the fractional electric consumption rate at the start of heat recovery mode. The electric consumption rate exponentially approaches the steady-state value according to the inputs for Heat Recovery Cooling Energy Modifier and Heat Recovery Cooling Energy Time Constant"
                    },
                    "heat_recovery_cooling_energy_time_constant": {
                        "type": "number",
                        "units": "hr",
                        "default": 0.0,
                        "note": "Enter the time constant used to model the transition from cooling only mode to heat recovery mode"
                    },
                    "heat_recovery_heating_capacity_modifier_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Enter the name of a performance curve which represents the change in heating capacity when heat recovery is active A default constant of 1.1 is used if this input is blank"
                    },
                    "initial_heat_recovery_heating_capacity_fraction": {
                        "type": "number",
                        "units": "W/W",
                        "default": 1.0,
                        "note": "Enter the fractional capacity available at the start of heat recovery mode. The capacity exponentially approaches the steady-state value according to the inputs for Heat Recovery Heating Capacity Modifier and Heat Recovery Heating Capacity Time Constant"
                    },
                    "heat_recovery_heating_capacity_time_constant": {
                        "type": "number",
                        "units": "hr",
                        "default": 0.15,
                        "note": "Enter the time constant used to model the transition from cooling only mode to heat recovery mode"
                    },
                    "heat_recovery_heating_energy_modifier_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Enter the name of a performance curve which represents the change in heating electric consumption rate when heat recovery is active A default constant of 1.1 is used if this input is blank"
                    },
                    "initial_heat_recovery_heating_energy_fraction": {
                        "type": "number",
                        "units": "W/W",
                        "default": 1.0,
                        "note": "Enter the fractional electric consumption rate at the start of heat recovery mode. The electric consumption rate exponentially approaches the steady-state value according to the inputs for Heat Recovery Cooling Energy Modifier and Heat Recovery Cooling Energy Time Constant"
                    },
                    "heat_recovery_heating_energy_time_constant": {
                        "type": "number",
                        "units": "hr",
                        "default": 0.0,
                        "note": "Enter the time constant used to model the transition from cooling only mode to heat recovery mode"
                    }
                },
                "required": [
                    "zone_terminal_unit_list_name"
                ]
            }
        },
        "group": "Variable Refrigerant Flow Equipment",
        "legacy_idd": {
            "field_info": {
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "gross_rated_total_cooling_capacity": {
                    "field_name": "Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "gross_rated_cooling_cop": {
                    "field_name": "Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "minimum_condenser_inlet_node_temperature_in_cooling_mode": {
                    "field_name": "Minimum Condenser Inlet Node Temperature in Cooling Mode",
                    "field_type": "n"
                },
                "maximum_condenser_inlet_node_temperature_in_cooling_mode": {
                    "field_name": "Maximum Condenser Inlet Node Temperature in Cooling Mode",
                    "field_type": "n"
                },
                "cooling_capacity_ratio_modifier_function_of_low_temperature_curve_name": {
                    "field_name": "Cooling Capacity Ratio Modifier Function of Low Temperature Curve Name",
                    "field_type": "a"
                },
                "cooling_capacity_ratio_boundary_curve_name": {
                    "field_name": "Cooling Capacity Ratio Boundary Curve Name",
                    "field_type": "a"
                },
                "cooling_capacity_ratio_modifier_function_of_high_temperature_curve_name": {
                    "field_name": "Cooling Capacity Ratio Modifier Function of High Temperature Curve Name",
                    "field_type": "a"
                },
                "cooling_energy_input_ratio_modifier_function_of_low_temperature_curve_name": {
                    "field_name": "Cooling Energy Input Ratio Modifier Function of Low Temperature Curve Name",
                    "field_type": "a"
                },
                "cooling_energy_input_ratio_boundary_curve_name": {
                    "field_name": "Cooling Energy Input Ratio Boundary Curve Name",
                    "field_type": "a"
                },
                "cooling_energy_input_ratio_modifier_function_of_high_temperature_curve_name": {
                    "field_name": "Cooling Energy Input Ratio Modifier Function of High Temperature Curve Name",
                    "field_type": "a"
                },
                "cooling_energy_input_ratio_modifier_function_of_low_part_load_ratio_curve_name": {
                    "field_name": "Cooling Energy Input Ratio Modifier Function of Low Part-Load Ratio Curve Name",
                    "field_type": "a"
                },
                "cooling_energy_input_ratio_modifier_function_of_high_part_load_ratio_curve_name": {
                    "field_name": "Cooling Energy Input Ratio Modifier Function of High Part-Load Ratio Curve Name",
                    "field_type": "a"
                },
                "cooling_combination_ratio_correction_factor_curve_name": {
                    "field_name": "Cooling Combination Ratio Correction Factor Curve Name",
                    "field_type": "a"
                },
                "cooling_part_load_fraction_correlation_curve_name": {
                    "field_name": "Cooling Part-Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "gross_rated_heating_capacity": {
                    "field_name": "Gross Rated Heating Capacity",
                    "field_type": "n"
                },
                "rated_heating_capacity_sizing_ratio": {
                    "field_name": "Rated Heating Capacity Sizing Ratio",
                    "field_type": "n"
                },
                "gross_rated_heating_cop": {
                    "field_name": "Gross Rated Heating COP",
                    "field_type": "n"
                },
                "minimum_condenser_inlet_node_temperature_in_heating_mode": {
                    "field_name": "Minimum Condenser Inlet Node Temperature in Heating Mode",
                    "field_type": "n"
                },
                "maximum_condenser_inlet_node_temperature_in_heating_mode": {
                    "field_name": "Maximum Condenser Inlet Node Temperature in Heating Mode",
                    "field_type": "n"
                },
                "heating_capacity_ratio_modifier_function_of_low_temperature_curve_name": {
                    "field_name": "Heating Capacity Ratio Modifier Function of Low Temperature Curve Name",
                    "field_type": "a"
                },
                "heating_capacity_ratio_boundary_curve_name": {
                    "field_name": "Heating Capacity Ratio Boundary Curve Name",
                    "field_type": "a"
                },
                "heating_capacity_ratio_modifier_function_of_high_temperature_curve_name": {
                    "field_name": "Heating Capacity Ratio Modifier Function of High Temperature Curve Name",
                    "field_type": "a"
                },
                "heating_energy_input_ratio_modifier_function_of_low_temperature_curve_name": {
                    "field_name": "Heating Energy Input Ratio Modifier Function of Low Temperature Curve Name",
                    "field_type": "a"
                },
                "heating_energy_input_ratio_boundary_curve_name": {
                    "field_name": "Heating Energy Input Ratio Boundary Curve Name",
                    "field_type": "a"
                },
                "heating_energy_input_ratio_modifier_function_of_high_temperature_curve_name": {
                    "field_name": "Heating Energy Input Ratio Modifier Function of High Temperature Curve Name",
                    "field_type": "a"
                },
                "heating_performance_curve_outdoor_temperature_type": {
                    "field_name": "Heating Performance Curve Outdoor Temperature Type",
                    "field_type": "a"
                },
                "heating_energy_input_ratio_modifier_function_of_low_part_load_ratio_curve_name": {
                    "field_name": "Heating Energy Input Ratio Modifier Function of Low Part-Load Ratio Curve Name",
                    "field_type": "a"
                },
                "heating_energy_input_ratio_modifier_function_of_high_part_load_ratio_curve_name": {
                    "field_name": "Heating Energy Input Ratio Modifier Function of High Part-Load Ratio Curve Name",
                    "field_type": "a"
                },
                "heating_combination_ratio_correction_factor_curve_name": {
                    "field_name": "Heating Combination Ratio Correction Factor Curve Name",
                    "field_type": "a"
                },
                "heating_part_load_fraction_correlation_curve_name": {
                    "field_name": "Heating Part-Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "minimum_heat_pump_part_load_ratio": {
                    "field_name": "Minimum Heat Pump Part-Load Ratio",
                    "field_type": "n"
                },
                "zone_name_for_master_thermostat_location": {
                    "field_name": "Zone Name for Master Thermostat Location",
                    "field_type": "a"
                },
                "master_thermostat_priority_control_type": {
                    "field_name": "Master Thermostat Priority Control Type",
                    "field_type": "a"
                },
                "thermostat_priority_schedule_name": {
                    "field_name": "Thermostat Priority Schedule Name",
                    "field_type": "a"
                },
                "zone_terminal_unit_list_name": {
                    "field_name": "Zone Terminal Unit List Name",
                    "field_type": "a"
                },
                "heat_pump_waste_heat_recovery": {
                    "field_name": "Heat Pump Waste Heat Recovery",
                    "field_type": "a"
                },
                "equivalent_piping_length_used_for_piping_correction_factor_in_cooling_mode": {
                    "field_name": "Equivalent Piping Length used for Piping Correction Factor in Cooling Mode",
                    "field_type": "n"
                },
                "vertical_height_used_for_piping_correction_factor": {
                    "field_name": "Vertical Height used for Piping Correction Factor",
                    "field_type": "n"
                },
                "piping_correction_factor_for_length_in_cooling_mode_curve_name": {
                    "field_name": "Piping Correction Factor for Length in Cooling Mode Curve Name",
                    "field_type": "a"
                },
                "piping_correction_factor_for_height_in_cooling_mode_coefficient": {
                    "field_name": "Piping Correction Factor for Height in Cooling Mode Coefficient",
                    "field_type": "n"
                },
                "equivalent_piping_length_used_for_piping_correction_factor_in_heating_mode": {
                    "field_name": "Equivalent Piping Length used for Piping Correction Factor in Heating Mode",
                    "field_type": "n"
                },
                "piping_correction_factor_for_length_in_heating_mode_curve_name": {
                    "field_name": "Piping Correction Factor for Length in Heating Mode Curve Name",
                    "field_type": "a"
                },
                "piping_correction_factor_for_height_in_heating_mode_coefficient": {
                    "field_name": "Piping Correction Factor for Height in Heating Mode Coefficient",
                    "field_type": "n"
                },
                "crankcase_heater_power_per_compressor": {
                    "field_name": "Crankcase Heater Power per Compressor",
                    "field_type": "n"
                },
                "number_of_compressors": {
                    "field_name": "Number of Compressors",
                    "field_type": "n"
                },
                "ratio_of_compressor_size_to_total_compressor_capacity": {
                    "field_name": "Ratio of Compressor Size to Total Compressor Capacity",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater": {
                    "field_name": "Maximum Outdoor Dry-Bulb Temperature for Crankcase Heater",
                    "field_type": "n"
                },
                "defrost_strategy": {
                    "field_name": "Defrost Strategy",
                    "field_type": "a"
                },
                "defrost_control": {
                    "field_name": "Defrost Control",
                    "field_type": "a"
                },
                "defrost_energy_input_ratio_modifier_function_of_temperature_curve_name": {
                    "field_name": "Defrost Energy Input Ratio Modifier Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "defrost_time_period_fraction": {
                    "field_name": "Defrost Time Period Fraction",
                    "field_type": "n"
                },
                "resistive_defrost_heater_capacity": {
                    "field_name": "Resistive Defrost Heater Capacity",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_defrost_operation": {
                    "field_name": "Maximum Outdoor Dry-bulb Temperature for Defrost Operation",
                    "field_type": "n"
                },
                "condenser_type": {
                    "field_name": "Condenser Type",
                    "field_type": "a"
                },
                "condenser_inlet_node_name": {
                    "field_name": "Condenser Inlet Node Name",
                    "field_type": "a"
                },
                "condenser_outlet_node_name": {
                    "field_name": "Condenser Outlet Node Name",
                    "field_type": "a"
                },
                "water_condenser_volume_flow_rate": {
                    "field_name": "Water Condenser Volume Flow Rate",
                    "field_type": "n"
                },
                "evaporative_condenser_effectiveness": {
                    "field_name": "Evaporative Condenser Effectiveness",
                    "field_type": "n"
                },
                "evaporative_condenser_air_flow_rate": {
                    "field_name": "Evaporative Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "evaporative_condenser_pump_rated_power_consumption": {
                    "field_name": "Evaporative Condenser Pump Rated Power Consumption",
                    "field_type": "n"
                },
                "supply_water_storage_tank_name": {
                    "field_name": "Supply Water Storage Tank Name",
                    "field_type": "a"
                },
                "basin_heater_capacity": {
                    "field_name": "Basin Heater Capacity",
                    "field_type": "n"
                },
                "basin_heater_setpoint_temperature": {
                    "field_name": "Basin Heater Setpoint Temperature",
                    "field_type": "n"
                },
                "basin_heater_operating_schedule_name": {
                    "field_name": "Basin Heater Operating Schedule Name",
                    "field_type": "a"
                },
                "fuel_type": {
                    "field_name": "Fuel Type",
                    "field_type": "a"
                },
                "minimum_condenser_inlet_node_temperature_in_heat_recovery_mode": {
                    "field_name": "Minimum Condenser Inlet Node Temperature in Heat Recovery Mode",
                    "field_type": "n"
                },
                "maximum_condenser_inlet_node_temperature_in_heat_recovery_mode": {
                    "field_name": "Maximum Condenser Inlet Node Temperature in Heat Recovery Mode",
                    "field_type": "n"
                },
                "heat_recovery_cooling_capacity_modifier_curve_name": {
                    "field_name": "Heat Recovery Cooling Capacity Modifier Curve Name",
                    "field_type": "a"
                },
                "initial_heat_recovery_cooling_capacity_fraction": {
                    "field_name": "Initial Heat Recovery Cooling Capacity Fraction",
                    "field_type": "n"
                },
                "heat_recovery_cooling_capacity_time_constant": {
                    "field_name": "Heat Recovery Cooling Capacity Time Constant",
                    "field_type": "n"
                },
                "heat_recovery_cooling_energy_modifier_curve_name": {
                    "field_name": "Heat Recovery Cooling Energy Modifier Curve Name",
                    "field_type": "a"
                },
                "initial_heat_recovery_cooling_energy_fraction": {
                    "field_name": "Initial Heat Recovery Cooling Energy Fraction",
                    "field_type": "n"
                },
                "heat_recovery_cooling_energy_time_constant": {
                    "field_name": "Heat Recovery Cooling Energy Time Constant",
                    "field_type": "n"
                },
                "heat_recovery_heating_capacity_modifier_curve_name": {
                    "field_name": "Heat Recovery Heating Capacity Modifier Curve Name",
                    "field_type": "a"
                },
                "initial_heat_recovery_heating_capacity_fraction": {
                    "field_name": "Initial Heat Recovery Heating Capacity Fraction",
                    "field_type": "n"
                },
                "heat_recovery_heating_capacity_time_constant": {
                    "field_name": "Heat Recovery Heating Capacity Time Constant",
                    "field_type": "n"
                },
                "heat_recovery_heating_energy_modifier_curve_name": {
                    "field_name": "Heat Recovery Heating Energy Modifier Curve Name",
                    "field_type": "a"
                },
                "initial_heat_recovery_heating_energy_fraction": {
                    "field_name": "Initial Heat Recovery Heating Energy Fraction",
                    "field_type": "n"
                },
                "heat_recovery_heating_energy_time_constant": {
                    "field_name": "Heat Recovery Heating Energy Time Constant",
                    "field_type": "n"
                },
                "name": {
                    "field_name": "Heat Pump Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "gross_rated_total_cooling_capacity",
                "gross_rated_cooling_cop",
                "minimum_condenser_inlet_node_temperature_in_cooling_mode",
                "maximum_condenser_inlet_node_temperature_in_cooling_mode",
                "cooling_capacity_ratio_modifier_function_of_low_temperature_curve_name",
                "cooling_capacity_ratio_boundary_curve_name",
                "cooling_capacity_ratio_modifier_function_of_high_temperature_curve_name",
                "cooling_energy_input_ratio_modifier_function_of_low_temperature_curve_name",
                "cooling_energy_input_ratio_boundary_curve_name",
                "cooling_energy_input_ratio_modifier_function_of_high_temperature_curve_name",
                "cooling_energy_input_ratio_modifier_function_of_low_part_load_ratio_curve_name",
                "cooling_energy_input_ratio_modifier_function_of_high_part_load_ratio_curve_name",
                "cooling_combination_ratio_correction_factor_curve_name",
                "cooling_part_load_fraction_correlation_curve_name",
                "gross_rated_heating_capacity",
                "rated_heating_capacity_sizing_ratio",
                "gross_rated_heating_cop",
                "minimum_condenser_inlet_node_temperature_in_heating_mode",
                "maximum_condenser_inlet_node_temperature_in_heating_mode",
                "heating_capacity_ratio_modifier_function_of_low_temperature_curve_name",
                "heating_capacity_ratio_boundary_curve_name",
                "heating_capacity_ratio_modifier_function_of_high_temperature_curve_name",
                "heating_energy_input_ratio_modifier_function_of_low_temperature_curve_name",
                "heating_energy_input_ratio_boundary_curve_name",
                "heating_energy_input_ratio_modifier_function_of_high_temperature_curve_name",
                "heating_performance_curve_outdoor_temperature_type",
                "heating_energy_input_ratio_modifier_function_of_low_part_load_ratio_curve_name",
                "heating_energy_input_ratio_modifier_function_of_high_part_load_ratio_curve_name",
                "heating_combination_ratio_correction_factor_curve_name",
                "heating_part_load_fraction_correlation_curve_name",
                "minimum_heat_pump_part_load_ratio",
                "zone_name_for_master_thermostat_location",
                "master_thermostat_priority_control_type",
                "thermostat_priority_schedule_name",
                "zone_terminal_unit_list_name",
                "heat_pump_waste_heat_recovery",
                "equivalent_piping_length_used_for_piping_correction_factor_in_cooling_mode",
                "vertical_height_used_for_piping_correction_factor",
                "piping_correction_factor_for_length_in_cooling_mode_curve_name",
                "piping_correction_factor_for_height_in_cooling_mode_coefficient",
                "equivalent_piping_length_used_for_piping_correction_factor_in_heating_mode",
                "piping_correction_factor_for_length_in_heating_mode_curve_name",
                "piping_correction_factor_for_height_in_heating_mode_coefficient",
                "crankcase_heater_power_per_compressor",
                "number_of_compressors",
                "ratio_of_compressor_size_to_total_compressor_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater",
                "defrost_strategy",
                "defrost_control",
                "defrost_energy_input_ratio_modifier_function_of_temperature_curve_name",
                "defrost_time_period_fraction",
                "resistive_defrost_heater_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_defrost_operation",
                "condenser_type",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name",
                "water_condenser_volume_flow_rate",
                "evaporative_condenser_effectiveness",
                "evaporative_condenser_air_flow_rate",
                "evaporative_condenser_pump_rated_power_consumption",
                "supply_water_storage_tank_name",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "basin_heater_operating_schedule_name",
                "fuel_type",
                "minimum_condenser_inlet_node_temperature_in_heat_recovery_mode",
                "maximum_condenser_inlet_node_temperature_in_heat_recovery_mode",
                "heat_recovery_cooling_capacity_modifier_curve_name",
                "initial_heat_recovery_cooling_capacity_fraction",
                "heat_recovery_cooling_capacity_time_constant",
                "heat_recovery_cooling_energy_modifier_curve_name",
                "initial_heat_recovery_cooling_energy_fraction",
                "heat_recovery_cooling_energy_time_constant",
                "heat_recovery_heating_capacity_modifier_curve_name",
                "initial_heat_recovery_heating_capacity_fraction",
                "heat_recovery_heating_capacity_time_constant",
                "heat_recovery_heating_energy_modifier_curve_name",
                "initial_heat_recovery_heating_energy_fraction",
                "heat_recovery_heating_energy_time_constant"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "cooling_capacity_ratio_modifier_function_of_low_temperature_curve_name",
                    "cooling_capacity_ratio_boundary_curve_name",
                    "cooling_capacity_ratio_modifier_function_of_high_temperature_curve_name",
                    "cooling_energy_input_ratio_modifier_function_of_low_temperature_curve_name",
                    "cooling_energy_input_ratio_boundary_curve_name",
                    "cooling_energy_input_ratio_modifier_function_of_high_temperature_curve_name",
                    "cooling_energy_input_ratio_modifier_function_of_low_part_load_ratio_curve_name",
                    "cooling_energy_input_ratio_modifier_function_of_high_part_load_ratio_curve_name",
                    "cooling_combination_ratio_correction_factor_curve_name",
                    "cooling_part_load_fraction_correlation_curve_name",
                    "heating_capacity_ratio_modifier_function_of_low_temperature_curve_name",
                    "heating_capacity_ratio_boundary_curve_name",
                    "heating_capacity_ratio_modifier_function_of_high_temperature_curve_name",
                    "heating_energy_input_ratio_modifier_function_of_low_temperature_curve_name",
                    "heating_energy_input_ratio_boundary_curve_name",
                    "heating_energy_input_ratio_modifier_function_of_high_temperature_curve_name",
                    "heating_performance_curve_outdoor_temperature_type",
                    "heating_energy_input_ratio_modifier_function_of_low_part_load_ratio_curve_name",
                    "heating_energy_input_ratio_modifier_function_of_high_part_load_ratio_curve_name",
                    "heating_combination_ratio_correction_factor_curve_name",
                    "heating_part_load_fraction_correlation_curve_name",
                    "zone_name_for_master_thermostat_location",
                    "master_thermostat_priority_control_type",
                    "thermostat_priority_schedule_name",
                    "zone_terminal_unit_list_name",
                    "heat_pump_waste_heat_recovery",
                    "piping_correction_factor_for_length_in_cooling_mode_curve_name",
                    "piping_correction_factor_for_length_in_heating_mode_curve_name",
                    "defrost_strategy",
                    "defrost_control",
                    "defrost_energy_input_ratio_modifier_function_of_temperature_curve_name",
                    "condenser_type",
                    "condenser_inlet_node_name",
                    "condenser_outlet_node_name",
                    "supply_water_storage_tank_name",
                    "basin_heater_operating_schedule_name",
                    "fuel_type",
                    "heat_recovery_cooling_capacity_modifier_curve_name",
                    "heat_recovery_cooling_energy_modifier_curve_name",
                    "heat_recovery_heating_capacity_modifier_curve_name",
                    "heat_recovery_heating_energy_modifier_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "gross_rated_total_cooling_capacity",
                    "gross_rated_cooling_cop",
                    "minimum_condenser_inlet_node_temperature_in_cooling_mode",
                    "maximum_condenser_inlet_node_temperature_in_cooling_mode",
                    "gross_rated_heating_capacity",
                    "rated_heating_capacity_sizing_ratio",
                    "gross_rated_heating_cop",
                    "minimum_condenser_inlet_node_temperature_in_heating_mode",
                    "maximum_condenser_inlet_node_temperature_in_heating_mode",
                    "minimum_heat_pump_part_load_ratio",
                    "equivalent_piping_length_used_for_piping_correction_factor_in_cooling_mode",
                    "vertical_height_used_for_piping_correction_factor",
                    "piping_correction_factor_for_height_in_cooling_mode_coefficient",
                    "equivalent_piping_length_used_for_piping_correction_factor_in_heating_mode",
                    "piping_correction_factor_for_height_in_heating_mode_coefficient",
                    "crankcase_heater_power_per_compressor",
                    "number_of_compressors",
                    "ratio_of_compressor_size_to_total_compressor_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater",
                    "defrost_time_period_fraction",
                    "resistive_defrost_heater_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_defrost_operation",
                    "water_condenser_volume_flow_rate",
                    "evaporative_condenser_effectiveness",
                    "evaporative_condenser_air_flow_rate",
                    "evaporative_condenser_pump_rated_power_consumption",
                    "basin_heater_capacity",
                    "basin_heater_setpoint_temperature",
                    "minimum_condenser_inlet_node_temperature_in_heat_recovery_mode",
                    "maximum_condenser_inlet_node_temperature_in_heat_recovery_mode",
                    "initial_heat_recovery_cooling_capacity_fraction",
                    "heat_recovery_cooling_capacity_time_constant",
                    "initial_heat_recovery_cooling_energy_fraction",
                    "heat_recovery_cooling_energy_time_constant",
                    "initial_heat_recovery_heating_capacity_fraction",
                    "heat_recovery_heating_capacity_time_constant",
                    "initial_heat_recovery_heating_energy_fraction",
                    "heat_recovery_heating_energy_time_constant"
                ]
            }
        },
        "type": "object",
        "memo": "Variable refrigerant flow (VRF) air-to-air heat pump condensing unit (includes one or more electric compressors and outdoor fan). Serves one or more VRF zone terminal units. See ZoneHVAC:TerminalUnit:VariableRefrigerantFlow and ZoneTerminalUnitList.",
        "min_fields": 37.0,
        "name": {
            "type": "string",
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames"
            ],
            "note": "Enter a unique name for this variable refrigerant flow heat pump."
        }
    }
}
```
