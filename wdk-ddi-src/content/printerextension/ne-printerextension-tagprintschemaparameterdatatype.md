---
UID: NE:printerextension.tagPrintSchemaParameterDataType
title: tagPrintSchemaParameterDataType
author: windows-driver-content
description: The PrintSchemaParameterDataType enumeration identifies the allowed data types for the Print Schema parameter.
old-location: print\tagprintschemaparameterdatatype.htm
old-project: print
ms.assetid: 3276C273-C950-4DC9-B338-E6E7E30DEB77
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: tagPrintSchemaParameterDataType, PrintSchemaParameterDataType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PrintSchemaParameterDataType
req.alt-loc: Printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: PrintSchemaParameterDataType
req.product: Windows 10 or later.
---

# tagPrintSchemaParameterDataType enumeration



## -description
The PrintSchemaParameterDataType enumeration identifies the allowed data types for the Print Schema parameter.



## -syntax

````
typedef enum tagPrintSchemaParameterDataType { 
  PrintSchemaParameterDataType_Integer        = 0,
  PrintSchemaParameterDataType_NumericString,
  PrintSchemaParameterDataType_String
} PrintSchemaParameterDataType;
````


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


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/82CC79A8-0281-4100-B3FB-1FFFB2454B8D">IPrintSchemaParameterDefinition::DataType</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PrintSchemaParameterDataType enumeration%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

