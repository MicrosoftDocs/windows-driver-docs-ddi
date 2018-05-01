---
UID: NF:printerextension.IPrintSchemaParameterInitializer.put_Value
title: IPrintSchemaParameterInitializer::put_Value
author: windows-driver-content
description: The Value (put_Value) property modifies the value of the IPrintSchemaParameterInitializer object.
old-location: print\iprintschemaparameterinitializer_putvalue.htm
old-project: print
ms.assetid: B0F003B4-D82D-4110-B53A-CDE45B75DC8C
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintSchemaParameterInitializer interface [Print Devices],Value property, IPrintSchemaParameterInitializer,put_Value, IPrintSchemaParameterInitializer.Value, IPrintSchemaParameterInitializer.put_Value, IPrintSchemaParameterInitializer::Value, IPrintSchemaParameterInitializer::put_Value, Value property [Print Devices], Value property [Print Devices],IPrintSchemaParameterInitializer interface, print.iprintschemaparameterinitializer_putvalue, printerextension/IPrintSchemaParameterInitializer::Value, printerextension/IPrintSchemaParameterInitializer::put_Value, put_Value
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaParameterInitializer.Value
-	IPrintSchemaParameterInitializer.put_Value
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaParameterInitializer::put_Value


## -description


The <b>Value</b> (put_Value) property modifies the value of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn454557">IPrintSchemaParameterInitializer</a> object. 

In PrintTicket XML, that’s the value of the &lt;psf:Value&gt; child element for the &lt;psf:ParameterInit&gt; element.

This property is write-only.


## -parameters


## -remarks



The <b>Value</b> (put_Value) property passes the new value as a Variant. Here's what the receiving function expects in the Variant type, and where the function will look for the new value, depending on the different parameter data types:

<table>
<tr>
<th>Parameter DataType</th>
<th>Variant type</th>
<th>Variant value</th>
</tr>
<tr>
<td>PrintSchemaParameterDataType_Integer</td>
<td>V_VT(pVar) is VT_I4</td>
<td>V_I4(pVar)</td>
</tr>
<tr>
<td>PrintSchemaParameterDataType_NumericString</td>
<td>V_VT(pVar) is VT_BSTR</td>
<td>V_BSTR(pVar)</td>
</tr>
<tr>
<td>PrintSchemaParameterDataType_String</td>
<td>V_VT(pVar) is VT_BSTR</td>
<td>V_BSTR(pVar)</td>
</tr>
</table>
 

If the input Variant type doesn’t match the parameter data type as shown in the preceding table, then the put_Value property call will return E_INVALIDARG.

In the case of the <b>PrintSchemaParameterDataType_NumericString</b>  parameter data type, the function will also validate that the V_BSTR(pVar) string only contains numeric characters. If the function finds any non-numeric characters, then the put_Value property call will return E_INVALIDARG.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn454557">IPrintSchemaParameterInitializer</a>
 

 

