---
UID: NF:portabledevicetypes.IPortableDeviceKeyCollection.GetAt
title: IPortableDeviceKeyCollection::GetAt (portabledevicetypes.h)
description: Retrieves a PROPERTYKEY from the collection by index.
old-location: wpddk\iportabledevicekeycollection_getat.htm
tech.root: wpd_dk
ms.assetid: fc74720e-0a39-4ef7-bb9a-e09a6445f0c3
ms.date: 02/15/2018
ms.keywords: GetAt, GetAt method, GetAt method,IPortableDeviceKeyCollection interface, IPortableDeviceKeyCollection interface,GetAt method, IPortableDeviceKeyCollection.GetAt, IPortableDeviceKeyCollection::GetAt, IPortableDeviceKeyCollectionGetAt, portabledevicetypes/IPortableDeviceKeyCollection::GetAt, wpddk.iportabledevicekeycollection_getat
f1_keywords:
 - "portabledevicetypes/IPortableDeviceKeyCollection.GetAt"
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
- IPortableDeviceKeyCollection.GetAt
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceKeyCollection::GetAt


## -description



Retrieves a <b>PROPERTYKEY</b> from the collection by index.




## -parameters




### -param dwIndex [in]

<b>DWORD</b> that contains the zero-based index of the key to be retrieved.


### -param pKey [out]

Pointer to a <b>PROPERTYKEY</b>.


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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The index passed in was out of range.

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicekeycollection">IPortableDeviceKeyCollection Interface</a>
 

 

