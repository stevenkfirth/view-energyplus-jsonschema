```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "gross_area": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m2"
                },
                "test_fluid": {
                    "type": "string",
                    "enum": [
                        "",
                        "Water"
                    ],
                    "default": "Water"
                },
                "test_flow_rate": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m3/s",
                    "ip-units": "gal/min"
                },
                "test_correlation_type": {
                    "type": "string",
                    "enum": [
                        "Average",
                        "Inlet",
                        "Outlet"
                    ]
                },
                "coefficient_1_of_efficiency_equation": {
                    "type": "number",
                    "units": "dimensionless",
                    "note": "Y-intercept term"
                },
                "coefficient_2_of_efficiency_equation": {
                    "type": "number",
                    "units": "W/m2-K",
                    "note": "1st Order term"
                },
                "coefficient_3_of_efficiency_equation": {
                    "type": "number",
                    "units": "W/m2-K2",
                    "note": "2nd order term"
                },
                "coefficient_2_of_incident_angle_modifier": {
                    "type": "number",
                    "note": "1st order term"
                },
                "coefficient_3_of_incident_angle_modifier": {
                    "type": "number",
                    "note": "2nd order term"
                }
            },
            "required": [
                "gross_area",
                "test_flow_rate",
                "test_correlation_type",
                "coefficient_1_of_efficiency_equation",
                "coefficient_2_of_efficiency_equation"
            ]
        }
    },
    "group": "Solar Collectors",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "FlatPlateSolarCollectorParameters"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "gross_area": {
                "field_name": "Gross Area",
                "field_type": "n"
            },
            "test_fluid": {
                "field_name": "Test Fluid",
                "field_type": "a"
            },
            "test_flow_rate": {
                "field_name": "Test Flow Rate",
                "field_type": "n"
            },
            "test_correlation_type": {
                "field_name": "Test Correlation Type",
                "field_type": "a"
            },
            "coefficient_1_of_efficiency_equation": {
                "field_name": "Coefficient 1 of Efficiency Equation",
                "field_type": "n"
            },
            "coefficient_2_of_efficiency_equation": {
                "field_name": "Coefficient 2 of Efficiency Equation",
                "field_type": "n"
            },
            "coefficient_3_of_efficiency_equation": {
                "field_name": "Coefficient 3 of Efficiency Equation",
                "field_type": "n"
            },
            "coefficient_2_of_incident_angle_modifier": {
                "field_name": "Coefficient 2 of Incident Angle Modifier",
                "field_type": "n"
            },
            "coefficient_3_of_incident_angle_modifier": {
                "field_name": "Coefficient 3 of Incident Angle Modifier",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "gross_area",
            "test_fluid",
            "test_flow_rate",
            "test_correlation_type",
            "coefficient_1_of_efficiency_equation",
            "coefficient_2_of_efficiency_equation",
            "coefficient_3_of_efficiency_equation",
            "coefficient_2_of_incident_angle_modifier",
            "coefficient_3_of_incident_angle_modifier"
        ],
        "alphas": {
            "fields": [
                "name",
                "test_fluid",
                "test_correlation_type"
            ]
        },
        "numerics": {
            "fields": [
                "gross_area",
                "test_flow_rate",
                "coefficient_1_of_efficiency_equation",
                "coefficient_2_of_efficiency_equation",
                "coefficient_3_of_efficiency_equation",
                "coefficient_2_of_incident_angle_modifier",
                "coefficient_3_of_incident_angle_modifier"
            ]
        }
    },
    "type": "object",
    "memo": "Thermal and optical performance parameters for a single flat plate solar collector module. These parameters are based on the testing methodologies described in ASHRAE Standards 93 and 96 which are used Solar Rating and Certification Corporation (SRCC) Directory of SRCC Certified Solar Collector Ratings. See EnergyPlus DataSets file SolarCollectors.idf.",
    "min_fields": 7.0
}
```
