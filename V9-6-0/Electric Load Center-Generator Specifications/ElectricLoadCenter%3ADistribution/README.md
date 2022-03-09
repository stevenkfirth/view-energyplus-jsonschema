```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "generator_list_name": {
                    "type": "string",
                    "note": "Name of an ElectricLoadCenter:Generators object",
                    "data_type": "object_list",
                    "object_list": [
                        "GeneratorLists"
                    ]
                },
                "generator_operation_scheme_type": {
                    "type": "string",
                    "note": "Determines how generators are to be controlled Required if Generator List is entered.",
                    "enum": [
                        "Baseload",
                        "DemandLimit",
                        "FollowThermal",
                        "FollowThermalLimitElectrical",
                        "TrackElectrical",
                        "TrackMeter",
                        "TrackSchedule"
                    ]
                },
                "generator_demand_limit_scheme_purchased_electric_demand_limit": {
                    "type": "number",
                    "units": "W"
                },
                "generator_track_schedule_name_scheme_schedule_name": {
                    "type": "string",
                    "note": "required when Generator Operation Scheme Type=TrackSchedule schedule values in Watts",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "generator_track_meter_scheme_meter_name": {
                    "type": "string",
                    "note": "required when Generator Operation Scheme Type=TrackMeter",
                    "data_type": "external_list",
                    "external_list": [
                        "autoRDDmeter"
                    ]
                },
                "electrical_buss_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AlternatingCurrent",
                        "AlternatingCurrentWithStorage",
                        "DirectCurrentWithInverter",
                        "DirectCurrentWithInverterACStorage",
                        "DirectCurrentWithInverterDCStorage"
                    ],
                    "default": "AlternatingCurrent"
                },
                "inverter_name": {
                    "type": "string",
                    "note": "required when Electrical Buss Type=DirectCurrentWithInverter, DirectCurrentWithInverterDCStorage, or DirectCurrentWithInverterACStorage",
                    "data_type": "object_list",
                    "object_list": [
                        "InverterList"
                    ]
                },
                "electrical_storage_object_name": {
                    "type": "string",
                    "note": "required when Electrical Buss Type=AlternatingCurrentWithStorage, DirectCurrentWithInverterDCStorage, or DirectCurrentWithInverterACStorage",
                    "data_type": "object_list",
                    "object_list": [
                        "ElecStorageList"
                    ]
                },
                "transformer_object_name": {
                    "type": "string",
                    "note": "required when power needs to be output from on-site generation or storage to the grid via transformer",
                    "data_type": "object_list",
                    "object_list": [
                        "TransformerNames"
                    ]
                },
                "storage_operation_scheme": {
                    "type": "string",
                    "note": "Select method to govern how storage charge and discharge is controlled TrackFacilityElectricDemandStoreExcessOnSite indicates that storage control will follow the facility power demand while accounting for any on-site generation. Only excess on site generation  gets stored (legacy behavior). TrackMeterDemandStoreExcessOnSite indicates that storage discharge control will follow an electric meter named in the field called Storage Control Track Meter Name. This scheme is similiar to TrackFacilityElectricDemandStoreExcessOnSite except that instead of the main facility electric meter, the control is based off of a user-selected meter. TrackChargeDischargeSchedules indicates that control will follow the charging and discharging power and schedules defined in the fields called Maximum Storage Charge Grid Supply Power, Storage Charge Grid Supply Power Fraction Schedule Name, Design Storage Discharge Grid Export Power, and Storage Discharge Grid Export Fraction Schedule Name. FacilityDemandLeveling indicates that storage control will attempt to control the facility's power demand drawn from the utility service to a prescribed level. The target utility demand is entered in the fields called Storage Control Utility Demand Limit and Storage Control Utility Demand Limit Fraction Schedule Name This scheme first accounts for any on-site generation and during times of high use will discharge storage to reduce facility grid demand to meet the target level and during times of low use will charge storage from the grid to increase facility grid demand to meet the target level.",
                    "enum": [
                        "",
                        "FacilityDemandLeveling",
                        "TrackChargeDischargeSchedules",
                        "TrackFacilityElectricDemandStoreExcessOnSite",
                        "TrackMeterDemandStoreExcessOnSite"
                    ],
                    "default": "TrackFacilityElectricDemandStoreExcessOnSite"
                },
                "storage_control_track_meter_name": {
                    "type": "string",
                    "note": "required when Storage Operation Scheme is set to TrackMeterDemandStoreExcessOnSite.",
                    "data_type": "external_list",
                    "external_list": [
                        "autoRDDmeter"
                    ]
                },
                "storage_converter_object_name": {
                    "type": "string",
                    "note": "Name of an ElectricLoadCenter:Storage:Converter used to convert AC to DC when charging DC storage from grid supply. A converter is expected when using Storage Operation Schemes FacilityDemandLeveling or TrackChargeDischargeSchedules A single bidirectional device will reference both an inverter object (DC to AC) and a converter object (AC to DC).",
                    "data_type": "object_list",
                    "object_list": [
                        "ConverterList"
                    ]
                },
                "maximum_storage_state_of_charge_fraction": {
                    "type": "number",
                    "note": "Fraction of storage capacity used as upper limit for controlling charging, for all storage operation schemes.",
                    "default": 1.0
                },
                "minimum_storage_state_of_charge_fraction": {
                    "type": "number",
                    "note": "Fraction of storage capacity used as lower limit for controlling discharging, for all storage operation schemes.",
                    "default": 0.0
                },
                "design_storage_control_charge_power": {
                    "type": "number",
                    "note": "Maximum rate that electric power can be charged into storage. Storage charging adjusted downward for conversion losses. Rate is modified by fractional values in the schedule named in the next field. Required field when using Storage Operation Schemes FacilityDemandLeveling or TrackChargeDischargeSchedules.",
                    "units": "W"
                },
                "storage_charge_power_fraction_schedule_name": {
                    "type": "string",
                    "note": "Controls timing and magnitude of charging storage. Required field if Storage Operation Scheme is set to TrackChargeDischargeSchedules. Schedule values should be fractions from 0.0 to 1.0, inclusive.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "design_storage_control_discharge_power": {
                    "type": "number",
                    "note": "Maximum rate that electric power can be discharged from storage. Rate is modified by fractional values in the schedule named in the next field. Required field when using Storage Operation Schemes FacilityDemandLeveling or TrackChargeDischargeSchedules.",
                    "units": "W"
                },
                "storage_discharge_power_fraction_schedule_name": {
                    "type": "string",
                    "note": "Controls timing and magnitude of discharging storage Required field if Storage Operation Scheme is set to TrackChargeDischargeSchedules. Schedule values should be fractions from 0.0 to 1.0, inclusive.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "storage_control_utility_demand_target": {
                    "type": "number",
                    "note": "Target utility service demand power for discharge control. Storage draws are adjusted upwards for conversion losses. Required field for FacilityDemandLeveling storage operation scheme",
                    "units": "W"
                },
                "storage_control_utility_demand_target_fraction_schedule_name": {
                    "type": "string",
                    "note": "Modifies the target utility service demand power over time. Schedule values should be fractions from -1.0 to 1.0, inclusive. if omitted a schedule value of 1.0 is used. Negative values indicate export to grid Schedule is used if Storage Operation Scheme is set to FacilityDemandLeveling.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            }
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "generator_list_name": {
                "field_name": "Generator List Name",
                "field_type": "a"
            },
            "generator_operation_scheme_type": {
                "field_name": "Generator Operation Scheme Type",
                "field_type": "a"
            },
            "generator_demand_limit_scheme_purchased_electric_demand_limit": {
                "field_name": "Generator Demand Limit Scheme Purchased Electric Demand Limit",
                "field_type": "n"
            },
            "generator_track_schedule_name_scheme_schedule_name": {
                "field_name": "Generator Track Schedule Name Scheme Schedule Name",
                "field_type": "a"
            },
            "generator_track_meter_scheme_meter_name": {
                "field_name": "Generator Track Meter Scheme Meter Name",
                "field_type": "a"
            },
            "electrical_buss_type": {
                "field_name": "Electrical Buss Type",
                "field_type": "a"
            },
            "inverter_name": {
                "field_name": "Inverter Name",
                "field_type": "a"
            },
            "electrical_storage_object_name": {
                "field_name": "Electrical Storage Object Name",
                "field_type": "a"
            },
            "transformer_object_name": {
                "field_name": "Transformer Object Name",
                "field_type": "a"
            },
            "storage_operation_scheme": {
                "field_name": "Storage Operation Scheme",
                "field_type": "a"
            },
            "storage_control_track_meter_name": {
                "field_name": "Storage Control Track Meter Name",
                "field_type": "a"
            },
            "storage_converter_object_name": {
                "field_name": "Storage Converter Object Name",
                "field_type": "a"
            },
            "maximum_storage_state_of_charge_fraction": {
                "field_name": "Maximum Storage State of Charge Fraction",
                "field_type": "n"
            },
            "minimum_storage_state_of_charge_fraction": {
                "field_name": "Minimum Storage State of Charge Fraction",
                "field_type": "n"
            },
            "design_storage_control_charge_power": {
                "field_name": "Design Storage Control Charge Power",
                "field_type": "n"
            },
            "storage_charge_power_fraction_schedule_name": {
                "field_name": "Storage Charge Power Fraction Schedule Name",
                "field_type": "a"
            },
            "design_storage_control_discharge_power": {
                "field_name": "Design Storage Control Discharge Power",
                "field_type": "n"
            },
            "storage_discharge_power_fraction_schedule_name": {
                "field_name": "Storage Discharge Power Fraction Schedule Name",
                "field_type": "a"
            },
            "storage_control_utility_demand_target": {
                "field_name": "Storage Control Utility Demand Target",
                "field_type": "n"
            },
            "storage_control_utility_demand_target_fraction_schedule_name": {
                "field_name": "Storage Control Utility Demand Target Fraction Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "generator_list_name",
            "generator_operation_scheme_type",
            "generator_demand_limit_scheme_purchased_electric_demand_limit",
            "generator_track_schedule_name_scheme_schedule_name",
            "generator_track_meter_scheme_meter_name",
            "electrical_buss_type",
            "inverter_name",
            "electrical_storage_object_name",
            "transformer_object_name",
            "storage_operation_scheme",
            "storage_control_track_meter_name",
            "storage_converter_object_name",
            "maximum_storage_state_of_charge_fraction",
            "minimum_storage_state_of_charge_fraction",
            "design_storage_control_charge_power",
            "storage_charge_power_fraction_schedule_name",
            "design_storage_control_discharge_power",
            "storage_discharge_power_fraction_schedule_name",
            "storage_control_utility_demand_target",
            "storage_control_utility_demand_target_fraction_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "generator_list_name",
                "generator_operation_scheme_type",
                "generator_track_schedule_name_scheme_schedule_name",
                "generator_track_meter_scheme_meter_name",
                "electrical_buss_type",
                "inverter_name",
                "electrical_storage_object_name",
                "transformer_object_name",
                "storage_operation_scheme",
                "storage_control_track_meter_name",
                "storage_converter_object_name",
                "storage_charge_power_fraction_schedule_name",
                "storage_discharge_power_fraction_schedule_name",
                "storage_control_utility_demand_target_fraction_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "generator_demand_limit_scheme_purchased_electric_demand_limit",
                "maximum_storage_state_of_charge_fraction",
                "minimum_storage_state_of_charge_fraction",
                "design_storage_control_charge_power",
                "design_storage_control_discharge_power",
                "storage_control_utility_demand_target"
            ]
        }
    },
    "type": "object",
    "memo": "Describes a subpanel a list of meters that can be reported are available after a run on the meter dictionary file (.mdd) if the Output:VariableDictionary has been requested."
}
```
