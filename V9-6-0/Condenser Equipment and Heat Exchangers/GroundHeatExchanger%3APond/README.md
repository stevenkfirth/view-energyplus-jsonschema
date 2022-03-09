```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "fluid_inlet_node_name": {
                    "type": "string"
                },
                "fluid_outlet_node_name": {
                    "type": "string"
                },
                "pond_depth": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0
                },
                "pond_area": {
                    "type": "number",
                    "units": "m2",
                    "exclusiveMinimum": 0.0
                },
                "hydronic_tubing_inside_diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "in"
                },
                "hydronic_tubing_outside_diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "in"
                },
                "hydronic_tubing_thermal_conductivity": {
                    "type": "number",
                    "units": "W/m-K",
                    "exclusiveMinimum": 0.0
                },
                "ground_thermal_conductivity": {
                    "type": "number",
                    "units": "W/m2-K",
                    "exclusiveMinimum": 0.0
                },
                "number_of_tubing_circuits": {
                    "type": "number",
                    "minimum": 1.0
                },
                "length_of_each_tubing_circuit": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                }
            },
            "required": [
                "fluid_inlet_node_name",
                "fluid_outlet_node_name",
                "pond_depth",
                "pond_area",
                "hydronic_tubing_inside_diameter",
                "hydronic_tubing_outside_diameter",
                "hydronic_tubing_thermal_conductivity",
                "ground_thermal_conductivity",
                "number_of_tubing_circuits",
                "length_of_each_tubing_circuit"
            ]
        }
    },
    "group": "Condenser Equipment and Heat Exchangers",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validCondenserEquipmentTypes",
            "validPlantEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validCondenserEquipmentNames",
            "validPlantEquipmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "fluid_inlet_node_name": {
                "field_name": "Fluid Inlet Node Name",
                "field_type": "a"
            },
            "fluid_outlet_node_name": {
                "field_name": "Fluid Outlet Node Name",
                "field_type": "a"
            },
            "pond_depth": {
                "field_name": "Pond Depth",
                "field_type": "n"
            },
            "pond_area": {
                "field_name": "Pond Area",
                "field_type": "n"
            },
            "hydronic_tubing_inside_diameter": {
                "field_name": "Hydronic Tubing Inside Diameter",
                "field_type": "n"
            },
            "hydronic_tubing_outside_diameter": {
                "field_name": "Hydronic Tubing Outside Diameter",
                "field_type": "n"
            },
            "hydronic_tubing_thermal_conductivity": {
                "field_name": "Hydronic Tubing Thermal Conductivity",
                "field_type": "n"
            },
            "ground_thermal_conductivity": {
                "field_name": "Ground Thermal Conductivity",
                "field_type": "n"
            },
            "number_of_tubing_circuits": {
                "field_name": "Number of Tubing Circuits",
                "field_type": "n"
            },
            "length_of_each_tubing_circuit": {
                "field_name": "Length of Each Tubing Circuit",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "fluid_inlet_node_name",
            "fluid_outlet_node_name",
            "pond_depth",
            "pond_area",
            "hydronic_tubing_inside_diameter",
            "hydronic_tubing_outside_diameter",
            "hydronic_tubing_thermal_conductivity",
            "ground_thermal_conductivity",
            "number_of_tubing_circuits",
            "length_of_each_tubing_circuit"
        ],
        "alphas": {
            "fields": [
                "name",
                "fluid_inlet_node_name",
                "fluid_outlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "pond_depth",
                "pond_area",
                "hydronic_tubing_inside_diameter",
                "hydronic_tubing_outside_diameter",
                "hydronic_tubing_thermal_conductivity",
                "ground_thermal_conductivity",
                "number_of_tubing_circuits",
                "length_of_each_tubing_circuit"
            ]
        }
    },
    "type": "object",
    "memo": "A model of a shallow pond with immersed pipe loops. Typically used in hybrid geothermal systems and included in the condenser loop. This component may also be used as a simple solar collector."
}
```
