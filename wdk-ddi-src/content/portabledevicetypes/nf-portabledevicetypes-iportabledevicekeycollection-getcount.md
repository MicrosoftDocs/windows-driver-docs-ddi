---
UID: NF:portabledevicetypes.IPortableDeviceKeyCollection.GetCount
title: IPortableDeviceKeyCollection::GetCount (portabledevicetypes.h)
description: Retrieves the number of keys in this collection.
old-location: wpddk\iportabledevicekeycollection_getcount.htm
tech.root: wpd_dk
ms.assetid: b0cc6f5b-04ca-40ca-ad30-466859c5aaa6
ms.date: 02/15/2018
ms.keywords: GetCount, GetCount method, GetCount method,IPortableDeviceKeyCollection interface, IPortableDeviceKeyCollection interface,GetCount method, IPortableDeviceKeyCollection.GetCount, IPortableDeviceKeyCollection::GetCount, IPortableDeviceKeyCollectionGetCount, portabledevicetypes/IPortableDeviceKeyCollection::GetCount, wpddk.iportabledevicekeycollection_getcount
ms.topic: method
f1_keywords:
 - "portabledevicetypes/IPortableDeviceKeyCollection.GetCount"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- PortableDeviceTypes.h
api_name:
- IPortableDeviceKeyCollection.GetCount
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceKeyCollection::GetCount


## -description



Retrieves the number of keys in this collection.




## -parameters




### -param pcElems [in]

Pointer to a <b>DWORD</b> that contains the number of keys in the collection.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicekeycollection">IPortableDeviceKeyCollection Interface</a>
 

 

