---
UID: NF:printerextension.IPrintSchemaParameterInitializer.put_Value
title: IPrintSchemaParameterInitializer::put_Value (printerextension.h)
description: The Value (put_Value) property modifies the value of the IPrintSchemaParameterInitializer object.
old-location: print\iprintschemaparameterinitializer_putvalue.htm
tech.root: print
ms.date: 10/01/2020
keywords: ["IPrintSchemaParameterInitializer::put_Value"]
ms.keywords: IPrintSchemaParameterInitializer interface [Print Devices],Value property, IPrintSchemaParameterInitializer,put_Value, IPrintSchemaParameterInitializer.Value, IPrintSchemaParameterInitializer.put_Value, IPrintSchemaParameterInitializer::Value, IPrintSchemaParameterInitializer::put_Value, Value property [Print Devices], Value property [Print Devices],IPrintSchemaParameterInitializer interface, print.iprintschemaparameterinitializer_putvalue, printerextension/IPrintSchemaParameterInitializer::Value, printerextension/IPrintSchemaParameterInitializer::put_Value, put_Value
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
 - IPrintSchemaParameterInitializer::put_Value
 - printerextension/IPrintSchemaParameterInitializer::put_Value
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaParameterInitializer.Value
 - IPrintSchemaParameterInitializer.put_Value
---

# IPrintSchemaParameterInitializer::put_Value

## -description

The **Value** (put_Value) property modifies the value of the [IPrintSchemaParameterInitializer](nn-printerextension-iprintschemaparameterinitializer.md) object.

In PrintTicket XML, that's the value of the **psf:Value** child element for the **psf:ParameterInit** element.

This property is write-only.

## -parameters

## -remarks

The **Value** (put_Value) property passes the new value as a Variant. Here is what the receiving function expects in the Variant type, and where the function will look for the new value, depending on the different parameter data types:

| Parameter DataType | Variant type | Variant value |
|--|--|--|
| PrintSchemaParameterDataType_Integer | V_VT(pVar) is VT_I4 | V_I4(pVar) |
| PrintSchemaParameterDataType_NumericString | V_VT(pVar) is VT_BSTR | V_BSTR(pVar) |
| PrintSchemaParameterDataType_String | V_VT(pVar) is VT_BSTR | V_BSTR(pVar) |

If the input **Variant** type does not match the parameter data type as shown in the preceding table, then the put_Value property call will return **E_INVALIDARG**.

In the case of the **PrintSchemaParameterDataType_NumericString** parameter data type, the function will also validate that the V_BSTR(pVar) string only contains numeric characters. If the function finds any non-numeric characters, then the put_Value property call will return **E_INVALIDARG**.

## -see-also

[IPrintSchemaParameterInitializer](nn-printerextension-iprintschemaparameterinitializer.md)
