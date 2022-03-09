```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "airflownetwork_control": {
                    "type": "string",
                    "enum": [
                        "",
                        "MultizoneWithDistribution",
                        "MultizoneWithDistributionOnlyDuringFanOperation",
                        "MultizoneWithoutDistribution",
                        "NoMultizoneOrDistribution"
                    ],
                    "default": "NoMultizoneOrDistribution",
                    "note": "NoMultizoneOrDistribution: Only perform Simple calculations (objects ZoneInfiltration:*, ZoneVentilation:*, ZoneMixing, ZoneCrossMixing, ZoneRefrigerationDoorMixing, ZoneAirBalance:OutdoorAir, ZoneEarthtube, ZoneThermalChimney, and ZoneCoolTower:Shower); MultizoneWithoutDistribution: Use AirflowNetwork objects to simulate multizone Airflows driven by wind during simulation time, and objects of ZoneInfiltration:*, ZoneVentilation:*, ZoneMixing, ZoneCrossMixing ZoneRefrigerationDoorMixing, ZoneAirBalance:OutdoorAir, ZoneEarthtube, ZoneThermalChimney, and ZoneCoolTower:Shower are ignored; MultizoneWithDistributionOnlyDuringFanOperation: Perform distribution system calculations during system fan on time and Simple calculations during system Fan off time; MultizoneWithDistribution: Perform distribution system calculations during system fan on time and multizone Airflow driven by wind during system fan off time."
                },
                "wind_pressure_coefficient_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Input",
                        "SurfaceAverageCalculation"
                    ],
                    "default": "SurfaceAverageCalculation",
                    "note": "Input: User must enter AirflowNetwork:MultiZone:WindPressureCoefficientArray, AirflowNetwork:MultiZone:ExternalNode, and AirflowNetwork:MultiZone:WindPressureCoefficientValues objects. SurfaceAverageCalculation: used only for rectangular buildings. If SurfaceAverageCalculation is selected, AirflowNetwork:MultiZone:WindPressureCoefficientArray, AirflowNetwork:MultiZone:ExternalNode, and AirflowNetwork:MultiZone:WindPressureCoefficientValues objects are not used."
                },
                "height_selection_for_local_wind_pressure_calculation": {
                    "type": "string",
                    "enum": [
                        "",
                        "ExternalNode",
                        "OpeningHeight"
                    ],
                    "default": "OpeningHeight",
                    "note": "If ExternalNode is selected, the height given in the AirflowNetwork:MultiZone:ExternalNode object will be used. If OpeningHeight is selected, the surface opening height (centroid) will be used to calculate local wind pressure This field is ignored when the choice of the Wind Pressure Coefficient Type field is SurfaceAverageCalculation."
                },
                "building_type": {
                    "type": "string",
                    "note": "Used only if Wind Pressure Coefficient Type = SurfaceAverageCalculation, otherwise this field may be left blank.",
                    "enum": [
                        "",
                        "HighRise",
                        "LowRise"
                    ],
                    "default": "LowRise"
                },
                "maximum_number_of_iterations": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 500.0,
                    "exclusiveMinimum": 10.0,
                    "maximum": 30000.0,
                    "note": "Determines the maximum number of iterations used to converge on a solution. If this limit is exceeded, the program terminates."
                },
                "initialization_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "LinearInitializationMethod",
                        "ZeroNodePressures"
                    ],
                    "default": "ZeroNodePressures"
                },
                "relative_airflow_convergence_tolerance": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 0.0001,
                    "exclusiveMinimum": 0.0,
                    "note": "This tolerance is defined as the absolute value of the sum of the mass Flow Rates divided by the sum of the absolute value of the mass Flow Rates. The mass Flow Rates described here refer to the mass Flow Rates at all Nodes in the AirflowNetwork model. The solution converges when both this tolerance and the tolerance in the next field (Absolute Airflow Convergence Tolerance) are satisfied."
                },
                "absolute_airflow_convergence_tolerance": {
                    "type": "number",
                    "units": "kg/s",
                    "default": 1e-06,
                    "exclusiveMinimum": 0.0,
                    "note": "This tolerance is defined as the absolute value of the sum of the mass flow rates. The mass flow rates described here refer to the mass flow rates at all nodes in the AirflowNetwork model. The solution converges when both this tolerance and the tolerance in the previous field (Relative Airflow Convergence Tolerance) are satisfied."
                },
                "convergence_acceleration_limit": {
                    "type": "number",
                    "units": "dimensionless",
                    "note": "Used only for AirflowNetwork:SimulationControl",
                    "minimum": -1.0,
                    "maximum": 1.0,
                    "default": -0.5
                },
                "azimuth_angle_of_long_axis_of_building": {
                    "type": "number",
                    "units": "deg",
                    "minimum": 0.0,
                    "maximum": 180.0,
                    "default": 0.0,
                    "note": "Degrees clockwise from true North. Used only if Wind Pressure Coefficient Type = SurfaceAverageCalculation."
                },
                "ratio_of_building_width_along_short_axis_to_width_along_long_axis": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0,
                    "note": "Used only if Wind Pressure Coefficient Type = SurfaceAverageCalculation."
                },
                "height_dependence_of_external_node_temperature": {
                    "type": "string",
                    "note": "If Yes, external node temperature is height dependent. If No, external node temperature is based on zero height.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "solver": {
                    "type": "string",
                    "note": "Select the solver to use for the pressure network solution",
                    "enum": [
                        "",
                        "ConjugateGradient",
                        "SkylineLU"
                    ],
                    "default": "SkylineLU"
                },
                "allow_unsupported_zone_equipment": {
                    "type": "string",
                    "note": "Set this input to Yes to have zone equipment that are currently unsupported in the AirflowNetwork model allowed in the simulation if present. Setting this field to Yes, allows the following equipments to be modeled along an AirflowNetwork model: ZoneHVAC:Dehumidifier, ZoneHVAC:EnergyRecoveryVentilator, WaterHeater:HeatPump:*.",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                }
            }
        }
    },
    "group": "AirflowNetwork",
    "name": {
        "type": "string",
        "is_required": true,
        "note": "Enter a unique name for this object."
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "airflownetwork_control": {
                "field_name": "AirflowNetwork Control",
                "field_type": "a"
            },
            "wind_pressure_coefficient_type": {
                "field_name": "Wind Pressure Coefficient Type",
                "field_type": "a"
            },
            "height_selection_for_local_wind_pressure_calculation": {
                "field_name": "Height Selection for Local Wind Pressure Calculation",
                "field_type": "a"
            },
            "building_type": {
                "field_name": "Building Type",
                "field_type": "a"
            },
            "maximum_number_of_iterations": {
                "field_name": "Maximum Number of Iterations",
                "field_type": "n"
            },
            "initialization_type": {
                "field_name": "Initialization Type",
                "field_type": "a"
            },
            "relative_airflow_convergence_tolerance": {
                "field_name": "Relative Airflow Convergence Tolerance",
                "field_type": "n"
            },
            "absolute_airflow_convergence_tolerance": {
                "field_name": "Absolute Airflow Convergence Tolerance",
                "field_type": "n"
            },
            "convergence_acceleration_limit": {
                "field_name": "Convergence Acceleration Limit",
                "field_type": "n"
            },
            "azimuth_angle_of_long_axis_of_building": {
                "field_name": "Azimuth Angle of Long Axis of Building",
                "field_type": "n"
            },
            "ratio_of_building_width_along_short_axis_to_width_along_long_axis": {
                "field_name": "Ratio of Building Width Along Short Axis to Width Along Long Axis",
                "field_type": "n"
            },
            "height_dependence_of_external_node_temperature": {
                "field_name": "Height Dependence of External Node Temperature",
                "field_type": "a"
            },
            "solver": {
                "field_name": "Solver",
                "field_type": "a"
            },
            "allow_unsupported_zone_equipment": {
                "field_name": "Allow Unsupported Zone Equipment",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "airflownetwork_control",
            "wind_pressure_coefficient_type",
            "height_selection_for_local_wind_pressure_calculation",
            "building_type",
            "maximum_number_of_iterations",
            "initialization_type",
            "relative_airflow_convergence_tolerance",
            "absolute_airflow_convergence_tolerance",
            "convergence_acceleration_limit",
            "azimuth_angle_of_long_axis_of_building",
            "ratio_of_building_width_along_short_axis_to_width_along_long_axis",
            "height_dependence_of_external_node_temperature",
            "solver",
            "allow_unsupported_zone_equipment"
        ],
        "alphas": {
            "fields": [
                "name",
                "airflownetwork_control",
                "wind_pressure_coefficient_type",
                "height_selection_for_local_wind_pressure_calculation",
                "building_type",
                "initialization_type",
                "height_dependence_of_external_node_temperature",
                "solver",
                "allow_unsupported_zone_equipment"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_number_of_iterations",
                "relative_airflow_convergence_tolerance",
                "absolute_airflow_convergence_tolerance",
                "convergence_acceleration_limit",
                "azimuth_angle_of_long_axis_of_building",
                "ratio_of_building_width_along_short_axis_to_width_along_long_axis"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "This object defines the global parameters used in an Airflow Network simulation.",
    "min_fields": 12.0
}
```
