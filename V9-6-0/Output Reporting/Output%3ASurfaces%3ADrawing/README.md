```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "report_type": {
                    "type": "string",
                    "enum": [
                        "DXF",
                        "DXF:WireFrame",
                        "VRML"
                    ]
                },
                "report_specifications_1": {
                    "type": "string",
                    "enum": [
                        "",
                        "RegularPolyline",
                        "ThickPolyline",
                        "Triangulate3DFace"
                    ],
                    "default": "Triangulate3DFace",
                    "note": "Triangulate3DFace (default), ThickPolyline, RegularPolyline apply to DXF This field is ignored for DXF:WireFrame and VRML"
                },
                "report_specifications_2": {
                    "type": "string",
                    "note": "Use ColorScheme Name for DXF reports",
                    "data_type": "object_list",
                    "object_list": [
                        "ColorSchemes"
                    ]
                }
            },
            "required": [
                "report_type"
            ]
        }
    },
    "group": "Output Reporting",
    "legacy_idd": {
        "field_info": {
            "report_type": {
                "field_name": "Report Type",
                "field_type": "a"
            },
            "report_specifications_1": {
                "field_name": "Report Specifications 1",
                "field_type": "a"
            },
            "report_specifications_2": {
                "field_name": "Report Specifications 2",
                "field_type": "a"
            }
        },
        "fields": [
            "report_type",
            "report_specifications_1",
            "report_specifications_2"
        ],
        "alphas": {
            "fields": [
                "report_type",
                "report_specifications_1",
                "report_specifications_2"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Produces reports/files that are capable of rendering graphically or being imported into other programs. Rendering does not alter the actual inputs/surfaces.",
    "format": "singleLine"
}
```
