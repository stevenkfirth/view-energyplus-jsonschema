```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "operating_mode_control_method": {
                    "type": "string",
                    "enum": [
                        "EMSControlled",
                        "ScheduledModes"
                    ]
                },
                "operation_mode_control_schedule_name": {
                    "type": "string",
                    "note": "This field is used if the control method is set to ScheduledModes Schedule values control operating mode: 0=off, 1=cooling only, 2= cooling and charge, 3= cooling and discharge, 4= charge only, and 5= discharge only",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "storage_type": {
                    "type": "string",
                    "enum": [
                        "Ice",
                        "UserDefinedFluidType",
                        "Water"
                    ]
                },
                "user_defined_fluid_type": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FluidAndGlycolNames"
                    ],
                    "note": "This field is required when Storage Type is UserDefinedFluidType"
                },
                "fluid_storage_volume": {
                    "units": "m3",
                    "ip-units": "gal",
                    "note": "required field if Storage Type is Water or UserDefinedFluidType",
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
                "ice_storage_capacity": {
                    "units": "GJ",
                    "note": "required field if Storage Type is Ice",
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
                "storage_capacity_sizing_factor": {
                    "type": "number",
                    "units": "hr",
                    "note": "If one of the previous two fields is set to autocalculate, this determines the storage capacity as a function of Cooling Only Mode Rated Total Evaporator Cooling Capacity"
                },
                "storage_tank_ambient_temperature_node_name": {
                    "type": "string"
                },
                "storage_tank_to_ambient_u_value_times_area_heat_transfer_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "exclusiveMinimum": 0.0
                },
                "fluid_storage_tank_rating_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "required field if Storage Type is Water or UserDefinedFluidType"
                },
                "rated_evaporator_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Flow rate corresponding to rated total cooling capacity, Rated SHR and Rated COP",
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
                "evaporator_air_inlet_node_name": {
                    "type": "string"
                },
                "evaporator_air_outlet_node_name": {
                    "type": "string"
                },
                "cooling_only_mode_available": {
                    "type": "string",
                    "enum": [
                        "No",
                        "Yes"
                    ]
                },
                "cooling_only_mode_rated_total_evaporator_cooling_capacity": {
                    "note": "required field if Cooling Only Mode is available or if autocalculating sizes gross capacity excluding supply air fan heat rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "cooling_only_mode_rated_sensible_heat_ratio": {
                    "type": "number",
                    "note": "required field if Cooling Only Mode is available Rated sensible heat ratio (gross sensible capacity/gross total capacity) sensible and total capacities do not include supply fan heat",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7
                },
                "cooling_only_mode_rated_cop": {
                    "type": "number",
                    "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input required field if Cooling Only Mode is available",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.0
                },
                "cooling_only_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling Only Mode is available Any curve or table with two independent variables can be used biquadratic curve = a + b*ewb + c*ewb**2 + d*db + e*db**2 + f*ewb*db x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "cooling_only_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling Only Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow rate",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_only_mode_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling Only Mode is available Any curve or table with two independent variables can be used curve = a + b*ewb + c*ewb**2 + d*db + e*db**2 + f*ewb*db x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "cooling_only_mode_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling Only Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_only_mode_part_load_fraction_correlation_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling Only Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 x = PLR = part load ratio (evaporator cooling load/steady state capacity)",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_only_mode_sensible_heat_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling Only Mode is available Any curve or table with two independent variables can be used curve = a + b*ewb + c*ewb**2 + d*edb + e*edb**2 + f*ewb*edb x = ewb = evaporator entering wet-bulb temperature seen by the cooling coil (C) y = edb = evaporator entering dry-bulb temperature seen by the cooling coil (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "cooling_only_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling Only Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_available": {
                    "type": "string",
                    "enum": [
                        "No",
                        "Yes"
                    ]
                },
                "cooling_and_charge_mode_rated_total_evaporator_cooling_capacity": {
                    "note": "required field if Cooling And Charge Mode is available gross capacity excluding supply air fan heat rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb thermal storage tank at Fluid Storage Tank Rating Temperature (water or fluid) or storage faction of 0.5 (ice)",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "cooling_and_charge_mode_capacity_sizing_factor": {
                    "type": "number",
                    "default": 0.5,
                    "note": "If previous field is autocalculate, this determines the evaporator capacity as a multiplier on the Cooling Only Mode Rated Total Evaporator Cooling Capacity"
                },
                "cooling_and_charge_mode_rated_storage_charging_capacity": {
                    "note": "required field if Cooling And Charge Mode is available net capacity including any internal devices rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb thermal storage tank at Fluid Storage Tank Rating Temperature (water or fluid) or storage faction of 0.5 (ice)",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "cooling_and_charge_mode_storage_capacity_sizing_factor": {
                    "type": "number",
                    "default": 0.5,
                    "note": "If previous field is autocalculate, this determines the storage cooling capacity as a multiplier on the Cooling Only Mode Rated Total Evaporator Cooling Capacity"
                },
                "cooling_and_charge_mode_rated_sensible_heat_ratio": {
                    "type": "number",
                    "note": "required field if Cooling And Charge Mode is available Rated sensible heat ratio (gross sensible evaporator capacity/gross total evaporator capacity) sensible and total capacities do not include supply fan heat",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7
                },
                "cooling_and_charge_mode_cooling_rated_cop": {
                    "type": "number",
                    "note": "Gross evaporator cooling capacity divided by power input to the compressor (for cooling) and outdoor fan, does not include supply fan heat or supply fan electrical energy input required field if Cooling And Charge Mode is available",
                    "units": "W/W",
                    "minimum": 0.0,
                    "default": 3.0
                },
                "cooling_and_charge_mode_charging_rated_cop": {
                    "type": "number",
                    "note": "net cooling capacity divided by power input to the compressor (for charging) and outdoor fan, includes any internal devices required field if Cooling And Charge Mode is available",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.0
                },
                "cooling_and_charge_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Allowed curve or table objects are Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = db, z = stes) x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_evaporator_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Allowed curve or table objects are Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = db, z = stes) x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_evaporator_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_evaporator_part_load_fraction_correlation_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 x = PLR = part load ratio (evaporator cooling load/steady state capacity)",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_storage_charge_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Allowed curve or table objects are Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = db, z = stes) x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_storage_charge_capacity_function_of_total_evaporator_plr_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 x = PLR = part load ratio (evaporator cooling load/steady state capacity)",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_storage_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Allowed curve or table objects are Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = db, z = stes) x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_storage_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_storage_energy_part_load_fraction_correlation_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 x = PLR = part load ratio (evaporator cooling load/steady state capacity)",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_sensible_heat_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Curves or tables with either two or three independent variables can be used. Curve:Biquadratic, Table:Lookup, Curve:Bicubic and Curve:QuadraticLinear allowed curve = a + b*ewb + c*ewb**2 + d*edb + e*edb**2 + f*ewb*edb x = ewb = entering wet-bulb temperature seen by the cooling coil (C) y = edb = entering dry-bulb temperature seen by the cooling coil (C) Also allows Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = edb, z = stes) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_charge_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Charge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_available": {
                    "type": "string",
                    "enum": [
                        "No",
                        "Yes"
                    ]
                },
                "cooling_and_discharge_mode_rated_total_evaporator_cooling_capacity": {
                    "note": "required field if Cooling And Discharge Mode is available gross capacity excluding supply air fan heat rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb thermal storage tank at Fluid Storage Tank Rating Temperature (water or fluid) or storage faction of 0.5 (ice)",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "cooling_and_discharge_mode_evaporator_capacity_sizing_factor": {
                    "type": "number",
                    "default": 1.0,
                    "note": "If previous field is autocalculate, this determines the charging capacity as a multiplier on the Cooling Only Mode Rated Total Evaporator Cooling Capacity"
                },
                "cooling_and_discharge_mode_rated_storage_discharging_capacity": {
                    "note": "required field if Cooling And Discharge Mode is available net capacity including any internal devices rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb thermal storage tank at 26.7 C (water) or storage faction of 0.5 (ice)",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "cooling_and_discharge_mode_storage_discharge_capacity_sizing_factor": {
                    "type": "number",
                    "default": 1.0,
                    "note": "If previous field is autocalculate, this determines the charging capacity as a multiplier on the Cooling Only Mode Rated Total Evaporator Cooling Capacity"
                },
                "cooling_and_discharge_mode_rated_sensible_heat_ratio": {
                    "type": "number",
                    "note": "required field if Cooling And Discharge Mode is available Rated sensible heat ratio (gross sensible evaporator capacity/gross total evaporator capacity) sensible and total capacities do not include supply fan heat",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7
                },
                "cooling_and_discharge_mode_cooling_rated_cop": {
                    "type": "number",
                    "note": "Gross evaporator cooling capacity divided by power input to the compressor (for cooling) and outdoor fan, does not include supply fan heat or supply fan electrical energy input required field if Cooling And Discharge Mode is available",
                    "units": "W/W",
                    "minimum": 0.0,
                    "default": 3.0
                },
                "cooling_and_discharge_mode_discharging_rated_cop": {
                    "type": "number",
                    "note": "gross cooling capacity divided by power input to the compressor (for discharging), includes any internal devices for discharging storage but not supply fan required field if Cooling And Discharge Mode is available",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.0
                },
                "cooling_and_discharge_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling Only Mode is available Allowed curve or table objects are Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = db, z = stes) x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_evaporator_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Allowed curve or table objects are Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = db, z = stes) x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_evaporator_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_evaporator_part_load_fraction_correlation_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 x = PLR = part load ratio (evaporator cooling load/steady state capacity)",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_storage_discharge_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Allowed curve or table objects are Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = db, z = stes) x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_storage_discharge_capacity_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_storage_discharge_capacity_function_of_total_evaporator_plr_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 x =PLR = part load ratio (evaporator cooling load/steady state capacity)",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_storage_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Allowed curve or table objects are Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = db, z = stes) x = ewb = evaporator entering wet-bulb temperature (C) y = db = dry-bulb temperature seen by the condenser (C) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_storage_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_storage_energy_part_load_fraction_correlation_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 x = PLR = part load ratio (evaporator cooling load/steady state capacity)",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_sensible_heat_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Curves or tables with either two or three independent variables can be used. curve = a + b*ewb + c*ewb**2 + d*edb + e*edb**2 + f*ewb*edb x = ewb = entering wet-bulb temperature seen by the cooling coil (C) y = edb = entering dry-bulb temperature seen by the cooling coil (C) Also allows Curve:Triquadratic and Table:Lookup curve or table = func(x = ewb, y = edb, z = stes) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "TrivariateFunctions"
                    ]
                },
                "cooling_and_discharge_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Cooling And Discharge Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "charge_only_mode_available": {
                    "type": "string",
                    "enum": [
                        "No",
                        "Yes"
                    ]
                },
                "charge_only_mode_rated_storage_charging_capacity": {
                    "note": "required field if Charge Only  Mode is available net capacity including any internal devices air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb thermal storage tank at 26.7 C (water) or storage faction of 0.5 (ice)",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "charge_only_mode_capacity_sizing_factor": {
                    "type": "number",
                    "default": 1.0,
                    "note": "If previous field is autocalculate, this determines the charging capacity as a multiplier on the Cooling Only Mode Rated Total Evaporator Cooling Capacity"
                },
                "charge_only_mode_charging_rated_cop": {
                    "type": "number",
                    "note": "net cooling capacity divided by power input to the compressor (for charging) and outdoor fan, includes any internal devices required field if Charge Only Mode is available",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.0
                },
                "charge_only_mode_storage_charge_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Charge Only Mode is available Any curve or table with two independent variables can be used curve = a + b*db + c*db**2 + d*stes + e*stes**2 + f*db*stes x = db = dry-bulb temperature seen by the condenser (C) y = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "charge_only_mode_storage_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Charge Only Mode is available Any curve or table with two independent variables can be used curve = a + b*db + c*db**2 + d*stes + e*stes**2 + f*db*stes x = db = dry-bulb temperature seen by the condenser (C) y = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "discharge_only_mode_available": {
                    "type": "string",
                    "enum": [
                        "No",
                        "Yes"
                    ]
                },
                "discharge_only_mode_rated_storage_discharging_capacity": {
                    "note": "required field if Discharge Only Mode is available net capacity including any internal devices rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and thermal storage tank at 26.7 C (water) or storage faction of 0.5 (ice)",
                    "units": "W",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "discharge_only_mode_capacity_sizing_factor": {
                    "type": "number",
                    "default": 1.0,
                    "note": "If previous field is autocalculate, this determines the discharging capacity as a multiplier on the Cooling Only Mode Rated Total Evaporator Cooling Capacity"
                },
                "discharge_only_mode_rated_sensible_heat_ratio": {
                    "type": "number",
                    "note": "required field if Discharge Only Mode is available Rated sensible heat ratio (gross sensible evaporator capacity/gross total evaporator capacity) sensible and total capacities do not include supply fan heat",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "discharge_only_mode_rated_cop": {
                    "type": "number",
                    "note": "required field if Discharge Only Mode is available gross cooling capacity divided by power input to the compressor (for discharging), includes any internal devices for discharging storage but not supply fan",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.0
                },
                "discharge_only_mode_storage_discharge_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Discharge Only Mode is available Any curve or table with two independent variables can be used curve = a + b*ewb + c*ewb**2 + d*stes + e*stes**2 + f*ewb*stes x = ewb = evaporator entering wet-bulb temperature (C) y = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "discharge_only_mode_storage_discharge_capacity_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Discharge Only Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "discharge_only_mode_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Discharge Only Mode is available Any curve or table with two independent variables can be used curve = a + b*ewb + c*ewb**2 + d*stes + e*stes**2 + f*ewb*stes x = ewb = evaporator entering wet-bulb temperature (C) y = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "discharge_only_mode_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Discharge Only Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 x = ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "discharge_only_mode_part_load_fraction_correlation_curve_name": {
                    "type": "string",
                    "note": "required field if Discharge Only Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "discharge_only_mode_sensible_heat_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "required field if Discharge Only Mode is available Curves or tables with either two or three independent variables can be used. For two independent variables: x = ewb = entering wet-bulb temperature seen by the cooling coil (C) y = edb = entering dry-bulb temperature seen by the cooling coil (C) For three independent variables: curve or table = func(x = ewb, y = edb, z = stes) z = stes = state of thermal energy storage (C or fraction)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "TrivariateFunctions"
                    ]
                },
                "discharge_only_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "required field if Discharge Only Mode is available Any curve or table with one independent variable can be used quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = Fraction of the full load evaporator air flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "ancillary_electric_power": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "note": "controls and miscellaneous standby ancillary electric power draw, when available"
                },
                "cold_weather_operation_minimum_outdoor_air_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "cold_weather_operation_ancillary_power": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0
                },
                "condenser_air_inlet_node_name": {
                    "type": "string",
                    "note": "Enter the name of an outdoor air node. This node name is also specified in an OutdoorAir:Node or OutdoorAir:NodeList object."
                },
                "condenser_air_outlet_node_name": {
                    "type": "string"
                },
                "condenser_design_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Used to calculate condenser leaving conditions and water use if evaporatively cooled.",
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
                "condenser_air_flow_sizing_factor": {
                    "type": "number",
                    "default": 1.0,
                    "note": "If previous field is autocalculate, this determines the condenser air flow size as a multiplier on the Rated Evaporator Air Flow Rate."
                },
                "condenser_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AirCooled",
                        "EvaporativelyCooled"
                    ],
                    "default": "AirCooled"
                },
                "evaporative_condenser_effectiveness": {
                    "type": "number",
                    "note": "required field if condenser type is evaporatively cooled",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7
                },
                "evaporative_condenser_pump_rated_power_consumption": {
                    "units": "W",
                    "default": 0.0,
                    "note": "Rated power consumed by the evaporative condenser's water pump",
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
                "basin_heater_capacity": {
                    "type": "number",
                    "units": "W/K",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled and for periods when the basin heater is available (field Basin Heater Operating Schedule Name). For this situation, the heater maintains the basin water temperature at the basin heater setpoint temperature when the outdoor air temperature falls below the setpoint temperature. The basin heater only operates when the DX coil is off. If this field is blank, the basin heater is always available."
                },
                "basin_heater_setpoint_temperature": {
                    "type": "number",
                    "units": "C",
                    "minimum": 2.0,
                    "default": 2.0,
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled. Enter the outdoor dry-bulb temperature when the basin heater turns on."
                },
                "basin_heater_availability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled. Schedule values greater than 0 allow the basin heater to operate whenever the outdoor air dry-bulb temperature is below the basin heater setpoint temperature. If a schedule name is not entered, the basin heater is allowed to operate throughout the entire simulation."
                },
                "supply_water_storage_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
                },
                "condensate_collection_water_storage_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
                },
                "storage_tank_plant_connection_inlet_node_name": {
                    "type": "string"
                },
                "storage_tank_plant_connection_outlet_node_name": {
                    "type": "string"
                },
                "storage_tank_plant_connection_design_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "storage_tank_plant_connection_heat_transfer_effectiveness": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7
                },
                "storage_tank_minimum_operating_limit_fluid_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "For fluid storage tanks only, minimum limit for storage tank If omitted,then the minimum temperature limit is that used for fluid property data."
                },
                "storage_tank_maximum_operating_limit_fluid_temperature": {
                    "type": "number",
                    "units": "C",
                    "note": "For fluid storage tanks only, maximum limit for storage tank If omitted,then the maximum temperature limit is that used for fluid property data."
                }
            },
            "required": [
                "operating_mode_control_method",
                "storage_type",
                "storage_tank_ambient_temperature_node_name",
                "storage_tank_to_ambient_u_value_times_area_heat_transfer_coefficient",
                "rated_evaporator_air_flow_rate",
                "evaporator_air_inlet_node_name",
                "evaporator_air_outlet_node_name",
                "cooling_only_mode_available",
                "cooling_and_charge_mode_available",
                "cooling_and_discharge_mode_available",
                "charge_only_mode_available",
                "discharge_only_mode_available",
                "condenser_air_inlet_node_name",
                "condenser_air_outlet_node_name",
                "condenser_design_air_flow_rate"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AFNCoilNames",
            "CoolingCoilsDX",
            "CoolingCoilsDXMultiModeOrSingleSpeed",
            "CoolingCoilsDXSingleSpeed",
            "validBranchEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ]
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
            "operating_mode_control_method": {
                "field_name": "Operating Mode Control Method",
                "field_type": "a"
            },
            "operation_mode_control_schedule_name": {
                "field_name": "Operation Mode Control Schedule Name",
                "field_type": "a"
            },
            "storage_type": {
                "field_name": "Storage Type",
                "field_type": "a"
            },
            "user_defined_fluid_type": {
                "field_name": "User Defined Fluid Type",
                "field_type": "a"
            },
            "fluid_storage_volume": {
                "field_name": "Fluid Storage Volume",
                "field_type": "n"
            },
            "ice_storage_capacity": {
                "field_name": "Ice Storage Capacity",
                "field_type": "n"
            },
            "storage_capacity_sizing_factor": {
                "field_name": "Storage Capacity Sizing Factor",
                "field_type": "n"
            },
            "storage_tank_ambient_temperature_node_name": {
                "field_name": "Storage Tank Ambient Temperature Node Name",
                "field_type": "a"
            },
            "storage_tank_to_ambient_u_value_times_area_heat_transfer_coefficient": {
                "field_name": "Storage Tank to Ambient U-value Times Area Heat Transfer Coefficient",
                "field_type": "n"
            },
            "fluid_storage_tank_rating_temperature": {
                "field_name": "Fluid Storage Tank Rating Temperature",
                "field_type": "n"
            },
            "rated_evaporator_air_flow_rate": {
                "field_name": "Rated Evaporator Air Flow Rate",
                "field_type": "n"
            },
            "evaporator_air_inlet_node_name": {
                "field_name": "Evaporator Air Inlet Node Name",
                "field_type": "a"
            },
            "evaporator_air_outlet_node_name": {
                "field_name": "Evaporator Air Outlet Node Name",
                "field_type": "a"
            },
            "cooling_only_mode_available": {
                "field_name": "Cooling Only Mode Available",
                "field_type": "a"
            },
            "cooling_only_mode_rated_total_evaporator_cooling_capacity": {
                "field_name": "Cooling Only Mode Rated Total Evaporator Cooling Capacity",
                "field_type": "n"
            },
            "cooling_only_mode_rated_sensible_heat_ratio": {
                "field_name": "Cooling Only Mode Rated Sensible Heat Ratio",
                "field_type": "n"
            },
            "cooling_only_mode_rated_cop": {
                "field_name": "Cooling Only Mode Rated COP",
                "field_type": "n"
            },
            "cooling_only_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name": {
                "field_name": "Cooling Only Mode Total Evaporator Cooling Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_only_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling Only Mode Total Evaporator Cooling Capacity Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_only_mode_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Cooling Only Mode Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_only_mode_energy_input_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling Only Mode Energy Input Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_only_mode_part_load_fraction_correlation_curve_name": {
                "field_name": "Cooling Only Mode Part Load Fraction Correlation Curve Name",
                "field_type": "a"
            },
            "cooling_only_mode_sensible_heat_ratio_function_of_temperature_curve_name": {
                "field_name": "Cooling Only Mode Sensible Heat Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_only_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling Only Mode Sensible Heat Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_available": {
                "field_name": "Cooling And Charge Mode Available",
                "field_type": "a"
            },
            "cooling_and_charge_mode_rated_total_evaporator_cooling_capacity": {
                "field_name": "Cooling And Charge Mode Rated Total Evaporator Cooling Capacity",
                "field_type": "n"
            },
            "cooling_and_charge_mode_capacity_sizing_factor": {
                "field_name": "Cooling And Charge Mode Capacity Sizing Factor",
                "field_type": "n"
            },
            "cooling_and_charge_mode_rated_storage_charging_capacity": {
                "field_name": "Cooling And Charge Mode Rated Storage Charging Capacity",
                "field_type": "n"
            },
            "cooling_and_charge_mode_storage_capacity_sizing_factor": {
                "field_name": "Cooling And Charge Mode Storage Capacity Sizing Factor",
                "field_type": "n"
            },
            "cooling_and_charge_mode_rated_sensible_heat_ratio": {
                "field_name": "Cooling And Charge Mode Rated Sensible Heat Ratio",
                "field_type": "n"
            },
            "cooling_and_charge_mode_cooling_rated_cop": {
                "field_name": "Cooling And Charge Mode Cooling Rated COP",
                "field_type": "n"
            },
            "cooling_and_charge_mode_charging_rated_cop": {
                "field_name": "Cooling And Charge Mode Charging Rated COP",
                "field_type": "n"
            },
            "cooling_and_charge_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name": {
                "field_name": "Cooling And Charge Mode Total Evaporator Cooling Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling And Charge Mode Total Evaporator Cooling Capacity Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_evaporator_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Cooling And Charge Mode Evaporator Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_evaporator_energy_input_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling And Charge Mode Evaporator Energy Input Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_evaporator_part_load_fraction_correlation_curve_name": {
                "field_name": "Cooling And Charge Mode Evaporator Part Load Fraction Correlation Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_storage_charge_capacity_function_of_temperature_curve_name": {
                "field_name": "Cooling And Charge Mode Storage Charge Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_storage_charge_capacity_function_of_total_evaporator_plr_curve_name": {
                "field_name": "Cooling And Charge Mode Storage Charge Capacity Function of Total Evaporator PLR Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_storage_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Cooling And Charge Mode Storage Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_storage_energy_input_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling And Charge Mode Storage Energy Input Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_storage_energy_part_load_fraction_correlation_curve_name": {
                "field_name": "Cooling And Charge Mode Storage Energy Part Load Fraction Correlation Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_sensible_heat_ratio_function_of_temperature_curve_name": {
                "field_name": "Cooling And Charge Mode Sensible Heat Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_charge_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling And Charge Mode Sensible Heat Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_available": {
                "field_name": "Cooling And Discharge Mode Available",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_rated_total_evaporator_cooling_capacity": {
                "field_name": "Cooling And Discharge Mode Rated Total Evaporator Cooling Capacity",
                "field_type": "n"
            },
            "cooling_and_discharge_mode_evaporator_capacity_sizing_factor": {
                "field_name": "Cooling And Discharge Mode Evaporator Capacity Sizing Factor",
                "field_type": "n"
            },
            "cooling_and_discharge_mode_rated_storage_discharging_capacity": {
                "field_name": "Cooling And Discharge Mode Rated Storage Discharging Capacity",
                "field_type": "n"
            },
            "cooling_and_discharge_mode_storage_discharge_capacity_sizing_factor": {
                "field_name": "Cooling And Discharge Mode Storage Discharge Capacity Sizing Factor",
                "field_type": "n"
            },
            "cooling_and_discharge_mode_rated_sensible_heat_ratio": {
                "field_name": "Cooling And Discharge Mode Rated Sensible Heat Ratio",
                "field_type": "n"
            },
            "cooling_and_discharge_mode_cooling_rated_cop": {
                "field_name": "Cooling And Discharge Mode Cooling Rated COP",
                "field_type": "n"
            },
            "cooling_and_discharge_mode_discharging_rated_cop": {
                "field_name": "Cooling And Discharge Mode Discharging Rated COP",
                "field_type": "n"
            },
            "cooling_and_discharge_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name": {
                "field_name": "Cooling And Discharge Mode Total Evaporator Cooling Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling And Discharge Mode Total Evaporator Cooling Capacity Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_evaporator_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Cooling And Discharge Mode Evaporator Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_evaporator_energy_input_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling And Discharge Mode Evaporator Energy Input Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_evaporator_part_load_fraction_correlation_curve_name": {
                "field_name": "Cooling And Discharge Mode Evaporator Part Load Fraction Correlation Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_storage_discharge_capacity_function_of_temperature_curve_name": {
                "field_name": "Cooling And Discharge Mode Storage Discharge Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_storage_discharge_capacity_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling And Discharge Mode Storage Discharge Capacity Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_storage_discharge_capacity_function_of_total_evaporator_plr_curve_name": {
                "field_name": "Cooling And Discharge Mode Storage Discharge Capacity Function of Total Evaporator PLR Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_storage_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Cooling And Discharge Mode Storage Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_storage_energy_input_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling And Discharge Mode Storage Energy Input Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_storage_energy_part_load_fraction_correlation_curve_name": {
                "field_name": "Cooling And Discharge Mode Storage Energy Part Load Fraction Correlation Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_sensible_heat_ratio_function_of_temperature_curve_name": {
                "field_name": "Cooling And Discharge Mode Sensible Heat Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_and_discharge_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Cooling And Discharge Mode Sensible Heat Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "charge_only_mode_available": {
                "field_name": "Charge Only Mode Available",
                "field_type": "a"
            },
            "charge_only_mode_rated_storage_charging_capacity": {
                "field_name": "Charge Only Mode Rated Storage Charging Capacity",
                "field_type": "n"
            },
            "charge_only_mode_capacity_sizing_factor": {
                "field_name": "Charge Only Mode Capacity Sizing Factor",
                "field_type": "n"
            },
            "charge_only_mode_charging_rated_cop": {
                "field_name": "Charge Only Mode Charging Rated COP",
                "field_type": "n"
            },
            "charge_only_mode_storage_charge_capacity_function_of_temperature_curve_name": {
                "field_name": "Charge Only Mode Storage Charge Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "charge_only_mode_storage_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Charge Only Mode Storage Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "discharge_only_mode_available": {
                "field_name": "Discharge Only Mode Available",
                "field_type": "a"
            },
            "discharge_only_mode_rated_storage_discharging_capacity": {
                "field_name": "Discharge Only Mode Rated Storage Discharging Capacity",
                "field_type": "n"
            },
            "discharge_only_mode_capacity_sizing_factor": {
                "field_name": "Discharge Only Mode Capacity Sizing Factor",
                "field_type": "n"
            },
            "discharge_only_mode_rated_sensible_heat_ratio": {
                "field_name": "Discharge Only Mode Rated Sensible Heat Ratio",
                "field_type": "n"
            },
            "discharge_only_mode_rated_cop": {
                "field_name": "Discharge Only Mode Rated COP",
                "field_type": "n"
            },
            "discharge_only_mode_storage_discharge_capacity_function_of_temperature_curve_name": {
                "field_name": "Discharge Only Mode Storage Discharge Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "discharge_only_mode_storage_discharge_capacity_function_of_flow_fraction_curve_name": {
                "field_name": "Discharge Only Mode Storage Discharge Capacity Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "discharge_only_mode_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Discharge Only Mode Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "discharge_only_mode_energy_input_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Discharge Only Mode Energy Input Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "discharge_only_mode_part_load_fraction_correlation_curve_name": {
                "field_name": "Discharge Only Mode Part Load Fraction Correlation Curve Name",
                "field_type": "a"
            },
            "discharge_only_mode_sensible_heat_ratio_function_of_temperature_curve_name": {
                "field_name": "Discharge Only Mode Sensible Heat Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "discharge_only_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Discharge Only Mode Sensible Heat Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "ancillary_electric_power": {
                "field_name": "Ancillary Electric Power",
                "field_type": "n"
            },
            "cold_weather_operation_minimum_outdoor_air_temperature": {
                "field_name": "Cold Weather Operation Minimum Outdoor Air Temperature",
                "field_type": "n"
            },
            "cold_weather_operation_ancillary_power": {
                "field_name": "Cold Weather Operation Ancillary Power",
                "field_type": "n"
            },
            "condenser_air_inlet_node_name": {
                "field_name": "Condenser Air Inlet Node Name",
                "field_type": "a"
            },
            "condenser_air_outlet_node_name": {
                "field_name": "Condenser Air Outlet Node Name",
                "field_type": "a"
            },
            "condenser_design_air_flow_rate": {
                "field_name": "Condenser Design Air Flow Rate",
                "field_type": "n"
            },
            "condenser_air_flow_sizing_factor": {
                "field_name": "Condenser Air Flow Sizing Factor",
                "field_type": "n"
            },
            "condenser_type": {
                "field_name": "Condenser Type",
                "field_type": "a"
            },
            "evaporative_condenser_effectiveness": {
                "field_name": "Evaporative Condenser Effectiveness",
                "field_type": "n"
            },
            "evaporative_condenser_pump_rated_power_consumption": {
                "field_name": "Evaporative Condenser Pump Rated Power Consumption",
                "field_type": "n"
            },
            "basin_heater_capacity": {
                "field_name": "Basin Heater Capacity",
                "field_type": "n"
            },
            "basin_heater_setpoint_temperature": {
                "field_name": "Basin Heater Setpoint Temperature",
                "field_type": "n"
            },
            "basin_heater_availability_schedule_name": {
                "field_name": "Basin Heater Availability Schedule Name",
                "field_type": "a"
            },
            "supply_water_storage_tank_name": {
                "field_name": "Supply Water Storage Tank Name",
                "field_type": "a"
            },
            "condensate_collection_water_storage_tank_name": {
                "field_name": "Condensate Collection Water Storage Tank Name",
                "field_type": "a"
            },
            "storage_tank_plant_connection_inlet_node_name": {
                "field_name": "Storage Tank Plant Connection Inlet Node Name",
                "field_type": "a"
            },
            "storage_tank_plant_connection_outlet_node_name": {
                "field_name": "Storage Tank Plant Connection Outlet Node Name",
                "field_type": "a"
            },
            "storage_tank_plant_connection_design_flow_rate": {
                "field_name": "Storage Tank Plant Connection Design Flow Rate",
                "field_type": "n"
            },
            "storage_tank_plant_connection_heat_transfer_effectiveness": {
                "field_name": "Storage Tank Plant Connection Heat Transfer Effectiveness",
                "field_type": "n"
            },
            "storage_tank_minimum_operating_limit_fluid_temperature": {
                "field_name": "Storage Tank Minimum Operating Limit Fluid Temperature",
                "field_type": "n"
            },
            "storage_tank_maximum_operating_limit_fluid_temperature": {
                "field_name": "Storage Tank Maximum Operating Limit Fluid Temperature",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "operating_mode_control_method",
            "operation_mode_control_schedule_name",
            "storage_type",
            "user_defined_fluid_type",
            "fluid_storage_volume",
            "ice_storage_capacity",
            "storage_capacity_sizing_factor",
            "storage_tank_ambient_temperature_node_name",
            "storage_tank_to_ambient_u_value_times_area_heat_transfer_coefficient",
            "fluid_storage_tank_rating_temperature",
            "rated_evaporator_air_flow_rate",
            "evaporator_air_inlet_node_name",
            "evaporator_air_outlet_node_name",
            "cooling_only_mode_available",
            "cooling_only_mode_rated_total_evaporator_cooling_capacity",
            "cooling_only_mode_rated_sensible_heat_ratio",
            "cooling_only_mode_rated_cop",
            "cooling_only_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name",
            "cooling_only_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name",
            "cooling_only_mode_energy_input_ratio_function_of_temperature_curve_name",
            "cooling_only_mode_energy_input_ratio_function_of_flow_fraction_curve_name",
            "cooling_only_mode_part_load_fraction_correlation_curve_name",
            "cooling_only_mode_sensible_heat_ratio_function_of_temperature_curve_name",
            "cooling_only_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name",
            "cooling_and_charge_mode_available",
            "cooling_and_charge_mode_rated_total_evaporator_cooling_capacity",
            "cooling_and_charge_mode_capacity_sizing_factor",
            "cooling_and_charge_mode_rated_storage_charging_capacity",
            "cooling_and_charge_mode_storage_capacity_sizing_factor",
            "cooling_and_charge_mode_rated_sensible_heat_ratio",
            "cooling_and_charge_mode_cooling_rated_cop",
            "cooling_and_charge_mode_charging_rated_cop",
            "cooling_and_charge_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name",
            "cooling_and_charge_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name",
            "cooling_and_charge_mode_evaporator_energy_input_ratio_function_of_temperature_curve_name",
            "cooling_and_charge_mode_evaporator_energy_input_ratio_function_of_flow_fraction_curve_name",
            "cooling_and_charge_mode_evaporator_part_load_fraction_correlation_curve_name",
            "cooling_and_charge_mode_storage_charge_capacity_function_of_temperature_curve_name",
            "cooling_and_charge_mode_storage_charge_capacity_function_of_total_evaporator_plr_curve_name",
            "cooling_and_charge_mode_storage_energy_input_ratio_function_of_temperature_curve_name",
            "cooling_and_charge_mode_storage_energy_input_ratio_function_of_flow_fraction_curve_name",
            "cooling_and_charge_mode_storage_energy_part_load_fraction_correlation_curve_name",
            "cooling_and_charge_mode_sensible_heat_ratio_function_of_temperature_curve_name",
            "cooling_and_charge_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name",
            "cooling_and_discharge_mode_available",
            "cooling_and_discharge_mode_rated_total_evaporator_cooling_capacity",
            "cooling_and_discharge_mode_evaporator_capacity_sizing_factor",
            "cooling_and_discharge_mode_rated_storage_discharging_capacity",
            "cooling_and_discharge_mode_storage_discharge_capacity_sizing_factor",
            "cooling_and_discharge_mode_rated_sensible_heat_ratio",
            "cooling_and_discharge_mode_cooling_rated_cop",
            "cooling_and_discharge_mode_discharging_rated_cop",
            "cooling_and_discharge_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name",
            "cooling_and_discharge_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name",
            "cooling_and_discharge_mode_evaporator_energy_input_ratio_function_of_temperature_curve_name",
            "cooling_and_discharge_mode_evaporator_energy_input_ratio_function_of_flow_fraction_curve_name",
            "cooling_and_discharge_mode_evaporator_part_load_fraction_correlation_curve_name",
            "cooling_and_discharge_mode_storage_discharge_capacity_function_of_temperature_curve_name",
            "cooling_and_discharge_mode_storage_discharge_capacity_function_of_flow_fraction_curve_name",
            "cooling_and_discharge_mode_storage_discharge_capacity_function_of_total_evaporator_plr_curve_name",
            "cooling_and_discharge_mode_storage_energy_input_ratio_function_of_temperature_curve_name",
            "cooling_and_discharge_mode_storage_energy_input_ratio_function_of_flow_fraction_curve_name",
            "cooling_and_discharge_mode_storage_energy_part_load_fraction_correlation_curve_name",
            "cooling_and_discharge_mode_sensible_heat_ratio_function_of_temperature_curve_name",
            "cooling_and_discharge_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name",
            "charge_only_mode_available",
            "charge_only_mode_rated_storage_charging_capacity",
            "charge_only_mode_capacity_sizing_factor",
            "charge_only_mode_charging_rated_cop",
            "charge_only_mode_storage_charge_capacity_function_of_temperature_curve_name",
            "charge_only_mode_storage_energy_input_ratio_function_of_temperature_curve_name",
            "discharge_only_mode_available",
            "discharge_only_mode_rated_storage_discharging_capacity",
            "discharge_only_mode_capacity_sizing_factor",
            "discharge_only_mode_rated_sensible_heat_ratio",
            "discharge_only_mode_rated_cop",
            "discharge_only_mode_storage_discharge_capacity_function_of_temperature_curve_name",
            "discharge_only_mode_storage_discharge_capacity_function_of_flow_fraction_curve_name",
            "discharge_only_mode_energy_input_ratio_function_of_temperature_curve_name",
            "discharge_only_mode_energy_input_ratio_function_of_flow_fraction_curve_name",
            "discharge_only_mode_part_load_fraction_correlation_curve_name",
            "discharge_only_mode_sensible_heat_ratio_function_of_temperature_curve_name",
            "discharge_only_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name",
            "ancillary_electric_power",
            "cold_weather_operation_minimum_outdoor_air_temperature",
            "cold_weather_operation_ancillary_power",
            "condenser_air_inlet_node_name",
            "condenser_air_outlet_node_name",
            "condenser_design_air_flow_rate",
            "condenser_air_flow_sizing_factor",
            "condenser_type",
            "evaporative_condenser_effectiveness",
            "evaporative_condenser_pump_rated_power_consumption",
            "basin_heater_capacity",
            "basin_heater_setpoint_temperature",
            "basin_heater_availability_schedule_name",
            "supply_water_storage_tank_name",
            "condensate_collection_water_storage_tank_name",
            "storage_tank_plant_connection_inlet_node_name",
            "storage_tank_plant_connection_outlet_node_name",
            "storage_tank_plant_connection_design_flow_rate",
            "storage_tank_plant_connection_heat_transfer_effectiveness",
            "storage_tank_minimum_operating_limit_fluid_temperature",
            "storage_tank_maximum_operating_limit_fluid_temperature"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "operating_mode_control_method",
                "operation_mode_control_schedule_name",
                "storage_type",
                "user_defined_fluid_type",
                "storage_tank_ambient_temperature_node_name",
                "evaporator_air_inlet_node_name",
                "evaporator_air_outlet_node_name",
                "cooling_only_mode_available",
                "cooling_only_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name",
                "cooling_only_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name",
                "cooling_only_mode_energy_input_ratio_function_of_temperature_curve_name",
                "cooling_only_mode_energy_input_ratio_function_of_flow_fraction_curve_name",
                "cooling_only_mode_part_load_fraction_correlation_curve_name",
                "cooling_only_mode_sensible_heat_ratio_function_of_temperature_curve_name",
                "cooling_only_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name",
                "cooling_and_charge_mode_available",
                "cooling_and_charge_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name",
                "cooling_and_charge_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name",
                "cooling_and_charge_mode_evaporator_energy_input_ratio_function_of_temperature_curve_name",
                "cooling_and_charge_mode_evaporator_energy_input_ratio_function_of_flow_fraction_curve_name",
                "cooling_and_charge_mode_evaporator_part_load_fraction_correlation_curve_name",
                "cooling_and_charge_mode_storage_charge_capacity_function_of_temperature_curve_name",
                "cooling_and_charge_mode_storage_charge_capacity_function_of_total_evaporator_plr_curve_name",
                "cooling_and_charge_mode_storage_energy_input_ratio_function_of_temperature_curve_name",
                "cooling_and_charge_mode_storage_energy_input_ratio_function_of_flow_fraction_curve_name",
                "cooling_and_charge_mode_storage_energy_part_load_fraction_correlation_curve_name",
                "cooling_and_charge_mode_sensible_heat_ratio_function_of_temperature_curve_name",
                "cooling_and_charge_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name",
                "cooling_and_discharge_mode_available",
                "cooling_and_discharge_mode_total_evaporator_cooling_capacity_function_of_temperature_curve_name",
                "cooling_and_discharge_mode_total_evaporator_cooling_capacity_function_of_flow_fraction_curve_name",
                "cooling_and_discharge_mode_evaporator_energy_input_ratio_function_of_temperature_curve_name",
                "cooling_and_discharge_mode_evaporator_energy_input_ratio_function_of_flow_fraction_curve_name",
                "cooling_and_discharge_mode_evaporator_part_load_fraction_correlation_curve_name",
                "cooling_and_discharge_mode_storage_discharge_capacity_function_of_temperature_curve_name",
                "cooling_and_discharge_mode_storage_discharge_capacity_function_of_flow_fraction_curve_name",
                "cooling_and_discharge_mode_storage_discharge_capacity_function_of_total_evaporator_plr_curve_name",
                "cooling_and_discharge_mode_storage_energy_input_ratio_function_of_temperature_curve_name",
                "cooling_and_discharge_mode_storage_energy_input_ratio_function_of_flow_fraction_curve_name",
                "cooling_and_discharge_mode_storage_energy_part_load_fraction_correlation_curve_name",
                "cooling_and_discharge_mode_sensible_heat_ratio_function_of_temperature_curve_name",
                "cooling_and_discharge_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name",
                "charge_only_mode_available",
                "charge_only_mode_storage_charge_capacity_function_of_temperature_curve_name",
                "charge_only_mode_storage_energy_input_ratio_function_of_temperature_curve_name",
                "discharge_only_mode_available",
                "discharge_only_mode_storage_discharge_capacity_function_of_temperature_curve_name",
                "discharge_only_mode_storage_discharge_capacity_function_of_flow_fraction_curve_name",
                "discharge_only_mode_energy_input_ratio_function_of_temperature_curve_name",
                "discharge_only_mode_energy_input_ratio_function_of_flow_fraction_curve_name",
                "discharge_only_mode_part_load_fraction_correlation_curve_name",
                "discharge_only_mode_sensible_heat_ratio_function_of_temperature_curve_name",
                "discharge_only_mode_sensible_heat_ratio_function_of_flow_fraction_curve_name",
                "condenser_air_inlet_node_name",
                "condenser_air_outlet_node_name",
                "condenser_type",
                "basin_heater_availability_schedule_name",
                "supply_water_storage_tank_name",
                "condensate_collection_water_storage_tank_name",
                "storage_tank_plant_connection_inlet_node_name",
                "storage_tank_plant_connection_outlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "fluid_storage_volume",
                "ice_storage_capacity",
                "storage_capacity_sizing_factor",
                "storage_tank_to_ambient_u_value_times_area_heat_transfer_coefficient",
                "fluid_storage_tank_rating_temperature",
                "rated_evaporator_air_flow_rate",
                "cooling_only_mode_rated_total_evaporator_cooling_capacity",
                "cooling_only_mode_rated_sensible_heat_ratio",
                "cooling_only_mode_rated_cop",
                "cooling_and_charge_mode_rated_total_evaporator_cooling_capacity",
                "cooling_and_charge_mode_capacity_sizing_factor",
                "cooling_and_charge_mode_rated_storage_charging_capacity",
                "cooling_and_charge_mode_storage_capacity_sizing_factor",
                "cooling_and_charge_mode_rated_sensible_heat_ratio",
                "cooling_and_charge_mode_cooling_rated_cop",
                "cooling_and_charge_mode_charging_rated_cop",
                "cooling_and_discharge_mode_rated_total_evaporator_cooling_capacity",
                "cooling_and_discharge_mode_evaporator_capacity_sizing_factor",
                "cooling_and_discharge_mode_rated_storage_discharging_capacity",
                "cooling_and_discharge_mode_storage_discharge_capacity_sizing_factor",
                "cooling_and_discharge_mode_rated_sensible_heat_ratio",
                "cooling_and_discharge_mode_cooling_rated_cop",
                "cooling_and_discharge_mode_discharging_rated_cop",
                "charge_only_mode_rated_storage_charging_capacity",
                "charge_only_mode_capacity_sizing_factor",
                "charge_only_mode_charging_rated_cop",
                "discharge_only_mode_rated_storage_discharging_capacity",
                "discharge_only_mode_capacity_sizing_factor",
                "discharge_only_mode_rated_sensible_heat_ratio",
                "discharge_only_mode_rated_cop",
                "ancillary_electric_power",
                "cold_weather_operation_minimum_outdoor_air_temperature",
                "cold_weather_operation_ancillary_power",
                "condenser_design_air_flow_rate",
                "condenser_air_flow_sizing_factor",
                "evaporative_condenser_effectiveness",
                "evaporative_condenser_pump_rated_power_consumption",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "storage_tank_plant_connection_design_flow_rate",
                "storage_tank_plant_connection_heat_transfer_effectiveness",
                "storage_tank_minimum_operating_limit_fluid_temperature",
                "storage_tank_maximum_operating_limit_fluid_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "Direct expansion (DX) cooling coil and condensing unit (includes electric compressor and condenser fan), single-speed with packaged integrated thermal storage for cooling.",
    "min_fields": 89.0
}
```
