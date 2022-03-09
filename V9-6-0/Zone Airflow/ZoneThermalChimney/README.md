```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "note": "Name of zone that is the thermal chimney",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "width_of_the_absorber_wall": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "cross_sectional_area_of_air_channel_outlet": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "discharge_coefficient": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.8
                },
                "zone_1_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_1": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_1": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_1": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_2_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_2": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_2": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_2": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_3_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_3": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_3": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_3": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_4_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_4": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_4": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_4": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_5_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_5": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_5": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_5": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_6_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_6": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_6": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_6": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_7_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_7": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_7": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_7": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_8_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_8": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_8": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_8": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_9_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_9": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_9": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_9": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_10_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_10": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_10": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_10": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_11_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_11": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_11": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_11": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_12_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_12": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_12": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_12": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_13_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_13": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_13": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_13": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_14_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_14": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_14": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_14": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_15_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_15": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_15": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_15": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_16_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_16": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_16": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_16": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_17_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_17": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_17": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_17": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_18_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_18": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_18": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_18": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_19_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_19": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_19": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_19": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                },
                "zone_20_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "distance_from_top_of_thermal_chimney_to_inlet_20": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "relative_ratios_of_air_flow_rates_passing_through_zone_20": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "cross_sectional_areas_of_air_channel_inlet_20": {
                    "type": "number",
                    "units": "m2",
                    "minimum": 0.0
                }
            },
            "required": [
                "zone_name",
                "width_of_the_absorber_wall",
                "cross_sectional_area_of_air_channel_outlet",
                "zone_1_name",
                "distance_from_top_of_thermal_chimney_to_inlet_1",
                "cross_sectional_areas_of_air_channel_inlet_1"
            ]
        }
    },
    "group": "Zone Airflow",
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
                "field_type": "a"
            },
            "width_of_the_absorber_wall": {
                "field_name": "Width of the Absorber Wall",
                "field_type": "n"
            },
            "cross_sectional_area_of_air_channel_outlet": {
                "field_name": "Cross Sectional Area of Air Channel Outlet",
                "field_type": "n"
            },
            "discharge_coefficient": {
                "field_name": "Discharge Coefficient",
                "field_type": "n"
            },
            "zone_1_name": {
                "field_name": "Zone 1 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_1": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 1",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_1": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 1",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_1": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 1",
                "field_type": "n"
            },
            "zone_2_name": {
                "field_name": "Zone 2 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_2": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 2",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_2": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 2",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_2": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 2",
                "field_type": "n"
            },
            "zone_3_name": {
                "field_name": "Zone 3 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_3": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 3",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_3": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 3",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_3": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 3",
                "field_type": "n"
            },
            "zone_4_name": {
                "field_name": "Zone 4 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_4": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 4",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_4": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 4",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_4": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 4",
                "field_type": "n"
            },
            "zone_5_name": {
                "field_name": "Zone 5 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_5": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 5",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_5": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 5",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_5": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 5",
                "field_type": "n"
            },
            "zone_6_name": {
                "field_name": "Zone 6 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_6": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 6",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_6": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 6",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_6": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 6",
                "field_type": "n"
            },
            "zone_7_name": {
                "field_name": "Zone 7 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_7": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 7",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_7": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 7",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_7": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 7",
                "field_type": "n"
            },
            "zone_8_name": {
                "field_name": "Zone 8 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_8": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 8",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_8": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 8",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_8": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 8",
                "field_type": "n"
            },
            "zone_9_name": {
                "field_name": "Zone 9 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_9": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 9",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_9": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 9",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_9": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 9",
                "field_type": "n"
            },
            "zone_10_name": {
                "field_name": "Zone 10 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_10": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 10",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_10": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 10",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_10": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 10",
                "field_type": "n"
            },
            "zone_11_name": {
                "field_name": "Zone 11 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_11": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 11",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_11": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 11",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_11": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 11",
                "field_type": "n"
            },
            "zone_12_name": {
                "field_name": "Zone 12 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_12": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 12",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_12": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 12",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_12": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 12",
                "field_type": "n"
            },
            "zone_13_name": {
                "field_name": "Zone 13 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_13": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 13",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_13": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 13",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_13": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 13",
                "field_type": "n"
            },
            "zone_14_name": {
                "field_name": "Zone 14 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_14": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 14",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_14": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 14",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_14": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 14",
                "field_type": "n"
            },
            "zone_15_name": {
                "field_name": "Zone 15 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_15": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 15",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_15": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 15",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_15": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 15",
                "field_type": "n"
            },
            "zone_16_name": {
                "field_name": "Zone 16 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_16": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 16",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_16": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 16",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_16": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 16",
                "field_type": "n"
            },
            "zone_17_name": {
                "field_name": "Zone 17 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_17": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 17",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_17": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 17",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_17": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 17",
                "field_type": "n"
            },
            "zone_18_name": {
                "field_name": "Zone 18 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_18": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 18",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_18": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 18",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_18": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 18",
                "field_type": "n"
            },
            "zone_19_name": {
                "field_name": "Zone 19 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_19": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 19",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_19": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 19",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_19": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 19",
                "field_type": "n"
            },
            "zone_20_name": {
                "field_name": "Zone 20 Name",
                "field_type": "a"
            },
            "distance_from_top_of_thermal_chimney_to_inlet_20": {
                "field_name": "Distance from Top of Thermal Chimney to Inlet 20",
                "field_type": "n"
            },
            "relative_ratios_of_air_flow_rates_passing_through_zone_20": {
                "field_name": "Relative Ratios of Air Flow Rates Passing through Zone 20",
                "field_type": "n"
            },
            "cross_sectional_areas_of_air_channel_inlet_20": {
                "field_name": "Cross Sectional Areas of Air Channel Inlet 20",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "zone_name",
            "availability_schedule_name",
            "width_of_the_absorber_wall",
            "cross_sectional_area_of_air_channel_outlet",
            "discharge_coefficient",
            "zone_1_name",
            "distance_from_top_of_thermal_chimney_to_inlet_1",
            "relative_ratios_of_air_flow_rates_passing_through_zone_1",
            "cross_sectional_areas_of_air_channel_inlet_1",
            "zone_2_name",
            "distance_from_top_of_thermal_chimney_to_inlet_2",
            "relative_ratios_of_air_flow_rates_passing_through_zone_2",
            "cross_sectional_areas_of_air_channel_inlet_2",
            "zone_3_name",
            "distance_from_top_of_thermal_chimney_to_inlet_3",
            "relative_ratios_of_air_flow_rates_passing_through_zone_3",
            "cross_sectional_areas_of_air_channel_inlet_3",
            "zone_4_name",
            "distance_from_top_of_thermal_chimney_to_inlet_4",
            "relative_ratios_of_air_flow_rates_passing_through_zone_4",
            "cross_sectional_areas_of_air_channel_inlet_4",
            "zone_5_name",
            "distance_from_top_of_thermal_chimney_to_inlet_5",
            "relative_ratios_of_air_flow_rates_passing_through_zone_5",
            "cross_sectional_areas_of_air_channel_inlet_5",
            "zone_6_name",
            "distance_from_top_of_thermal_chimney_to_inlet_6",
            "relative_ratios_of_air_flow_rates_passing_through_zone_6",
            "cross_sectional_areas_of_air_channel_inlet_6",
            "zone_7_name",
            "distance_from_top_of_thermal_chimney_to_inlet_7",
            "relative_ratios_of_air_flow_rates_passing_through_zone_7",
            "cross_sectional_areas_of_air_channel_inlet_7",
            "zone_8_name",
            "distance_from_top_of_thermal_chimney_to_inlet_8",
            "relative_ratios_of_air_flow_rates_passing_through_zone_8",
            "cross_sectional_areas_of_air_channel_inlet_8",
            "zone_9_name",
            "distance_from_top_of_thermal_chimney_to_inlet_9",
            "relative_ratios_of_air_flow_rates_passing_through_zone_9",
            "cross_sectional_areas_of_air_channel_inlet_9",
            "zone_10_name",
            "distance_from_top_of_thermal_chimney_to_inlet_10",
            "relative_ratios_of_air_flow_rates_passing_through_zone_10",
            "cross_sectional_areas_of_air_channel_inlet_10",
            "zone_11_name",
            "distance_from_top_of_thermal_chimney_to_inlet_11",
            "relative_ratios_of_air_flow_rates_passing_through_zone_11",
            "cross_sectional_areas_of_air_channel_inlet_11",
            "zone_12_name",
            "distance_from_top_of_thermal_chimney_to_inlet_12",
            "relative_ratios_of_air_flow_rates_passing_through_zone_12",
            "cross_sectional_areas_of_air_channel_inlet_12",
            "zone_13_name",
            "distance_from_top_of_thermal_chimney_to_inlet_13",
            "relative_ratios_of_air_flow_rates_passing_through_zone_13",
            "cross_sectional_areas_of_air_channel_inlet_13",
            "zone_14_name",
            "distance_from_top_of_thermal_chimney_to_inlet_14",
            "relative_ratios_of_air_flow_rates_passing_through_zone_14",
            "cross_sectional_areas_of_air_channel_inlet_14",
            "zone_15_name",
            "distance_from_top_of_thermal_chimney_to_inlet_15",
            "relative_ratios_of_air_flow_rates_passing_through_zone_15",
            "cross_sectional_areas_of_air_channel_inlet_15",
            "zone_16_name",
            "distance_from_top_of_thermal_chimney_to_inlet_16",
            "relative_ratios_of_air_flow_rates_passing_through_zone_16",
            "cross_sectional_areas_of_air_channel_inlet_16",
            "zone_17_name",
            "distance_from_top_of_thermal_chimney_to_inlet_17",
            "relative_ratios_of_air_flow_rates_passing_through_zone_17",
            "cross_sectional_areas_of_air_channel_inlet_17",
            "zone_18_name",
            "distance_from_top_of_thermal_chimney_to_inlet_18",
            "relative_ratios_of_air_flow_rates_passing_through_zone_18",
            "cross_sectional_areas_of_air_channel_inlet_18",
            "zone_19_name",
            "distance_from_top_of_thermal_chimney_to_inlet_19",
            "relative_ratios_of_air_flow_rates_passing_through_zone_19",
            "cross_sectional_areas_of_air_channel_inlet_19",
            "zone_20_name",
            "distance_from_top_of_thermal_chimney_to_inlet_20",
            "relative_ratios_of_air_flow_rates_passing_through_zone_20",
            "cross_sectional_areas_of_air_channel_inlet_20"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_name",
                "availability_schedule_name",
                "zone_1_name",
                "zone_2_name",
                "zone_3_name",
                "zone_4_name",
                "zone_5_name",
                "zone_6_name",
                "zone_7_name",
                "zone_8_name",
                "zone_9_name",
                "zone_10_name",
                "zone_11_name",
                "zone_12_name",
                "zone_13_name",
                "zone_14_name",
                "zone_15_name",
                "zone_16_name",
                "zone_17_name",
                "zone_18_name",
                "zone_19_name",
                "zone_20_name"
            ]
        },
        "numerics": {
            "fields": [
                "width_of_the_absorber_wall",
                "cross_sectional_area_of_air_channel_outlet",
                "discharge_coefficient",
                "distance_from_top_of_thermal_chimney_to_inlet_1",
                "relative_ratios_of_air_flow_rates_passing_through_zone_1",
                "cross_sectional_areas_of_air_channel_inlet_1",
                "distance_from_top_of_thermal_chimney_to_inlet_2",
                "relative_ratios_of_air_flow_rates_passing_through_zone_2",
                "cross_sectional_areas_of_air_channel_inlet_2",
                "distance_from_top_of_thermal_chimney_to_inlet_3",
                "relative_ratios_of_air_flow_rates_passing_through_zone_3",
                "cross_sectional_areas_of_air_channel_inlet_3",
                "distance_from_top_of_thermal_chimney_to_inlet_4",
                "relative_ratios_of_air_flow_rates_passing_through_zone_4",
                "cross_sectional_areas_of_air_channel_inlet_4",
                "distance_from_top_of_thermal_chimney_to_inlet_5",
                "relative_ratios_of_air_flow_rates_passing_through_zone_5",
                "cross_sectional_areas_of_air_channel_inlet_5",
                "distance_from_top_of_thermal_chimney_to_inlet_6",
                "relative_ratios_of_air_flow_rates_passing_through_zone_6",
                "cross_sectional_areas_of_air_channel_inlet_6",
                "distance_from_top_of_thermal_chimney_to_inlet_7",
                "relative_ratios_of_air_flow_rates_passing_through_zone_7",
                "cross_sectional_areas_of_air_channel_inlet_7",
                "distance_from_top_of_thermal_chimney_to_inlet_8",
                "relative_ratios_of_air_flow_rates_passing_through_zone_8",
                "cross_sectional_areas_of_air_channel_inlet_8",
                "distance_from_top_of_thermal_chimney_to_inlet_9",
                "relative_ratios_of_air_flow_rates_passing_through_zone_9",
                "cross_sectional_areas_of_air_channel_inlet_9",
                "distance_from_top_of_thermal_chimney_to_inlet_10",
                "relative_ratios_of_air_flow_rates_passing_through_zone_10",
                "cross_sectional_areas_of_air_channel_inlet_10",
                "distance_from_top_of_thermal_chimney_to_inlet_11",
                "relative_ratios_of_air_flow_rates_passing_through_zone_11",
                "cross_sectional_areas_of_air_channel_inlet_11",
                "distance_from_top_of_thermal_chimney_to_inlet_12",
                "relative_ratios_of_air_flow_rates_passing_through_zone_12",
                "cross_sectional_areas_of_air_channel_inlet_12",
                "distance_from_top_of_thermal_chimney_to_inlet_13",
                "relative_ratios_of_air_flow_rates_passing_through_zone_13",
                "cross_sectional_areas_of_air_channel_inlet_13",
                "distance_from_top_of_thermal_chimney_to_inlet_14",
                "relative_ratios_of_air_flow_rates_passing_through_zone_14",
                "cross_sectional_areas_of_air_channel_inlet_14",
                "distance_from_top_of_thermal_chimney_to_inlet_15",
                "relative_ratios_of_air_flow_rates_passing_through_zone_15",
                "cross_sectional_areas_of_air_channel_inlet_15",
                "distance_from_top_of_thermal_chimney_to_inlet_16",
                "relative_ratios_of_air_flow_rates_passing_through_zone_16",
                "cross_sectional_areas_of_air_channel_inlet_16",
                "distance_from_top_of_thermal_chimney_to_inlet_17",
                "relative_ratios_of_air_flow_rates_passing_through_zone_17",
                "cross_sectional_areas_of_air_channel_inlet_17",
                "distance_from_top_of_thermal_chimney_to_inlet_18",
                "relative_ratios_of_air_flow_rates_passing_through_zone_18",
                "cross_sectional_areas_of_air_channel_inlet_18",
                "distance_from_top_of_thermal_chimney_to_inlet_19",
                "relative_ratios_of_air_flow_rates_passing_through_zone_19",
                "cross_sectional_areas_of_air_channel_inlet_19",
                "distance_from_top_of_thermal_chimney_to_inlet_20",
                "relative_ratios_of_air_flow_rates_passing_through_zone_20",
                "cross_sectional_areas_of_air_channel_inlet_20"
            ]
        }
    },
    "type": "object",
    "memo": "A thermal chimney is a vertical shaft utilizing solar radiation to enhance natural ventilation. It consists of an absorber wall, air gap and glass cover with high solar transmissivity.",
    "min_fields": 10.0
}
```
