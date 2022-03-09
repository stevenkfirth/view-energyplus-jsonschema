```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "reference_electrical_power_output": {
                    "type": "number",
                    "units": "W",
                    "exclusiveMinimum": 0.0
                },
                "minimum_full_load_electrical_power_output": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "maximum_full_load_electrical_power_output": {
                    "type": "number",
                    "units": "W",
                    "exclusiveMinimum": 0.0,
                    "note": "If left blank, Maximum Full Load Electrical Power Output will be set equal to the Reference Electrical Power Output."
                },
                "reference_electrical_efficiency_using_lower_heating_value": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "note": "Electric power output divided by fuel energy input (LHV basis) at reference conditions."
                },
                "reference_combustion_air_inlet_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 15.0
                },
                "reference_combustion_air_inlet_humidity_ratio": {
                    "type": "number",
                    "units": "kgWater/kgDryAir",
                    "exclusiveMinimum": 0.0,
                    "default": 0.00638
                },
                "reference_elevation": {
                    "type": "number",
                    "units": "m",
                    "minimum": -300.0,
                    "default": 0.0
                },
                "electrical_power_function_of_temperature_and_elevation_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*T + c*T**2 + d*Elev + e*Elev**2 + f*T*Elev T = combustion air inlet temperature (C) Elev = elevation (m)"
                },
                "electrical_efficiency_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*T + c*T**2 Cubic curve = a + b*T + c*T**2 + d*T**3 T = combustion air inlet temperature (C)"
                },
                "electrical_efficiency_function_of_part_load_ratio_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*PLR + c*PLR**2 Cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = ratio of Generator Load to steady state Electrical Power Output at current operating conditions"
                },
                "fuel_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Coal",
                        "Diesel",
                        "FuelOilNo1",
                        "FuelOilNo2",
                        "Gasoline",
                        "NaturalGas",
                        "OtherFuel1",
                        "OtherFuel2",
                        "Propane"
                    ],
                    "default": "NaturalGas"
                },
                "fuel_higher_heating_value": {
                    "type": "number",
                    "units": "kJ/kg",
                    "default": 50000.0,
                    "exclusiveMinimum": 0.0
                },
                "fuel_lower_heating_value": {
                    "type": "number",
                    "units": "kJ/kg",
                    "default": 45450.0,
                    "exclusiveMinimum": 0.0
                },
                "standby_power": {
                    "type": "number",
                    "units": "W",
                    "default": 0.0,
                    "minimum": 0.0,
                    "note": "Electric power consumed when the generator is available but not being called by the Electric Load Center."
                },
                "ancillary_power": {
                    "type": "number",
                    "units": "W",
                    "default": 0.0,
                    "minimum": 0.0,
                    "note": "Electric power consumed by ancillary equipment (e.g., external fuel pressurization pump). Set to zero if Reference Electrical Power Output is the 'net' value (ancillary power already deducted). Input value is positive, but indicates negative electric generation."
                },
                "ancillary_power_function_of_fuel_input_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*mdot + c*mdot**2 mdot = fuel mass flow rate (kg/s) If left blank, model assumes ancillary power defined in previous field is constant whenever the generator is operating."
                },
                "heat_recovery_water_inlet_node_name": {
                    "type": "string"
                },
                "heat_recovery_water_outlet_node_name": {
                    "type": "string"
                },
                "reference_thermal_efficiency_using_lower_heat_value": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0,
                    "note": "Reference thermal efficiency (heat recovery to water) based on the Lower Heating Value (LHV) of the fuel."
                },
                "reference_inlet_water_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "heat_recovery_water_flow_operating_mode": {
                    "type": "string",
                    "enum": [
                        "",
                        "InternalControl",
                        "PlantControl"
                    ],
                    "default": "PlantControl",
                    "note": "PlantControl means the heat recovery water flow rate is determined by the plant, but the user needs to supply a heat recovery water flow rate. InternalControl means the heat recovery water flow rate is controlled by this generator. If 'InternalControl' is selected, then the user needs to supply a reference heat recovery water flow rate and optionally the name of a heat recovery flow rate modifier curve."
                },
                "reference_heat_recovery_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "exclusiveMinimum": 0.0
                },
                "heat_recovery_water_flow_rate_function_of_temperature_and_power_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*T + c*T**2 + d*Pnet + e*Pnet + f*T*Pnet T = heat recovery inlet water temperature Pnet = net power output = electric power output - ancillary power If left blank, model assumes the heat recovery water flow rate is constant whenever the generator is operating, at the Reference HR Water Flow Rate defined in the previous field."
                },
                "thermal_efficiency_function_of_temperature_and_elevation_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "Bicubic curve = a + b*T + c*T**2 + d*Elev + e*Elev**2 + f*T*Elev + g*T**3 + h*Elev**3 + i*T**2*Elev + j*T*Elev**2 Biquadratic curve = a + b*T + c*T**2 + d*Elev + e*Elev**2 + f*T*Elev T = combustion air inlet temperature (C) Elev = elevation (m) If field is left blank, model assumes this modifier equals 1 for entire simulation."
                },
                "heat_recovery_rate_function_of_part_load_ratio_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*PLR + c*PLR**2 Cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = ratio of Generator Load to steady state Electrical Power Output at current operating conditions If field is left blank, model assumes this modifier equals 1 for entire simulation."
                },
                "heat_recovery_rate_function_of_inlet_water_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*T + c*T**2 T = inlet water temperature (C) If field is left blank, model assumes this modifier equals 1 for entire simulation."
                },
                "heat_recovery_rate_function_of_water_flow_rate_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*Flow + c*Flow**2 Flow = flow rate of water through the heat exchanger (m3/s) If field is left blank, model assumes this modifier equals 1 for entire simulation."
                },
                "minimum_heat_recovery_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "maximum_heat_recovery_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "maximum_heat_recovery_water_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "combustion_air_inlet_node_name": {
                    "type": "string",
                    "note": "Must be an outdoor air node."
                },
                "combustion_air_outlet_node_name": {
                    "type": "string"
                },
                "reference_exhaust_air_mass_flow_rate": {
                    "type": "number",
                    "units": "kg/s",
                    "exclusiveMinimum": 0.0
                },
                "exhaust_air_flow_rate_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*T + c*T**2 Cubic curve = a + b*T + c*T**2 + d*T**3 T = combustion air inlet temperature (C) If field is left blank, model assumes this modifier equals 1 for entire simulation."
                },
                "exhaust_air_flow_rate_function_of_part_load_ratio_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*PLR + c*PLR**2 Cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = ratio of Generator Load to steady state Electrical Power Output at current operating conditions. If field is left blank, model assumes this modifier equals 1 for entire simulation."
                },
                "nominal_exhaust_air_outlet_temperature": {
                    "type": "number",
                    "note": "Exhaust air outlet temperature at reference conditions."
                },
                "exhaust_air_temperature_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*T + c*T**2 Cubic curve = a + b*T + c*T**2 + d*T**3 T = combustion air inlet temperature (C) If field is left blank, model assumes this modifier equals 1 for entire simulation."
                },
                "exhaust_air_temperature_function_of_part_load_ratio_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Quadratic curve = a + b*PLR + c*PLR**2 Cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = ratio of Generator Load to steady state Electrical Power Output at current operating conditions. If field is left blank, model assumes this modifier equals 1 for entire simulation."
                }
            },
            "required": [
                "reference_electrical_power_output",
                "reference_electrical_efficiency_using_lower_heating_value",
                "electrical_power_function_of_temperature_and_elevation_curve_name",
                "electrical_efficiency_function_of_temperature_curve_name",
                "electrical_efficiency_function_of_part_load_ratio_curve_name"
            ]
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "GeneratorNames",
            "MicroTurbineGeneratorNames",
            "validBranchEquipmentNames",
            "validCondenserEquipmentNames",
            "validPlantEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validCondenserEquipmentTypes",
            "validPlantEquipmentTypes"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "reference_electrical_power_output": {
                "field_name": "Reference Electrical Power Output",
                "field_type": "n"
            },
            "minimum_full_load_electrical_power_output": {
                "field_name": "Minimum Full Load Electrical Power Output",
                "field_type": "n"
            },
            "maximum_full_load_electrical_power_output": {
                "field_name": "Maximum Full Load Electrical Power Output",
                "field_type": "n"
            },
            "reference_electrical_efficiency_using_lower_heating_value": {
                "field_name": "Reference Electrical Efficiency Using Lower Heating Value",
                "field_type": "n"
            },
            "reference_combustion_air_inlet_temperature": {
                "field_name": "Reference Combustion Air Inlet Temperature",
                "field_type": "n"
            },
            "reference_combustion_air_inlet_humidity_ratio": {
                "field_name": "Reference Combustion Air Inlet Humidity Ratio",
                "field_type": "n"
            },
            "reference_elevation": {
                "field_name": "Reference Elevation",
                "field_type": "n"
            },
            "electrical_power_function_of_temperature_and_elevation_curve_name": {
                "field_name": "Electrical Power Function of Temperature and Elevation Curve Name",
                "field_type": "a"
            },
            "electrical_efficiency_function_of_temperature_curve_name": {
                "field_name": "Electrical Efficiency Function of Temperature Curve Name",
                "field_type": "a"
            },
            "electrical_efficiency_function_of_part_load_ratio_curve_name": {
                "field_name": "Electrical Efficiency Function of Part Load Ratio Curve Name",
                "field_type": "a"
            },
            "fuel_type": {
                "field_name": "Fuel Type",
                "field_type": "a"
            },
            "fuel_higher_heating_value": {
                "field_name": "Fuel Higher Heating Value",
                "field_type": "n"
            },
            "fuel_lower_heating_value": {
                "field_name": "Fuel Lower Heating Value",
                "field_type": "n"
            },
            "standby_power": {
                "field_name": "Standby Power",
                "field_type": "n"
            },
            "ancillary_power": {
                "field_name": "Ancillary Power",
                "field_type": "n"
            },
            "ancillary_power_function_of_fuel_input_curve_name": {
                "field_name": "Ancillary Power Function of Fuel Input Curve Name",
                "field_type": "a"
            },
            "heat_recovery_water_inlet_node_name": {
                "field_name": "Heat Recovery Water Inlet Node Name",
                "field_type": "a"
            },
            "heat_recovery_water_outlet_node_name": {
                "field_name": "Heat Recovery Water Outlet Node Name",
                "field_type": "a"
            },
            "reference_thermal_efficiency_using_lower_heat_value": {
                "field_name": "Reference Thermal Efficiency Using Lower Heat Value",
                "field_type": "n"
            },
            "reference_inlet_water_temperature": {
                "field_name": "Reference Inlet Water Temperature",
                "field_type": "n"
            },
            "heat_recovery_water_flow_operating_mode": {
                "field_name": "Heat Recovery Water Flow Operating Mode",
                "field_type": "a"
            },
            "reference_heat_recovery_water_flow_rate": {
                "field_name": "Reference Heat Recovery Water Flow Rate",
                "field_type": "n"
            },
            "heat_recovery_water_flow_rate_function_of_temperature_and_power_curve_name": {
                "field_name": "Heat Recovery Water Flow Rate Function of Temperature and Power Curve Name",
                "field_type": "a"
            },
            "thermal_efficiency_function_of_temperature_and_elevation_curve_name": {
                "field_name": "Thermal Efficiency Function of Temperature and Elevation Curve Name",
                "field_type": "a"
            },
            "heat_recovery_rate_function_of_part_load_ratio_curve_name": {
                "field_name": "Heat Recovery Rate Function of Part Load Ratio Curve Name",
                "field_type": "a"
            },
            "heat_recovery_rate_function_of_inlet_water_temperature_curve_name": {
                "field_name": "Heat Recovery Rate Function of Inlet Water Temperature Curve Name",
                "field_type": "a"
            },
            "heat_recovery_rate_function_of_water_flow_rate_curve_name": {
                "field_name": "Heat Recovery Rate Function of Water Flow Rate Curve Name",
                "field_type": "a"
            },
            "minimum_heat_recovery_water_flow_rate": {
                "field_name": "Minimum Heat Recovery Water Flow Rate",
                "field_type": "n"
            },
            "maximum_heat_recovery_water_flow_rate": {
                "field_name": "Maximum Heat Recovery Water Flow Rate",
                "field_type": "n"
            },
            "maximum_heat_recovery_water_temperature": {
                "field_name": "Maximum Heat Recovery Water Temperature",
                "field_type": "n"
            },
            "combustion_air_inlet_node_name": {
                "field_name": "Combustion Air Inlet Node Name",
                "field_type": "a"
            },
            "combustion_air_outlet_node_name": {
                "field_name": "Combustion Air Outlet Node Name",
                "field_type": "a"
            },
            "reference_exhaust_air_mass_flow_rate": {
                "field_name": "Reference Exhaust Air Mass Flow Rate",
                "field_type": "n"
            },
            "exhaust_air_flow_rate_function_of_temperature_curve_name": {
                "field_name": "Exhaust Air Flow Rate Function of Temperature Curve Name",
                "field_type": "a"
            },
            "exhaust_air_flow_rate_function_of_part_load_ratio_curve_name": {
                "field_name": "Exhaust Air Flow Rate Function of Part Load Ratio Curve Name",
                "field_type": "a"
            },
            "nominal_exhaust_air_outlet_temperature": {
                "field_name": "Nominal Exhaust Air Outlet Temperature",
                "field_type": "n"
            },
            "exhaust_air_temperature_function_of_temperature_curve_name": {
                "field_name": "Exhaust Air Temperature Function of Temperature Curve Name",
                "field_type": "a"
            },
            "exhaust_air_temperature_function_of_part_load_ratio_curve_name": {
                "field_name": "Exhaust Air Temperature Function of Part Load Ratio Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "reference_electrical_power_output",
            "minimum_full_load_electrical_power_output",
            "maximum_full_load_electrical_power_output",
            "reference_electrical_efficiency_using_lower_heating_value",
            "reference_combustion_air_inlet_temperature",
            "reference_combustion_air_inlet_humidity_ratio",
            "reference_elevation",
            "electrical_power_function_of_temperature_and_elevation_curve_name",
            "electrical_efficiency_function_of_temperature_curve_name",
            "electrical_efficiency_function_of_part_load_ratio_curve_name",
            "fuel_type",
            "fuel_higher_heating_value",
            "fuel_lower_heating_value",
            "standby_power",
            "ancillary_power",
            "ancillary_power_function_of_fuel_input_curve_name",
            "heat_recovery_water_inlet_node_name",
            "heat_recovery_water_outlet_node_name",
            "reference_thermal_efficiency_using_lower_heat_value",
            "reference_inlet_water_temperature",
            "heat_recovery_water_flow_operating_mode",
            "reference_heat_recovery_water_flow_rate",
            "heat_recovery_water_flow_rate_function_of_temperature_and_power_curve_name",
            "thermal_efficiency_function_of_temperature_and_elevation_curve_name",
            "heat_recovery_rate_function_of_part_load_ratio_curve_name",
            "heat_recovery_rate_function_of_inlet_water_temperature_curve_name",
            "heat_recovery_rate_function_of_water_flow_rate_curve_name",
            "minimum_heat_recovery_water_flow_rate",
            "maximum_heat_recovery_water_flow_rate",
            "maximum_heat_recovery_water_temperature",
            "combustion_air_inlet_node_name",
            "combustion_air_outlet_node_name",
            "reference_exhaust_air_mass_flow_rate",
            "exhaust_air_flow_rate_function_of_temperature_curve_name",
            "exhaust_air_flow_rate_function_of_part_load_ratio_curve_name",
            "nominal_exhaust_air_outlet_temperature",
            "exhaust_air_temperature_function_of_temperature_curve_name",
            "exhaust_air_temperature_function_of_part_load_ratio_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "electrical_power_function_of_temperature_and_elevation_curve_name",
                "electrical_efficiency_function_of_temperature_curve_name",
                "electrical_efficiency_function_of_part_load_ratio_curve_name",
                "fuel_type",
                "ancillary_power_function_of_fuel_input_curve_name",
                "heat_recovery_water_inlet_node_name",
                "heat_recovery_water_outlet_node_name",
                "heat_recovery_water_flow_operating_mode",
                "heat_recovery_water_flow_rate_function_of_temperature_and_power_curve_name",
                "thermal_efficiency_function_of_temperature_and_elevation_curve_name",
                "heat_recovery_rate_function_of_part_load_ratio_curve_name",
                "heat_recovery_rate_function_of_inlet_water_temperature_curve_name",
                "heat_recovery_rate_function_of_water_flow_rate_curve_name",
                "combustion_air_inlet_node_name",
                "combustion_air_outlet_node_name",
                "exhaust_air_flow_rate_function_of_temperature_curve_name",
                "exhaust_air_flow_rate_function_of_part_load_ratio_curve_name",
                "exhaust_air_temperature_function_of_temperature_curve_name",
                "exhaust_air_temperature_function_of_part_load_ratio_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "reference_electrical_power_output",
                "minimum_full_load_electrical_power_output",
                "maximum_full_load_electrical_power_output",
                "reference_electrical_efficiency_using_lower_heating_value",
                "reference_combustion_air_inlet_temperature",
                "reference_combustion_air_inlet_humidity_ratio",
                "reference_elevation",
                "fuel_higher_heating_value",
                "fuel_lower_heating_value",
                "standby_power",
                "ancillary_power",
                "reference_thermal_efficiency_using_lower_heat_value",
                "reference_inlet_water_temperature",
                "reference_heat_recovery_water_flow_rate",
                "minimum_heat_recovery_water_flow_rate",
                "maximum_heat_recovery_water_flow_rate",
                "maximum_heat_recovery_water_temperature",
                "reference_exhaust_air_mass_flow_rate",
                "nominal_exhaust_air_outlet_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "MicroTurbine generators are small combustion turbines (e.g., 25kW to 500kW). The model calculates electrical power output, fuel use, standby and ancillary power. Energy recovery from exhaust air can be used to heat water.",
    "min_fields": 11.0
}
```
