---
UID: NF:portabledevicetypes.IPortableDevicePropVariantCollection.GetCount
title: IPortableDevicePropVariantCollection::GetCount (portabledevicetypes.h)
description: Retrieves the number of items in this collection.
old-location: wpddk\iportabledevicepropvariantcollection_getcount.htm
tech.root: wpd_dk
ms.assetid: a9eecbc4-c461-4c13-99e0-3132bd0f6b9c
ms.date: 02/15/2018
ms.keywords: GetCount, GetCount method, GetCount method,IPortableDevicePropVariantCollection interface, IPortableDevicePropVariantCollection interface,GetCount method, IPortableDevicePropVariantCollection.GetCount, IPortableDevicePropVariantCollection::GetCount, IPortableDevicePropVariantCollectionGetCount, portabledevicetypes/IPortableDevicePropVariantCollection::GetCount, wpddk.iportabledevicepropvariantcollection_getcount
f1_keywords:
 - "portabledevicetypes/IPortableDevicePropVariantCollection.GetCount"
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
- IPortableDevicePropVariantCollection.GetCount
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDevicePropVariantCollection::GetCount


## -description



Retrieves the number of items in this collection.




## -parameters




### -param pcElems [in]

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicepropvariantcollection">IPortableDevicePropVariantCollection Interface</a>
 

 

