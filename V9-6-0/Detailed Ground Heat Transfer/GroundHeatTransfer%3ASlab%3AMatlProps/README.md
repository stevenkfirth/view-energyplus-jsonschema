```
{
    "GroundHeatTransfer:Slab:MatlProps": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "rho_slab_material_density": {
                        "type": "number",
                        "note": "Density of Slab Material typical value= 2300.0",
                        "units": "kg/m3",
                        "exclusiveMinimum": 0.0,
                        "default": 2300.0
                    },
                    "rho_soil_density": {
                        "type": "number",
                        "note": "Density of Soil Material typical value= 1200.0",
                        "exclusiveMinimum": 0.0,
                        "default": 1200.0,
                        "units": "kg/m3"
                    },
                    "cp_slab_cp": {
                        "type": "number",
                        "note": "Specific Heat of Slab Material typical value=650.0",
                        "units": "J/kg-K",
                        "exclusiveMinimum": 0.0,
                        "default": 650.0
                    },
                    "cp_soil_cp": {
                        "type": "number",
                        "note": "Specific Heat of Soil Material typical value= 1200.0",
                        "exclusiveMinimum": 0.0,
                        "default": 1200.0,
                        "units": "J/kg-K"
                    },
                    "tcon_slab_k": {
                        "type": "number",
                        "note": "Conductivity of Slab Material typical value= .9",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K",
                        "default": 0.9
                    },
                    "tcon_soil_k": {
                        "type": "number",
                        "note": "Conductivity of Soil Material typical value= 1.0",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K",
                        "default": 1.0
                    }
                }
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "rho_slab_material_density": {
                    "field_name": "RHO: Slab Material density",
                    "field_type": "n"
                },
                "rho_soil_density": {
                    "field_name": "RHO: Soil Density",
                    "field_type": "n"
                },
                "cp_slab_cp": {
                    "field_name": "CP: Slab CP",
                    "field_type": "n"
                },
                "cp_soil_cp": {
                    "field_name": "CP: Soil CP",
                    "field_type": "n"
                },
                "tcon_slab_k": {
                    "field_name": "TCON: Slab k",
                    "field_type": "n"
                },
                "tcon_soil_k": {
                    "field_name": "TCON: Soil k",
                    "field_type": "n"
                }
            },
            "fields": [
                "rho_slab_material_density",
                "rho_soil_density",
                "cp_slab_cp",
                "cp_soil_cp",
                "tcon_slab_k",
                "tcon_soil_k"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "rho_slab_material_density",
                    "rho_soil_density",
                    "cp_slab_cp",
                    "cp_soil_cp",
                    "tcon_slab_k",
                    "tcon_soil_k"
                ]
            }
        },
        "type": "object",
        "memo": "This object contains the material properties for the materials used in the model. The fields are mostly self explanatory."
    }
}
```
