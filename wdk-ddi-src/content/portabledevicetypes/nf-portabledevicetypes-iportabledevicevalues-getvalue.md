---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetValue
title: IPortableDeviceValues::GetValue
author: windows-driver-content
description: The GetValue interface retrieves a PROPVARIANT value that is specified by a key.
old-location: wpddk\iportabledevicevalues_getvalue.htm
tech.root: wpd_dk
ms.assetid: 3c078259-98e8-4874-aa5e-060f0da1a246
ms.date: 02/15/2018
ms.keywords: GetValue, GetValue method, GetValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetValue method, IPortableDeviceValues.GetValue, IPortableDeviceValues::GetValue, IPortableDeviceValuesGetValue, portabledevicetypes/IPortableDeviceValues::GetValue, wpddk.iportabledevicevalues_getvalue
ms.topic: method
req.header: portabledevicetypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	PortableDeviceTypes.h
api_name:
-	IPortableDeviceValues.GetValue
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::GetValue


## -description



The GetValue interface retrieves a <b>PROPVARIANT</b> value that is specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param pValue [out]

A pointer to the retrieved <b>PROPVARIANT</b> value. The caller must release the memory by calling <b>PropVariantClear</b> when the call is complete.


## -returns



The method returns an <b>HRESULT</b>. Possible return values are shown in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
The property that is specified by <i>key</i> is not in the collection.

</td>
</tr>
</table>
 




## -remarks



This method can be used to retrieve a value of any type from the collection. However, if you know the value type in advance, use one of the specialized retrieval methods of this interface for additional type checking.

When the VARTYPE for <i>pValue</i> is VT_VECTOR or VT_UI1, retrieving a <b>NULL</b> or zero-sized buffer is not supported. For example, neither  pValue.caub.pElems = <b>NULL</b> nor pValue.caub.cElems = 0 are allowed.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/aaa6cfd7-ac55-49b5-b077-98e42367ce0e">IPortableDeviceValues::RemoveValue</a>



<a href="https://msdn.microsoft.com/43670b44-7554-4cef-9b8d-aa66c16edf13">IPortableDeviceValues::SetValue</a>
 

 

