---
UID: NF:printerextension.IPrintSchemaParameterInitializer.get_Value
title: IPrintSchemaParameterInitializer::get_Value
description: The Value (get_Value) property gets the current value of the IPrintSchemaParameterInitializer object.
old-location: print\iprintschemaparameterinitializer_getvalue.htm
tech.root: print
ms.assetid: CDBAB58C-F051-4047-A538-5504F0E28EC7
ms.date: 04/20/2018
ms.keywords: IPrintSchemaParameterInitializer interface [Print Devices],Value property, IPrintSchemaParameterInitializer,get_Value, IPrintSchemaParameterInitializer.Value, IPrintSchemaParameterInitializer.get_Value, IPrintSchemaParameterInitializer::Value, IPrintSchemaParameterInitializer::get_Value, Value property [Print Devices], Value property [Print Devices],IPrintSchemaParameterInitializer interface, get_Value, print.iprintschemaparameterinitializer_getvalue, printerextension/IPrintSchemaParameterInitializer::Value, printerextension/IPrintSchemaParameterInitializer::get_Value
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
-	IPrintSchemaParameterInitializer.get_Value
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaParameterInitializer::get_Value


## -description


The <b>Value</b> (get_Value) property gets the current value of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn454557">IPrintSchemaParameterInitializer</a> object.

 In PrintTicket XML, that’s the value of the &lt;psf:Value&gt; child element for the &lt;psf:ParameterInit&gt; element.

This property is read-only.


## -parameters


## -remarks



The <b>Value</b> (get_Value) property returns the current value of the <b>IPrintSchemaParameterInitializer</b> object in the form of a Variant variable. Here's how the value and type are stored in the Variant for the different parameter data types:

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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn454557">IPrintSchemaParameterInitializer</a>
 

 

