---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_RangeMax
title: IPrintSchemaParameterDefinition::get_RangeMax (printerextension.h)
description: The RangeMax property gets the maximum value of the allowed data range.
old-location: print\_iprintschemaparameterdefinition_rangemax.htm
tech.root: print
ms.assetid: 516FADF0-3786-4C41-B38D-4A742AD68719
ms.date: 04/20/2018
ms.keywords: IPrintSchemaParameterDefinition interface [Print Devices],RangeMax property, IPrintSchemaParameterDefinition.RangeMax, IPrintSchemaParameterDefinition.get_RangeMax, IPrintSchemaParameterDefinition::RangeMax, IPrintSchemaParameterDefinition::get_RangeMax, RangeMax property [Print Devices], RangeMax property [Print Devices],IPrintSchemaParameterDefinition interface, get_RangeMax, print._iprintschemaparameterdefinition_rangemax, printerextension/IPrintSchemaParameterDefinition::RangeMax, printerextension/IPrintSchemaParameterDefinition::get_RangeMax
ms.topic: method
f1_keywords:
 - "printerextension/IPrintSchemaParameterDefinition.RangeMax"
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
- COM
api_location:
- Printerextension.h
api_name:
- IPrintSchemaParameterDefinition.RangeMax
- IPrintSchemaParameterDefinition.get_RangeMax
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaParameterDefinition::get_RangeMax


## -description


The <b>RangeMax</b> property gets the maximum value of the allowed data range.

This property is read-only.


## -parameters


## -remarks



For the <b>PrintSchemaParameterDataType_Integer</b> data type, the value returned by <b>RangeMax</b> maps to the <psf:MaxValue> property value of the Print Schema parameter definition. This maximum value shows the maximum integer value that the driver supports.

For the <b>PrintSchemaParameterDataType_NumericString</b> and <b>PrintSchemaParameterDataType_String</b>  data types, this maps to the <psf:MaxLength> property value of the Print Schema parameter definition. This maximum value  shows the maximum length of string that the driver supports.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschemaparameterdefinition">IPrintSchemaParameterDefinition</a>
 

 

