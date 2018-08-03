---
UID: NF:portabledevicetypes.IPortableDeviceValues.RemoveValue
title: IPortableDeviceValues::RemoveValue
author: windows-driver-content
description: The RemoveValue method removes an item from the collection.
old-location: wpddk\iportabledevicevalues_removevalue.htm
tech.root: wpd_dk
ms.assetid: aaa6cfd7-ac55-49b5-b077-98e42367ce0e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IPortableDeviceValues interface,RemoveValue method, IPortableDeviceValues.RemoveValue, IPortableDeviceValues::RemoveValue, IPortableDeviceValuesRemoveValue, RemoveValue, RemoveValue method, RemoveValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::RemoveValue, wpddk.iportabledevicevalues_removevalue
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IPortableDeviceValues.RemoveValue
product: Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::RemoveValue


## -description



The <b>RemoveValue</b> method removes an item from the collection.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to remove.


## -returns



The method returns an <b>HRESULT</b>. Possible values include, but are not limited to, those in the following table.

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
</table>
 




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/3c078259-98e8-4874-aa5e-060f0da1a246">IPortableDeviceValues::GetValue</a>



<a href="https://msdn.microsoft.com/43670b44-7554-4cef-9b8d-aa66c16edf13">IPortableDeviceValues::SetValue</a>
 

 

