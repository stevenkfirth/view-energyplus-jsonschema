```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available."
                },
                "zone_name": {
                    "type": "string",
                    "note": "This must be a controlled zone and appear in a ZoneHVAC:EquipmentConnections object.",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "rated_ambient_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 23.9,
                    "exclusiveMinimum": 0.0
                },
                "rated_ambient_relative_humidity": {
                    "type": "number",
                    "units": "percent",
                    "default": 55.0,
                    "exclusiveMinimum": 0.0,
                    "exclusiveMaximum": 100.0
                },
                "rated_total_cooling_capacity_per_unit_length": {
                    "type": "number",
                    "units": "W/m",
                    "default": 1900.0,
                    "exclusiveMinimum": 0.0
                },
                "rated_latent_heat_ratio": {
                    "type": "number",
                    "default": 0.3,
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "rated_runtime_fraction": {
                    "type": "number",
                    "default": 0.85,
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0
                },
                "case_length": {
                    "type": "number",
                    "units": "m",
                    "default": 3.0,
                    "exclusiveMinimum": 0.0
                },
                "case_operating_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 1.1,
                    "exclusiveMaximum": 20.0
                },
                "latent_case_credit_curve_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "CaseTemperatureMethod",
                        "DewpointMethod",
                        "RelativeHumidityMethod"
                    ],
                    "default": "CaseTemperatureMethod"
                },
                "latent_case_credit_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "standard_case_fan_power_per_unit_length": {
                    "type": "number",
                    "units": "W/m",
                    "default": 75.0,
                    "minimum": 0.0
                },
                "operating_case_fan_power_per_unit_length": {
                    "type": "number",
                    "units": "W/m",
                    "default": 75.0,
                    "minimum": 0.0
                },
                "standard_case_lighting_power_per_unit_length": {
                    "type": "number",
                    "units": "W/m",
                    "default": 90.0
                },
                "installed_case_lighting_power_per_unit_length": {
                    "type": "number",
                    "units": "W/m",
                    "note": "default set equal to Standard Case Lighting Power per Unit Length"
                },
                "case_lighting_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "fraction_of_lighting_energy_to_case": {
                    "type": "number",
                    "default": 1.0,
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "case_anti_sweat_heater_power_per_unit_length": {
                    "type": "number",
                    "units": "W/m",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "minimum_anti_sweat_heater_power_per_unit_length": {
                    "type": "number",
                    "units": "W/m",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "This field is only applicable to the Linear, Dewpoint Method, and Heat Balance Method anti-sweat heater control types"
                },
                "anti_sweat_heater_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Constant",
                        "DewpointMethod",
                        "HeatBalanceMethod",
                        "Linear",
                        "None"
                    ],
                    "default": "None"
                },
                "humidity_at_zero_anti_sweat_heater_energy": {
                    "type": "number",
                    "units": "percent",
                    "default": -10.0,
                    "note": "This field is only applicable to Linear AS heater control type Zone relative humidity (%) where anti-sweat heater energy is zero"
                },
                "case_height": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "default": 1.5,
                    "note": "This field only applicable to Heat Balance Method AS heater control type Height must be greater than zero if Heat Balance Method AS heater control is selected"
                },
                "fraction_of_anti_sweat_heater_energy_to_case": {
                    "type": "number",
                    "default": 1.0,
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "case_defrost_power_per_unit_length": {
                    "type": "number",
                    "units": "W/m",
                    "note": "Used to evaluate load on case as well as power or heat consumption",
                    "default": 0.0,
                    "minimum": 0.0
                },
                "case_defrost_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Electric",
                        "ElectricWithTemperatureTermination",
                        "HotFluid",
                        "HotFluidWithTemperatureTermination",
                        "HotGas",
                        "HotGasWithTemperatureTermination",
                        "None",
                        "OffCycle"
                    ],
                    "default": "OffCycle"
                },
                "case_defrost_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "A case defrost schedule name is required unless case defrost type = None"
                },
                "case_defrost_drip_down_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "If left blank, the defrost schedule will be used The start time for each defrost period in this drip-down schedule should coincide with the start time for each defrost period in the case defrost schedule (previous input field). The length of each defrost drip-down period must be greater than or equal to the corresponding defrost period specified in the case defrost schedule. This extra time allows the melted frost to drip from the coil before refrigeration is restarted."
                },
                "defrost_energy_correction_curve_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "CaseTemperatureMethod",
                        "DewpointMethod",
                        "None",
                        "RelativeHumidityMethod"
                    ],
                    "default": "None",
                    "note": "Case Temperature, Relative Humidity, and Dewpoint Method are applicable to case defrost types with temperature termination only."
                },
                "defrost_energy_correction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Defrost Energy Correction Curve Name is applicable to case defrost types with temperature termination only."
                },
                "under_case_hvac_return_air_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "refrigerated_case_restocking_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Schedule values should be in units of Watts per unit case length (W/m) Leave this field blank if no restocking is to be modeled"
                },
                "case_credit_fraction_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Schedule values should be from 0 to 1 Leave this field blank if no case credit fraction is to be applied"
                },
                "design_evaporator_temperature_or_brine_inlet_temperature": {
                    "type": "number",
                    "note": "Required for detailed refrigeration system, not for compressor rack For a DX system, enter the saturated temperature for refrigerant pressure leaving case For a brine-cooled cooled (secondary system) case, enter the brine inlet temperature Default is 5 C less than case operating temperature",
                    "units": "C",
                    "minimum": -70.0,
                    "maximum": 40.0
                },
                "average_refrigerant_charge_inventory": {
                    "type": "number",
                    "units": "kg/m",
                    "default": 0.0
                },
                "under_case_hvac_return_air_node_name": {
                    "type": "string",
                    "note": "Name of the return air node for this case. If left blank, defaults to the first return air node for this zone."
                }
            },
            "required": [
                "zone_name",
                "latent_case_credit_curve_name"
            ]
        }
    },
    "group": "Refrigeration",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "RefrigerationCaseAndWalkInAndListNames",
            "RefrigerationCaseAndWalkInNames"
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "rated_ambient_temperature": {
                "field_name": "Rated Ambient Temperature",
                "field_type": "n"
            },
            "rated_ambient_relative_humidity": {
                "field_name": "Rated Ambient Relative Humidity",
                "field_type": "n"
            },
            "rated_total_cooling_capacity_per_unit_length": {
                "field_name": "Rated Total Cooling Capacity per Unit Length",
                "field_type": "n"
            },
            "rated_latent_heat_ratio": {
                "field_name": "Rated Latent Heat Ratio",
                "field_type": "n"
            },
            "rated_runtime_fraction": {
                "field_name": "Rated Runtime Fraction",
                "field_type": "n"
            },
            "case_length": {
                "field_name": "Case Length",
                "field_type": "n"
            },
            "case_operating_temperature": {
                "field_name": "Case Operating Temperature",
                "field_type": "n"
            },
            "latent_case_credit_curve_type": {
                "field_name": "Latent Case Credit Curve Type",
                "field_type": "a"
            },
            "latent_case_credit_curve_name": {
                "field_name": "Latent Case Credit Curve Name",
                "field_type": "a"
            },
            "standard_case_fan_power_per_unit_length": {
                "field_name": "Standard Case Fan Power per Unit Length",
                "field_type": "n"
            },
            "operating_case_fan_power_per_unit_length": {
                "field_name": "Operating Case Fan Power per Unit Length",
                "field_type": "n"
            },
            "standard_case_lighting_power_per_unit_length": {
                "field_name": "Standard Case Lighting Power per Unit Length",
                "field_type": "n"
            },
            "installed_case_lighting_power_per_unit_length": {
                "field_name": "Installed Case Lighting Power per Unit Length",
                "field_type": "n"
            },
            "case_lighting_schedule_name": {
                "field_name": "Case Lighting Schedule Name",
                "field_type": "a"
            },
            "fraction_of_lighting_energy_to_case": {
                "field_name": "Fraction of Lighting Energy to Case",
                "field_type": "n"
            },
            "case_anti_sweat_heater_power_per_unit_length": {
                "field_name": "Case Anti-Sweat Heater Power per Unit Length",
                "field_type": "n"
            },
            "minimum_anti_sweat_heater_power_per_unit_length": {
                "field_name": "Minimum Anti-Sweat Heater Power per Unit Length",
                "field_type": "n"
            },
            "anti_sweat_heater_control_type": {
                "field_name": "Anti-Sweat Heater Control Type",
                "field_type": "a"
            },
            "humidity_at_zero_anti_sweat_heater_energy": {
                "field_name": "Humidity at Zero Anti-Sweat Heater Energy",
                "field_type": "n"
            },
            "case_height": {
                "field_name": "Case Height",
                "field_type": "n"
            },
            "fraction_of_anti_sweat_heater_energy_to_case": {
                "field_name": "Fraction of Anti-Sweat Heater Energy to Case",
                "field_type": "n"
            },
            "case_defrost_power_per_unit_length": {
                "field_name": "Case Defrost Power per Unit Length",
                "field_type": "n"
            },
            "case_defrost_type": {
                "field_name": "Case Defrost Type",
                "field_type": "a"
            },
            "case_defrost_schedule_name": {
                "field_name": "Case Defrost Schedule Name",
                "field_type": "a"
            },
            "case_defrost_drip_down_schedule_name": {
                "field_name": "Case Defrost Drip-Down Schedule Name",
                "field_type": "a"
            },
            "defrost_energy_correction_curve_type": {
                "field_name": "Defrost Energy Correction Curve Type",
                "field_type": "a"
            },
            "defrost_energy_correction_curve_name": {
                "field_name": "Defrost Energy Correction Curve Name",
                "field_type": "a"
            },
            "under_case_hvac_return_air_fraction": {
                "field_name": "Under Case HVAC Return Air Fraction",
                "field_type": "n"
            },
            "refrigerated_case_restocking_schedule_name": {
                "field_name": "Refrigerated Case Restocking Schedule Name",
                "field_type": "a"
            },
            "case_credit_fraction_schedule_name": {
                "field_name": "Case Credit Fraction Schedule Name",
                "field_type": "a"
            },
            "design_evaporator_temperature_or_brine_inlet_temperature": {
                "field_name": "Design Evaporator Temperature or Brine Inlet Temperature",
                "field_type": "n"
            },
            "average_refrigerant_charge_inventory": {
                "field_name": "Average Refrigerant Charge Inventory",
                "field_type": "n"
            },
            "under_case_hvac_return_air_node_name": {
                "field_name": "Under Case HVAC Return Air Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "zone_name",
            "rated_ambient_temperature",
            "rated_ambient_relative_humidity",
            "rated_total_cooling_capacity_per_unit_length",
            "rated_latent_heat_ratio",
            "rated_runtime_fraction",
            "case_length",
            "case_operating_temperature",
            "latent_case_credit_curve_type",
            "latent_case_credit_curve_name",
            "standard_case_fan_power_per_unit_length",
            "operating_case_fan_power_per_unit_length",
            "standard_case_lighting_power_per_unit_length",
            "installed_case_lighting_power_per_unit_length",
            "case_lighting_schedule_name",
            "fraction_of_lighting_energy_to_case",
            "case_anti_sweat_heater_power_per_unit_length",
            "minimum_anti_sweat_heater_power_per_unit_length",
            "anti_sweat_heater_control_type",
            "humidity_at_zero_anti_sweat_heater_energy",
            "case_height",
            "fraction_of_anti_sweat_heater_energy_to_case",
            "case_defrost_power_per_unit_length",
            "case_defrost_type",
            "case_defrost_schedule_name",
            "case_defrost_drip_down_schedule_name",
            "defrost_energy_correction_curve_type",
            "defrost_energy_correction_curve_name",
            "under_case_hvac_return_air_fraction",
            "refrigerated_case_restocking_schedule_name",
            "case_credit_fraction_schedule_name",
            "design_evaporator_temperature_or_brine_inlet_temperature",
            "average_refrigerant_charge_inventory",
            "under_case_hvac_return_air_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "zone_name",
                "latent_case_credit_curve_type",
                "latent_case_credit_curve_name",
                "case_lighting_schedule_name",
                "anti_sweat_heater_control_type",
                "case_defrost_type",
                "case_defrost_schedule_name",
                "case_defrost_drip_down_schedule_name",
                "defrost_energy_correction_curve_type",
                "defrost_energy_correction_curve_name",
                "refrigerated_case_restocking_schedule_name",
                "case_credit_fraction_schedule_name",
                "under_case_hvac_return_air_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "rated_ambient_temperature",
                "rated_ambient_relative_humidity",
                "rated_total_cooling_capacity_per_unit_length",
                "rated_latent_heat_ratio",
                "rated_runtime_fraction",
                "case_length",
                "case_operating_temperature",
                "standard_case_fan_power_per_unit_length",
                "operating_case_fan_power_per_unit_length",
                "standard_case_lighting_power_per_unit_length",
                "installed_case_lighting_power_per_unit_length",
                "fraction_of_lighting_energy_to_case",
                "case_anti_sweat_heater_power_per_unit_length",
                "minimum_anti_sweat_heater_power_per_unit_length",
                "humidity_at_zero_anti_sweat_heater_energy",
                "case_height",
                "fraction_of_anti_sweat_heater_energy_to_case",
                "case_defrost_power_per_unit_length",
                "under_case_hvac_return_air_fraction",
                "design_evaporator_temperature_or_brine_inlet_temperature",
                "average_refrigerant_charge_inventory"
            ]
        }
    },
    "type": "object",
    "memo": "The Refrigeration Case object works in conjunction with a compressor rack, a refrigeration system, or a secondary loop to simulate the performance of a refrigerated case system. The object calculates the energy use for lights, fans and anti-sweat heaters and accounts for the sensible and latent heat exchange with the surrounding environment (termed \"case credits\") which impacts the temperature and humidity in the zone where the case is located.",
    "min_fields": 28.0
}
```
