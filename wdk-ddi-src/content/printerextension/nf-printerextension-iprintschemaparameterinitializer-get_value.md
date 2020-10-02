---
UID: NF:printerextension.IPrintSchemaParameterInitializer.get_Value
title: IPrintSchemaParameterInitializer::get_Value (printerextension.h)
description: The Value (get_Value) property gets the current value of the IPrintSchemaParameterInitializer object.
old-location: print\iprintschemaparameterinitializer_getvalue.htm
tech.root: print
ms.assetid: CDBAB58C-F051-4047-A538-5504F0E28EC7
ms.date: 10/01/2020
keywords: ["IPrintSchemaParameterInitializer::get_Value"]
ms.keywords: IPrintSchemaParameterInitializer interface [Print Devices],Value property, IPrintSchemaParameterInitializer,get_Value, IPrintSchemaParameterInitializer.Value, IPrintSchemaParameterInitializer.get_Value, IPrintSchemaParameterInitializer::Value, IPrintSchemaParameterInitializer::get_Value, Value property [Print Devices], Value property [Print Devices],IPrintSchemaParameterInitializer interface, get_Value, print.iprintschemaparameterinitializer_getvalue, printerextension/IPrintSchemaParameterInitializer::Value, printerextension/IPrintSchemaParameterInitializer::get_Value
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintSchemaParameterInitializer::get_Value
 - printerextension/IPrintSchemaParameterInitializer::get_Value
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaParameterInitializer.Value
 - IPrintSchemaParameterInitializer.get_Value
---

# IPrintSchemaParameterInitializer::get_Value

## -description

The **Value** (get_Value) property gets the current value of the [IPrintSchemaParameterInitializer](nn-printerextension-iprintschemaparameterinitializer.md) object.

 In PrintTicket XML, that is the value of the **psf:Value** child element for the **psf:ParameterInit** element.

This property is read-only.

## -parameters

## -remarks

The **Value** (get_Value) property returns the current value of the **IPrintSchemaParameterInitializer** object in the form of a Variant variable. Here's how the value and type are stored in the Variant for the different parameter data types:

| Parameter DataType | Variant type | Variant value |
|--|--|--|
| PrintSchemaParameterDataType_Integer | V_VT(pVar) is VT_I4 | V_I4(pVar) |
| PrintSchemaParameterDataType_NumericString | V_VT(pVar) is VT_BSTR | V_BSTR(pVar) |
| PrintSchemaParameterDataType_String | V_VT(pVar) is VT_BSTR | V_BSTR(pVar) |

## -see-also

[IPrintSchemaParameterInitializer](nn-printerextension-iprintschemaparameterinitializer.md)
