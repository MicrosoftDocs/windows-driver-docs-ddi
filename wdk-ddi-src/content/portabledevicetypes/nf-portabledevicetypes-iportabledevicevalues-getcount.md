---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetCount
title: IPortableDeviceValues::GetCount
description: Retrieves the number of items in the collection.
old-location: wpddk\iportabledevicevalues_getcount.htm
tech.root: wpd_dk
ms.assetid: 40bf1a26-bba9-4484-b92a-2c2680f66cb5
ms.date: 02/15/2018
ms.keywords: GetCount, GetCount method, GetCount method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetCount method, IPortableDeviceValues.GetCount, IPortableDeviceValues::GetCount, IPortableDeviceValuesGetCount, portabledevicetypes/IPortableDeviceValues::GetCount, wpddk.iportabledevicevalues_getcount
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
-	IPortableDeviceValues.GetCount
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::GetCount


## -description



Retrieves the number of items in the collection.




## -parameters




### -param pcelt [in]

Pointer to a <b>DWORD</b> that contains the number of items in the collection.


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
 

 

