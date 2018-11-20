---
UID: NF:portabledevicetypes.IPortableDeviceValuesCollection.GetCount
title: IPortableDeviceValuesCollection::GetCount
author: windows-driver-content
description: Retrieves the number of items in the collection.
old-location: wpddk\iportabledevicevaluescollection_getcount.htm
tech.root: wpd_dk
ms.assetid: e94a1a6a-8c2d-45ee-96cf-08566373e8f5
ms.date: 02/15/2018
ms.keywords: GetCount, GetCount method, GetCount method,IPortableDeviceValuesCollection interface, IPortableDeviceValuesCollection interface,GetCount method, IPortableDeviceValuesCollection.GetCount, IPortableDeviceValuesCollection::GetCount, IPortableDeviceValuesCollectionGetCount, portabledevicetypes/IPortableDeviceValuesCollection::GetCount, wpddk.iportabledevicevaluescollection_getcount
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
-	IPortableDeviceValuesCollection.GetCount
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValuesCollection::GetCount


## -description



Retrieves the number of items in the collection.




## -parameters




### -param pcElems [in]

Pointer to a <b>DWORD</b> that contains the number of <b>IPortableDeviceValues</b> interfaces in the collection.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A required pointer argument was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/f6115732-00d2-48db-9087-6e33a769ca4b">IPortableDeviceValuesCollection Interface</a>
 

 

