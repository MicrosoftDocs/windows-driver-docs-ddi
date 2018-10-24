---
UID: NF:portabledevicetypes.IPortableDeviceValues.Clear
title: IPortableDeviceValues::Clear
author: windows-driver-content
description: Deletes all items from the collection.
old-location: wpddk\iportabledevicevalues_clear.htm
tech.root: wpd_dk
ms.assetid: 0978d4cd-3ed1-478b-b5ea-8fe21811526c
ms.date: 02/15/2018
ms.keywords: Clear, Clear method, Clear method,IPortableDeviceValues interface, IPortableDeviceValues interface,Clear method, IPortableDeviceValues.Clear, IPortableDeviceValues::Clear, IPortableDeviceValuesClear, portabledevicetypes/IPortableDeviceValues::Clear, wpddk.iportabledevicevalues_clear
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
-	IPortableDeviceValues.Clear
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::Clear


## -description



Deletes all items from the collection.




## -parameters






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



This method frees the memory for all dynamically allocated items in the collection. For interfaces, it calls <b>Release</b>.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>
 

 

