```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "fluid_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FluidNames"
                    ]
                },
                "fluid_property_type": {
                    "type": "string",
                    "note": "Enthalpy Units are J/kg Density Units are kg/m3",
                    "enum": [
                        "Density",
                        "Enthalpy"
                    ]
                },
                "temperature_values_name": {
                    "type": "string",
                    "note": "Enter the name of a FluidProperties:Temperatures object.",
                    "data_type": "object_list",
                    "object_list": [
                        "FluidPropertyTemperatures"
                    ]
                },
                "pressure": {
                    "type": "number",
                    "note": "pressure for this list of properties",
                    "units": "Pa",
                    "exclusiveMinimum": 0.0
                },
                "property_value_1": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_2": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_3": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_4": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_5": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_6": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_7": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_8": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_9": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_10": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_11": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_12": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_13": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_14": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_15": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_16": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_17": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_18": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_19": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_20": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_21": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_22": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_23": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_24": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_25": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_26": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_27": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_28": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_29": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_30": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_31": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_32": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_33": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_34": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_35": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_36": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_37": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_38": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_39": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_40": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_41": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_42": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_43": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_44": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_45": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_46": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_47": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_48": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_49": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_50": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_51": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_52": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_53": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_54": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_55": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_56": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_57": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_58": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_59": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_60": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_61": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_62": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_63": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_64": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_65": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_66": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_67": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_68": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_69": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_70": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_71": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_72": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_73": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_74": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_75": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_76": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_77": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_78": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_79": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_80": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_81": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_82": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_83": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_84": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_85": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_86": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_87": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_88": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_89": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_90": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_91": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_92": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_93": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_94": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_95": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_96": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_97": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_98": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_99": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_100": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_101": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_102": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_103": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_104": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_105": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_106": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_107": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_108": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_109": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_110": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_111": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_112": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_113": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_114": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_115": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_116": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_117": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_118": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_119": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_120": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_121": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_122": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_123": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_124": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_125": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_126": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_127": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_128": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_129": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_130": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_131": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_132": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_133": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_134": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_135": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_136": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_137": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_138": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_139": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_140": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_141": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_142": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_143": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_144": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_145": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_146": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_147": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_148": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_149": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_150": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_151": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_152": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_153": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_154": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_155": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_156": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_157": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_158": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_159": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_160": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_161": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_162": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_163": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_164": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_165": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_166": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_167": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_168": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_169": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_170": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_171": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_172": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_173": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_174": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_175": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_176": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_177": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_178": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_179": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_180": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_181": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_182": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_183": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_184": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_185": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_186": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_187": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_188": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_189": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_190": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_191": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_192": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_193": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_194": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_195": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_196": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_197": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_198": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_199": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_200": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_201": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_202": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_203": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_204": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_205": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_206": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_207": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_208": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_209": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_210": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_211": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_212": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_213": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_214": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_215": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_216": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_217": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_218": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_219": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_220": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_221": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_222": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_223": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_224": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_225": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_226": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_227": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_228": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_229": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_230": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_231": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_232": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_233": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_234": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_235": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_236": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_237": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_238": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_239": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_240": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_241": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_242": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_243": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_244": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_245": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_246": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_247": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_248": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_249": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                },
                "property_value_250": {
                    "type": "number",
                    "unitsBasedOnField": "fluid_property_type"
                }
            }
        }
    },
    "group": "Fluid Properties",
    "legacy_idd": {
        "field_info": {
            "fluid_name": {
                "field_name": "Fluid Name",
                "field_type": "a"
            },
            "fluid_property_type": {
                "field_name": "Fluid Property Type",
                "field_type": "a"
            },
            "temperature_values_name": {
                "field_name": "Temperature Values Name",
                "field_type": "a"
            },
            "pressure": {
                "field_name": "Pressure",
                "field_type": "n"
            },
            "property_value_1": {
                "field_name": "Property Value 1",
                "field_type": "n"
            },
            "property_value_2": {
                "field_name": "Property Value 2",
                "field_type": "n"
            },
            "property_value_3": {
                "field_name": "Property Value 3",
                "field_type": "n"
            },
            "property_value_4": {
                "field_name": "Property Value 4",
                "field_type": "n"
            },
            "property_value_5": {
                "field_name": "Property Value 5",
                "field_type": "n"
            },
            "property_value_6": {
                "field_name": "Property Value 6",
                "field_type": "n"
            },
            "property_value_7": {
                "field_name": "Property Value 7",
                "field_type": "n"
            },
            "property_value_8": {
                "field_name": "Property Value 8",
                "field_type": "n"
            },
            "property_value_9": {
                "field_name": "Property Value 9",
                "field_type": "n"
            },
            "property_value_10": {
                "field_name": "Property Value 10",
                "field_type": "n"
            },
            "property_value_11": {
                "field_name": "Property Value 11",
                "field_type": "n"
            },
            "property_value_12": {
                "field_name": "Property Value 12",
                "field_type": "n"
            },
            "property_value_13": {
                "field_name": "Property Value 13",
                "field_type": "n"
            },
            "property_value_14": {
                "field_name": "Property Value 14",
                "field_type": "n"
            },
            "property_value_15": {
                "field_name": "Property Value 15",
                "field_type": "n"
            },
            "property_value_16": {
                "field_name": "Property Value 16",
                "field_type": "n"
            },
            "property_value_17": {
                "field_name": "Property Value 17",
                "field_type": "n"
            },
            "property_value_18": {
                "field_name": "Property Value 18",
                "field_type": "n"
            },
            "property_value_19": {
                "field_name": "Property Value 19",
                "field_type": "n"
            },
            "property_value_20": {
                "field_name": "Property Value 20",
                "field_type": "n"
            },
            "property_value_21": {
                "field_name": "Property Value 21",
                "field_type": "n"
            },
            "property_value_22": {
                "field_name": "Property Value 22",
                "field_type": "n"
            },
            "property_value_23": {
                "field_name": "Property Value 23",
                "field_type": "n"
            },
            "property_value_24": {
                "field_name": "Property Value 24",
                "field_type": "n"
            },
            "property_value_25": {
                "field_name": "Property Value 25",
                "field_type": "n"
            },
            "property_value_26": {
                "field_name": "Property Value 26",
                "field_type": "n"
            },
            "property_value_27": {
                "field_name": "Property Value 27",
                "field_type": "n"
            },
            "property_value_28": {
                "field_name": "Property Value 28",
                "field_type": "n"
            },
            "property_value_29": {
                "field_name": "Property Value 29",
                "field_type": "n"
            },
            "property_value_30": {
                "field_name": "Property Value 30",
                "field_type": "n"
            },
            "property_value_31": {
                "field_name": "Property Value 31",
                "field_type": "n"
            },
            "property_value_32": {
                "field_name": "Property Value 32",
                "field_type": "n"
            },
            "property_value_33": {
                "field_name": "Property Value 33",
                "field_type": "n"
            },
            "property_value_34": {
                "field_name": "Property Value 34",
                "field_type": "n"
            },
            "property_value_35": {
                "field_name": "Property Value 35",
                "field_type": "n"
            },
            "property_value_36": {
                "field_name": "Property Value 36",
                "field_type": "n"
            },
            "property_value_37": {
                "field_name": "Property Value 37",
                "field_type": "n"
            },
            "property_value_38": {
                "field_name": "Property Value 38",
                "field_type": "n"
            },
            "property_value_39": {
                "field_name": "Property Value 39",
                "field_type": "n"
            },
            "property_value_40": {
                "field_name": "Property Value 40",
                "field_type": "n"
            },
            "property_value_41": {
                "field_name": "Property Value 41",
                "field_type": "n"
            },
            "property_value_42": {
                "field_name": "Property Value 42",
                "field_type": "n"
            },
            "property_value_43": {
                "field_name": "Property Value 43",
                "field_type": "n"
            },
            "property_value_44": {
                "field_name": "Property Value 44",
                "field_type": "n"
            },
            "property_value_45": {
                "field_name": "Property Value 45",
                "field_type": "n"
            },
            "property_value_46": {
                "field_name": "Property Value 46",
                "field_type": "n"
            },
            "property_value_47": {
                "field_name": "Property Value 47",
                "field_type": "n"
            },
            "property_value_48": {
                "field_name": "Property Value 48",
                "field_type": "n"
            },
            "property_value_49": {
                "field_name": "Property Value 49",
                "field_type": "n"
            },
            "property_value_50": {
                "field_name": "Property Value 50",
                "field_type": "n"
            },
            "property_value_51": {
                "field_name": "Property Value 51",
                "field_type": "n"
            },
            "property_value_52": {
                "field_name": "Property Value 52",
                "field_type": "n"
            },
            "property_value_53": {
                "field_name": "Property Value 53",
                "field_type": "n"
            },
            "property_value_54": {
                "field_name": "Property Value 54",
                "field_type": "n"
            },
            "property_value_55": {
                "field_name": "Property Value 55",
                "field_type": "n"
            },
            "property_value_56": {
                "field_name": "Property Value 56",
                "field_type": "n"
            },
            "property_value_57": {
                "field_name": "Property Value 57",
                "field_type": "n"
            },
            "property_value_58": {
                "field_name": "Property Value 58",
                "field_type": "n"
            },
            "property_value_59": {
                "field_name": "Property Value 59",
                "field_type": "n"
            },
            "property_value_60": {
                "field_name": "Property Value 60",
                "field_type": "n"
            },
            "property_value_61": {
                "field_name": "Property Value 61",
                "field_type": "n"
            },
            "property_value_62": {
                "field_name": "Property Value 62",
                "field_type": "n"
            },
            "property_value_63": {
                "field_name": "Property Value 63",
                "field_type": "n"
            },
            "property_value_64": {
                "field_name": "Property Value 64",
                "field_type": "n"
            },
            "property_value_65": {
                "field_name": "Property Value 65",
                "field_type": "n"
            },
            "property_value_66": {
                "field_name": "Property Value 66",
                "field_type": "n"
            },
            "property_value_67": {
                "field_name": "Property Value 67",
                "field_type": "n"
            },
            "property_value_68": {
                "field_name": "Property Value 68",
                "field_type": "n"
            },
            "property_value_69": {
                "field_name": "Property Value 69",
                "field_type": "n"
            },
            "property_value_70": {
                "field_name": "Property Value 70",
                "field_type": "n"
            },
            "property_value_71": {
                "field_name": "Property Value 71",
                "field_type": "n"
            },
            "property_value_72": {
                "field_name": "Property Value 72",
                "field_type": "n"
            },
            "property_value_73": {
                "field_name": "Property Value 73",
                "field_type": "n"
            },
            "property_value_74": {
                "field_name": "Property Value 74",
                "field_type": "n"
            },
            "property_value_75": {
                "field_name": "Property Value 75",
                "field_type": "n"
            },
            "property_value_76": {
                "field_name": "Property Value 76",
                "field_type": "n"
            },
            "property_value_77": {
                "field_name": "Property Value 77",
                "field_type": "n"
            },
            "property_value_78": {
                "field_name": "Property Value 78",
                "field_type": "n"
            },
            "property_value_79": {
                "field_name": "Property Value 79",
                "field_type": "n"
            },
            "property_value_80": {
                "field_name": "Property Value 80",
                "field_type": "n"
            },
            "property_value_81": {
                "field_name": "Property Value 81",
                "field_type": "n"
            },
            "property_value_82": {
                "field_name": "Property Value 82",
                "field_type": "n"
            },
            "property_value_83": {
                "field_name": "Property Value 83",
                "field_type": "n"
            },
            "property_value_84": {
                "field_name": "Property Value 84",
                "field_type": "n"
            },
            "property_value_85": {
                "field_name": "Property Value 85",
                "field_type": "n"
            },
            "property_value_86": {
                "field_name": "Property Value 86",
                "field_type": "n"
            },
            "property_value_87": {
                "field_name": "Property Value 87",
                "field_type": "n"
            },
            "property_value_88": {
                "field_name": "Property Value 88",
                "field_type": "n"
            },
            "property_value_89": {
                "field_name": "Property Value 89",
                "field_type": "n"
            },
            "property_value_90": {
                "field_name": "Property Value 90",
                "field_type": "n"
            },
            "property_value_91": {
                "field_name": "Property Value 91",
                "field_type": "n"
            },
            "property_value_92": {
                "field_name": "Property Value 92",
                "field_type": "n"
            },
            "property_value_93": {
                "field_name": "Property Value 93",
                "field_type": "n"
            },
            "property_value_94": {
                "field_name": "Property Value 94",
                "field_type": "n"
            },
            "property_value_95": {
                "field_name": "Property Value 95",
                "field_type": "n"
            },
            "property_value_96": {
                "field_name": "Property Value 96",
                "field_type": "n"
            },
            "property_value_97": {
                "field_name": "Property Value 97",
                "field_type": "n"
            },
            "property_value_98": {
                "field_name": "Property Value 98",
                "field_type": "n"
            },
            "property_value_99": {
                "field_name": "Property Value 99",
                "field_type": "n"
            },
            "property_value_100": {
                "field_name": "Property Value 100",
                "field_type": "n"
            },
            "property_value_101": {
                "field_name": "Property Value 101",
                "field_type": "n"
            },
            "property_value_102": {
                "field_name": "Property Value 102",
                "field_type": "n"
            },
            "property_value_103": {
                "field_name": "Property Value 103",
                "field_type": "n"
            },
            "property_value_104": {
                "field_name": "Property Value 104",
                "field_type": "n"
            },
            "property_value_105": {
                "field_name": "Property Value 105",
                "field_type": "n"
            },
            "property_value_106": {
                "field_name": "Property Value 106",
                "field_type": "n"
            },
            "property_value_107": {
                "field_name": "Property Value 107",
                "field_type": "n"
            },
            "property_value_108": {
                "field_name": "Property Value 108",
                "field_type": "n"
            },
            "property_value_109": {
                "field_name": "Property Value 109",
                "field_type": "n"
            },
            "property_value_110": {
                "field_name": "Property Value 110",
                "field_type": "n"
            },
            "property_value_111": {
                "field_name": "Property Value 111",
                "field_type": "n"
            },
            "property_value_112": {
                "field_name": "Property Value 112",
                "field_type": "n"
            },
            "property_value_113": {
                "field_name": "Property Value 113",
                "field_type": "n"
            },
            "property_value_114": {
                "field_name": "Property Value 114",
                "field_type": "n"
            },
            "property_value_115": {
                "field_name": "Property Value 115",
                "field_type": "n"
            },
            "property_value_116": {
                "field_name": "Property Value 116",
                "field_type": "n"
            },
            "property_value_117": {
                "field_name": "Property Value 117",
                "field_type": "n"
            },
            "property_value_118": {
                "field_name": "Property Value 118",
                "field_type": "n"
            },
            "property_value_119": {
                "field_name": "Property Value 119",
                "field_type": "n"
            },
            "property_value_120": {
                "field_name": "Property Value 120",
                "field_type": "n"
            },
            "property_value_121": {
                "field_name": "Property Value 121",
                "field_type": "n"
            },
            "property_value_122": {
                "field_name": "Property Value 122",
                "field_type": "n"
            },
            "property_value_123": {
                "field_name": "Property Value 123",
                "field_type": "n"
            },
            "property_value_124": {
                "field_name": "Property Value 124",
                "field_type": "n"
            },
            "property_value_125": {
                "field_name": "Property Value 125",
                "field_type": "n"
            },
            "property_value_126": {
                "field_name": "Property Value 126",
                "field_type": "n"
            },
            "property_value_127": {
                "field_name": "Property Value 127",
                "field_type": "n"
            },
            "property_value_128": {
                "field_name": "Property Value 128",
                "field_type": "n"
            },
            "property_value_129": {
                "field_name": "Property Value 129",
                "field_type": "n"
            },
            "property_value_130": {
                "field_name": "Property Value 130",
                "field_type": "n"
            },
            "property_value_131": {
                "field_name": "Property Value 131",
                "field_type": "n"
            },
            "property_value_132": {
                "field_name": "Property Value 132",
                "field_type": "n"
            },
            "property_value_133": {
                "field_name": "Property Value 133",
                "field_type": "n"
            },
            "property_value_134": {
                "field_name": "Property Value 134",
                "field_type": "n"
            },
            "property_value_135": {
                "field_name": "Property Value 135",
                "field_type": "n"
            },
            "property_value_136": {
                "field_name": "Property Value 136",
                "field_type": "n"
            },
            "property_value_137": {
                "field_name": "Property Value 137",
                "field_type": "n"
            },
            "property_value_138": {
                "field_name": "Property Value 138",
                "field_type": "n"
            },
            "property_value_139": {
                "field_name": "Property Value 139",
                "field_type": "n"
            },
            "property_value_140": {
                "field_name": "Property Value 140",
                "field_type": "n"
            },
            "property_value_141": {
                "field_name": "Property Value 141",
                "field_type": "n"
            },
            "property_value_142": {
                "field_name": "Property Value 142",
                "field_type": "n"
            },
            "property_value_143": {
                "field_name": "Property Value 143",
                "field_type": "n"
            },
            "property_value_144": {
                "field_name": "Property Value 144",
                "field_type": "n"
            },
            "property_value_145": {
                "field_name": "Property Value 145",
                "field_type": "n"
            },
            "property_value_146": {
                "field_name": "Property Value 146",
                "field_type": "n"
            },
            "property_value_147": {
                "field_name": "Property Value 147",
                "field_type": "n"
            },
            "property_value_148": {
                "field_name": "Property Value 148",
                "field_type": "n"
            },
            "property_value_149": {
                "field_name": "Property Value 149",
                "field_type": "n"
            },
            "property_value_150": {
                "field_name": "Property Value 150",
                "field_type": "n"
            },
            "property_value_151": {
                "field_name": "Property Value 151",
                "field_type": "n"
            },
            "property_value_152": {
                "field_name": "Property Value 152",
                "field_type": "n"
            },
            "property_value_153": {
                "field_name": "Property Value 153",
                "field_type": "n"
            },
            "property_value_154": {
                "field_name": "Property Value 154",
                "field_type": "n"
            },
            "property_value_155": {
                "field_name": "Property Value 155",
                "field_type": "n"
            },
            "property_value_156": {
                "field_name": "Property Value 156",
                "field_type": "n"
            },
            "property_value_157": {
                "field_name": "Property Value 157",
                "field_type": "n"
            },
            "property_value_158": {
                "field_name": "Property Value 158",
                "field_type": "n"
            },
            "property_value_159": {
                "field_name": "Property Value 159",
                "field_type": "n"
            },
            "property_value_160": {
                "field_name": "Property Value 160",
                "field_type": "n"
            },
            "property_value_161": {
                "field_name": "Property Value 161",
                "field_type": "n"
            },
            "property_value_162": {
                "field_name": "Property Value 162",
                "field_type": "n"
            },
            "property_value_163": {
                "field_name": "Property Value 163",
                "field_type": "n"
            },
            "property_value_164": {
                "field_name": "Property Value 164",
                "field_type": "n"
            },
            "property_value_165": {
                "field_name": "Property Value 165",
                "field_type": "n"
            },
            "property_value_166": {
                "field_name": "Property Value 166",
                "field_type": "n"
            },
            "property_value_167": {
                "field_name": "Property Value 167",
                "field_type": "n"
            },
            "property_value_168": {
                "field_name": "Property Value 168",
                "field_type": "n"
            },
            "property_value_169": {
                "field_name": "Property Value 169",
                "field_type": "n"
            },
            "property_value_170": {
                "field_name": "Property Value 170",
                "field_type": "n"
            },
            "property_value_171": {
                "field_name": "Property Value 171",
                "field_type": "n"
            },
            "property_value_172": {
                "field_name": "Property Value 172",
                "field_type": "n"
            },
            "property_value_173": {
                "field_name": "Property Value 173",
                "field_type": "n"
            },
            "property_value_174": {
                "field_name": "Property Value 174",
                "field_type": "n"
            },
            "property_value_175": {
                "field_name": "Property Value 175",
                "field_type": "n"
            },
            "property_value_176": {
                "field_name": "Property Value 176",
                "field_type": "n"
            },
            "property_value_177": {
                "field_name": "Property Value 177",
                "field_type": "n"
            },
            "property_value_178": {
                "field_name": "Property Value 178",
                "field_type": "n"
            },
            "property_value_179": {
                "field_name": "Property Value 179",
                "field_type": "n"
            },
            "property_value_180": {
                "field_name": "Property Value 180",
                "field_type": "n"
            },
            "property_value_181": {
                "field_name": "Property Value 181",
                "field_type": "n"
            },
            "property_value_182": {
                "field_name": "Property Value 182",
                "field_type": "n"
            },
            "property_value_183": {
                "field_name": "Property Value 183",
                "field_type": "n"
            },
            "property_value_184": {
                "field_name": "Property Value 184",
                "field_type": "n"
            },
            "property_value_185": {
                "field_name": "Property Value 185",
                "field_type": "n"
            },
            "property_value_186": {
                "field_name": "Property Value 186",
                "field_type": "n"
            },
            "property_value_187": {
                "field_name": "Property Value 187",
                "field_type": "n"
            },
            "property_value_188": {
                "field_name": "Property Value 188",
                "field_type": "n"
            },
            "property_value_189": {
                "field_name": "Property Value 189",
                "field_type": "n"
            },
            "property_value_190": {
                "field_name": "Property Value 190",
                "field_type": "n"
            },
            "property_value_191": {
                "field_name": "Property Value 191",
                "field_type": "n"
            },
            "property_value_192": {
                "field_name": "Property Value 192",
                "field_type": "n"
            },
            "property_value_193": {
                "field_name": "Property Value 193",
                "field_type": "n"
            },
            "property_value_194": {
                "field_name": "Property Value 194",
                "field_type": "n"
            },
            "property_value_195": {
                "field_name": "Property Value 195",
                "field_type": "n"
            },
            "property_value_196": {
                "field_name": "Property Value 196",
                "field_type": "n"
            },
            "property_value_197": {
                "field_name": "Property Value 197",
                "field_type": "n"
            },
            "property_value_198": {
                "field_name": "Property Value 198",
                "field_type": "n"
            },
            "property_value_199": {
                "field_name": "Property Value 199",
                "field_type": "n"
            },
            "property_value_200": {
                "field_name": "Property Value 200",
                "field_type": "n"
            },
            "property_value_201": {
                "field_name": "Property Value 201",
                "field_type": "n"
            },
            "property_value_202": {
                "field_name": "Property Value 202",
                "field_type": "n"
            },
            "property_value_203": {
                "field_name": "Property Value 203",
                "field_type": "n"
            },
            "property_value_204": {
                "field_name": "Property Value 204",
                "field_type": "n"
            },
            "property_value_205": {
                "field_name": "Property Value 205",
                "field_type": "n"
            },
            "property_value_206": {
                "field_name": "Property Value 206",
                "field_type": "n"
            },
            "property_value_207": {
                "field_name": "Property Value 207",
                "field_type": "n"
            },
            "property_value_208": {
                "field_name": "Property Value 208",
                "field_type": "n"
            },
            "property_value_209": {
                "field_name": "Property Value 209",
                "field_type": "n"
            },
            "property_value_210": {
                "field_name": "Property Value 210",
                "field_type": "n"
            },
            "property_value_211": {
                "field_name": "Property Value 211",
                "field_type": "n"
            },
            "property_value_212": {
                "field_name": "Property Value 212",
                "field_type": "n"
            },
            "property_value_213": {
                "field_name": "Property Value 213",
                "field_type": "n"
            },
            "property_value_214": {
                "field_name": "Property Value 214",
                "field_type": "n"
            },
            "property_value_215": {
                "field_name": "Property Value 215",
                "field_type": "n"
            },
            "property_value_216": {
                "field_name": "Property Value 216",
                "field_type": "n"
            },
            "property_value_217": {
                "field_name": "Property Value 217",
                "field_type": "n"
            },
            "property_value_218": {
                "field_name": "Property Value 218",
                "field_type": "n"
            },
            "property_value_219": {
                "field_name": "Property Value 219",
                "field_type": "n"
            },
            "property_value_220": {
                "field_name": "Property Value 220",
                "field_type": "n"
            },
            "property_value_221": {
                "field_name": "Property Value 221",
                "field_type": "n"
            },
            "property_value_222": {
                "field_name": "Property Value 222",
                "field_type": "n"
            },
            "property_value_223": {
                "field_name": "Property Value 223",
                "field_type": "n"
            },
            "property_value_224": {
                "field_name": "Property Value 224",
                "field_type": "n"
            },
            "property_value_225": {
                "field_name": "Property Value 225",
                "field_type": "n"
            },
            "property_value_226": {
                "field_name": "Property Value 226",
                "field_type": "n"
            },
            "property_value_227": {
                "field_name": "Property Value 227",
                "field_type": "n"
            },
            "property_value_228": {
                "field_name": "Property Value 228",
                "field_type": "n"
            },
            "property_value_229": {
                "field_name": "Property Value 229",
                "field_type": "n"
            },
            "property_value_230": {
                "field_name": "Property Value 230",
                "field_type": "n"
            },
            "property_value_231": {
                "field_name": "Property Value 231",
                "field_type": "n"
            },
            "property_value_232": {
                "field_name": "Property Value 232",
                "field_type": "n"
            },
            "property_value_233": {
                "field_name": "Property Value 233",
                "field_type": "n"
            },
            "property_value_234": {
                "field_name": "Property Value 234",
                "field_type": "n"
            },
            "property_value_235": {
                "field_name": "Property Value 235",
                "field_type": "n"
            },
            "property_value_236": {
                "field_name": "Property Value 236",
                "field_type": "n"
            },
            "property_value_237": {
                "field_name": "Property Value 237",
                "field_type": "n"
            },
            "property_value_238": {
                "field_name": "Property Value 238",
                "field_type": "n"
            },
            "property_value_239": {
                "field_name": "Property Value 239",
                "field_type": "n"
            },
            "property_value_240": {
                "field_name": "Property Value 240",
                "field_type": "n"
            },
            "property_value_241": {
                "field_name": "Property Value 241",
                "field_type": "n"
            },
            "property_value_242": {
                "field_name": "Property Value 242",
                "field_type": "n"
            },
            "property_value_243": {
                "field_name": "Property Value 243",
                "field_type": "n"
            },
            "property_value_244": {
                "field_name": "Property Value 244",
                "field_type": "n"
            },
            "property_value_245": {
                "field_name": "Property Value 245",
                "field_type": "n"
            },
            "property_value_246": {
                "field_name": "Property Value 246",
                "field_type": "n"
            },
            "property_value_247": {
                "field_name": "Property Value 247",
                "field_type": "n"
            },
            "property_value_248": {
                "field_name": "Property Value 248",
                "field_type": "n"
            },
            "property_value_249": {
                "field_name": "Property Value 249",
                "field_type": "n"
            },
            "property_value_250": {
                "field_name": "Property Value 250",
                "field_type": "n"
            }
        },
        "fields": [
            "fluid_name",
            "fluid_property_type",
            "temperature_values_name",
            "pressure",
            "property_value_1",
            "property_value_2",
            "property_value_3",
            "property_value_4",
            "property_value_5",
            "property_value_6",
            "property_value_7",
            "property_value_8",
            "property_value_9",
            "property_value_10",
            "property_value_11",
            "property_value_12",
            "property_value_13",
            "property_value_14",
            "property_value_15",
            "property_value_16",
            "property_value_17",
            "property_value_18",
            "property_value_19",
            "property_value_20",
            "property_value_21",
            "property_value_22",
            "property_value_23",
            "property_value_24",
            "property_value_25",
            "property_value_26",
            "property_value_27",
            "property_value_28",
            "property_value_29",
            "property_value_30",
            "property_value_31",
            "property_value_32",
            "property_value_33",
            "property_value_34",
            "property_value_35",
            "property_value_36",
            "property_value_37",
            "property_value_38",
            "property_value_39",
            "property_value_40",
            "property_value_41",
            "property_value_42",
            "property_value_43",
            "property_value_44",
            "property_value_45",
            "property_value_46",
            "property_value_47",
            "property_value_48",
            "property_value_49",
            "property_value_50",
            "property_value_51",
            "property_value_52",
            "property_value_53",
            "property_value_54",
            "property_value_55",
            "property_value_56",
            "property_value_57",
            "property_value_58",
            "property_value_59",
            "property_value_60",
            "property_value_61",
            "property_value_62",
            "property_value_63",
            "property_value_64",
            "property_value_65",
            "property_value_66",
            "property_value_67",
            "property_value_68",
            "property_value_69",
            "property_value_70",
            "property_value_71",
            "property_value_72",
            "property_value_73",
            "property_value_74",
            "property_value_75",
            "property_value_76",
            "property_value_77",
            "property_value_78",
            "property_value_79",
            "property_value_80",
            "property_value_81",
            "property_value_82",
            "property_value_83",
            "property_value_84",
            "property_value_85",
            "property_value_86",
            "property_value_87",
            "property_value_88",
            "property_value_89",
            "property_value_90",
            "property_value_91",
            "property_value_92",
            "property_value_93",
            "property_value_94",
            "property_value_95",
            "property_value_96",
            "property_value_97",
            "property_value_98",
            "property_value_99",
            "property_value_100",
            "property_value_101",
            "property_value_102",
            "property_value_103",
            "property_value_104",
            "property_value_105",
            "property_value_106",
            "property_value_107",
            "property_value_108",
            "property_value_109",
            "property_value_110",
            "property_value_111",
            "property_value_112",
            "property_value_113",
            "property_value_114",
            "property_value_115",
            "property_value_116",
            "property_value_117",
            "property_value_118",
            "property_value_119",
            "property_value_120",
            "property_value_121",
            "property_value_122",
            "property_value_123",
            "property_value_124",
            "property_value_125",
            "property_value_126",
            "property_value_127",
            "property_value_128",
            "property_value_129",
            "property_value_130",
            "property_value_131",
            "property_value_132",
            "property_value_133",
            "property_value_134",
            "property_value_135",
            "property_value_136",
            "property_value_137",
            "property_value_138",
            "property_value_139",
            "property_value_140",
            "property_value_141",
            "property_value_142",
            "property_value_143",
            "property_value_144",
            "property_value_145",
            "property_value_146",
            "property_value_147",
            "property_value_148",
            "property_value_149",
            "property_value_150",
            "property_value_151",
            "property_value_152",
            "property_value_153",
            "property_value_154",
            "property_value_155",
            "property_value_156",
            "property_value_157",
            "property_value_158",
            "property_value_159",
            "property_value_160",
            "property_value_161",
            "property_value_162",
            "property_value_163",
            "property_value_164",
            "property_value_165",
            "property_value_166",
            "property_value_167",
            "property_value_168",
            "property_value_169",
            "property_value_170",
            "property_value_171",
            "property_value_172",
            "property_value_173",
            "property_value_174",
            "property_value_175",
            "property_value_176",
            "property_value_177",
            "property_value_178",
            "property_value_179",
            "property_value_180",
            "property_value_181",
            "property_value_182",
            "property_value_183",
            "property_value_184",
            "property_value_185",
            "property_value_186",
            "property_value_187",
            "property_value_188",
            "property_value_189",
            "property_value_190",
            "property_value_191",
            "property_value_192",
            "property_value_193",
            "property_value_194",
            "property_value_195",
            "property_value_196",
            "property_value_197",
            "property_value_198",
            "property_value_199",
            "property_value_200",
            "property_value_201",
            "property_value_202",
            "property_value_203",
            "property_value_204",
            "property_value_205",
            "property_value_206",
            "property_value_207",
            "property_value_208",
            "property_value_209",
            "property_value_210",
            "property_value_211",
            "property_value_212",
            "property_value_213",
            "property_value_214",
            "property_value_215",
            "property_value_216",
            "property_value_217",
            "property_value_218",
            "property_value_219",
            "property_value_220",
            "property_value_221",
            "property_value_222",
            "property_value_223",
            "property_value_224",
            "property_value_225",
            "property_value_226",
            "property_value_227",
            "property_value_228",
            "property_value_229",
            "property_value_230",
            "property_value_231",
            "property_value_232",
            "property_value_233",
            "property_value_234",
            "property_value_235",
            "property_value_236",
            "property_value_237",
            "property_value_238",
            "property_value_239",
            "property_value_240",
            "property_value_241",
            "property_value_242",
            "property_value_243",
            "property_value_244",
            "property_value_245",
            "property_value_246",
            "property_value_247",
            "property_value_248",
            "property_value_249",
            "property_value_250"
        ],
        "alphas": {
            "fields": [
                "fluid_name",
                "fluid_property_type",
                "temperature_values_name"
            ]
        },
        "numerics": {
            "fields": [
                "pressure",
                "property_value_1",
                "property_value_2",
                "property_value_3",
                "property_value_4",
                "property_value_5",
                "property_value_6",
                "property_value_7",
                "property_value_8",
                "property_value_9",
                "property_value_10",
                "property_value_11",
                "property_value_12",
                "property_value_13",
                "property_value_14",
                "property_value_15",
                "property_value_16",
                "property_value_17",
                "property_value_18",
                "property_value_19",
                "property_value_20",
                "property_value_21",
                "property_value_22",
                "property_value_23",
                "property_value_24",
                "property_value_25",
                "property_value_26",
                "property_value_27",
                "property_value_28",
                "property_value_29",
                "property_value_30",
                "property_value_31",
                "property_value_32",
                "property_value_33",
                "property_value_34",
                "property_value_35",
                "property_value_36",
                "property_value_37",
                "property_value_38",
                "property_value_39",
                "property_value_40",
                "property_value_41",
                "property_value_42",
                "property_value_43",
                "property_value_44",
                "property_value_45",
                "property_value_46",
                "property_value_47",
                "property_value_48",
                "property_value_49",
                "property_value_50",
                "property_value_51",
                "property_value_52",
                "property_value_53",
                "property_value_54",
                "property_value_55",
                "property_value_56",
                "property_value_57",
                "property_value_58",
                "property_value_59",
                "property_value_60",
                "property_value_61",
                "property_value_62",
                "property_value_63",
                "property_value_64",
                "property_value_65",
                "property_value_66",
                "property_value_67",
                "property_value_68",
                "property_value_69",
                "property_value_70",
                "property_value_71",
                "property_value_72",
                "property_value_73",
                "property_value_74",
                "property_value_75",
                "property_value_76",
                "property_value_77",
                "property_value_78",
                "property_value_79",
                "property_value_80",
                "property_value_81",
                "property_value_82",
                "property_value_83",
                "property_value_84",
                "property_value_85",
                "property_value_86",
                "property_value_87",
                "property_value_88",
                "property_value_89",
                "property_value_90",
                "property_value_91",
                "property_value_92",
                "property_value_93",
                "property_value_94",
                "property_value_95",
                "property_value_96",
                "property_value_97",
                "property_value_98",
                "property_value_99",
                "property_value_100",
                "property_value_101",
                "property_value_102",
                "property_value_103",
                "property_value_104",
                "property_value_105",
                "property_value_106",
                "property_value_107",
                "property_value_108",
                "property_value_109",
                "property_value_110",
                "property_value_111",
                "property_value_112",
                "property_value_113",
                "property_value_114",
                "property_value_115",
                "property_value_116",
                "property_value_117",
                "property_value_118",
                "property_value_119",
                "property_value_120",
                "property_value_121",
                "property_value_122",
                "property_value_123",
                "property_value_124",
                "property_value_125",
                "property_value_126",
                "property_value_127",
                "property_value_128",
                "property_value_129",
                "property_value_130",
                "property_value_131",
                "property_value_132",
                "property_value_133",
                "property_value_134",
                "property_value_135",
                "property_value_136",
                "property_value_137",
                "property_value_138",
                "property_value_139",
                "property_value_140",
                "property_value_141",
                "property_value_142",
                "property_value_143",
                "property_value_144",
                "property_value_145",
                "property_value_146",
                "property_value_147",
                "property_value_148",
                "property_value_149",
                "property_value_150",
                "property_value_151",
                "property_value_152",
                "property_value_153",
                "property_value_154",
                "property_value_155",
                "property_value_156",
                "property_value_157",
                "property_value_158",
                "property_value_159",
                "property_value_160",
                "property_value_161",
                "property_value_162",
                "property_value_163",
                "property_value_164",
                "property_value_165",
                "property_value_166",
                "property_value_167",
                "property_value_168",
                "property_value_169",
                "property_value_170",
                "property_value_171",
                "property_value_172",
                "property_value_173",
                "property_value_174",
                "property_value_175",
                "property_value_176",
                "property_value_177",
                "property_value_178",
                "property_value_179",
                "property_value_180",
                "property_value_181",
                "property_value_182",
                "property_value_183",
                "property_value_184",
                "property_value_185",
                "property_value_186",
                "property_value_187",
                "property_value_188",
                "property_value_189",
                "property_value_190",
                "property_value_191",
                "property_value_192",
                "property_value_193",
                "property_value_194",
                "property_value_195",
                "property_value_196",
                "property_value_197",
                "property_value_198",
                "property_value_199",
                "property_value_200",
                "property_value_201",
                "property_value_202",
                "property_value_203",
                "property_value_204",
                "property_value_205",
                "property_value_206",
                "property_value_207",
                "property_value_208",
                "property_value_209",
                "property_value_210",
                "property_value_211",
                "property_value_212",
                "property_value_213",
                "property_value_214",
                "property_value_215",
                "property_value_216",
                "property_value_217",
                "property_value_218",
                "property_value_219",
                "property_value_220",
                "property_value_221",
                "property_value_222",
                "property_value_223",
                "property_value_224",
                "property_value_225",
                "property_value_226",
                "property_value_227",
                "property_value_228",
                "property_value_229",
                "property_value_230",
                "property_value_231",
                "property_value_232",
                "property_value_233",
                "property_value_234",
                "property_value_235",
                "property_value_236",
                "property_value_237",
                "property_value_238",
                "property_value_239",
                "property_value_240",
                "property_value_241",
                "property_value_242",
                "property_value_243",
                "property_value_244",
                "property_value_245",
                "property_value_246",
                "property_value_247",
                "property_value_248",
                "property_value_249",
                "property_value_250"
            ]
        }
    },
    "type": "object",
    "memo": "fluid properties for the superheated region",
    "format": "FluidProperty"
}
```
