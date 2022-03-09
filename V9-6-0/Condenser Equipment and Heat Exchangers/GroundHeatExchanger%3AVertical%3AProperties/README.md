```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "depth_of_top_of_borehole": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "borehole_length": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m"
                },
                "borehole_diameter": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m",
                    "ip-units": "in"
                },
                "grout_thermal_conductivity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "W/m-K"
                },
                "grout_thermal_heat_capacity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "J/m3-K"
                },
                "pipe_thermal_conductivity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "W/m-K"
                },
                "pipe_thermal_heat_capacity": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "J/m3-K"
                },
                "pipe_outer_diameter": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m",
                    "ip-units": "in"
                },
                "pipe_thickness": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m",
                    "ip-units": "in"
                },
                "u_tube_distance": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "units": "m"
                }
            },
            "required": [
                "depth_of_top_of_borehole",
                "borehole_length",
                "borehole_diameter",
                "grout_thermal_conductivity",
                "grout_thermal_heat_capacity",
                "pipe_thermal_conductivity",
                "pipe_thermal_heat_capacity",
                "pipe_outer_diameter",
                "pipe_thickness",
                "u_tube_distance"
            ]
        }
    },
    "group": "Condenser Equipment and Heat Exchangers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "GroundHeatExchangerVerticalPropertiesNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "depth_of_top_of_borehole": {
                "field_name": "Depth of Top of Borehole",
                "field_type": "n"
            },
            "borehole_length": {
                "field_name": "Borehole Length",
                "field_type": "n"
            },
            "borehole_diameter": {
                "field_name": "Borehole Diameter",
                "field_type": "n"
            },
            "grout_thermal_conductivity": {
                "field_name": "Grout Thermal Conductivity",
                "field_type": "n"
            },
            "grout_thermal_heat_capacity": {
                "field_name": "Grout Thermal Heat Capacity",
                "field_type": "n"
            },
            "pipe_thermal_conductivity": {
                "field_name": "Pipe Thermal Conductivity",
                "field_type": "n"
            },
            "pipe_thermal_heat_capacity": {
                "field_name": "Pipe Thermal Heat Capacity",
                "field_type": "n"
            },
            "pipe_outer_diameter": {
                "field_name": "Pipe Outer Diameter",
                "field_type": "n"
            },
            "pipe_thickness": {
                "field_name": "Pipe Thickness",
                "field_type": "n"
            },
            "u_tube_distance": {
                "field_name": "U-Tube Distance",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "depth_of_top_of_borehole",
            "borehole_length",
            "borehole_diameter",
            "grout_thermal_conductivity",
            "grout_thermal_heat_capacity",
            "pipe_thermal_conductivity",
            "pipe_thermal_heat_capacity",
            "pipe_outer_diameter",
            "pipe_thickness",
            "u_tube_distance"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "depth_of_top_of_borehole",
                "borehole_length",
                "borehole_diameter",
                "grout_thermal_conductivity",
                "grout_thermal_heat_capacity",
                "pipe_thermal_conductivity",
                "pipe_thermal_heat_capacity",
                "pipe_outer_diameter",
                "pipe_thickness",
                "u_tube_distance"
            ]
        }
    },
    "type": "object",
    "memo": "Properties for vertical ground heat exchanger systems",
    "min_fields": 11.0
}
```
