---
UID: NE:printerextension.tagPrintSchemaParameterDataType
title: tagPrintSchemaParameterDataType (printerextension.h)
description: The PrintSchemaParameterDataType enumeration identifies the allowed data types for the Print Schema parameter.
old-location: print\tagprintschemaparameterdatatype.htm
tech.root: print
ms.assetid: 3276C273-C950-4DC9-B338-E6E7E30DEB77
ms.date: 04/20/2018
keywords: ["tagPrintSchemaParameterDataType enumeration"]
ms.keywords: PrintSchemaParameterDataType, PrintSchemaParameterDataType enumeration [Print Devices], PrintSchemaParameterDataType_Integer, PrintSchemaParameterDataType_NumericString, PrintSchemaParameterDataType_String, print.tagprintschemaparameterdatatype, printerextension/PrintSchemaParameterDataType, printerextension/PrintSchemaParameterDataType_Integer, printerextension/PrintSchemaParameterDataType_NumericString, printerextension/PrintSchemaParameterDataType_String, tagPrintSchemaParameterDataType
f1_keywords:
 - "printerextension/PrintSchemaParameterDataType"
 - "PrintSchemaParameterDataType"
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Printerextension.h
api_name:
- PrintSchemaParameterDataType
targetos: Windows
req.typenames: PrintSchemaParameterDataType
---

# tagPrintSchemaParameterDataType enumeration


## -description


The PrintSchemaParameterDataType enumeration identifies the allowed data types for the Print Schema parameter.


## -enum-fields




### -field PrintSchemaParameterDataType_Integer

Integer data type.
This maps to the Print Schema’s IntegerParamType parameters.


### -field PrintSchemaParameterDataType_NumericString

String data type with only numeric chars allowed.
This maps to the Print Schema’s StringParamType parameters, with UnitType = “numeric”.


### -field PrintSchemaParameterDataType_String

String data type with arbitrary chars allowed.
This maps to the Print Schema’s StringParamType parameters, with UnitType not equal to “numeric”.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaparameterdefinition-get_datatype">IPrintSchemaParameterDefinition::DataType</a>
 

 

