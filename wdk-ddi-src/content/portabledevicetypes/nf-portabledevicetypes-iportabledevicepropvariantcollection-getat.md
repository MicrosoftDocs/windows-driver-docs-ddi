---
UID: NF:portabledevicetypes.IPortableDevicePropVariantCollection.GetAt
title: IPortableDevicePropVariantCollection::GetAt
author: windows-driver-content
description: Retrieves an item from the collection by a zero-based index.
old-location: wpddk\iportabledevicepropvariantcollection_getat.htm
tech.root: wpd_dk
ms.assetid: f42239b1-4f41-4b54-a29c-f5e5e2681a59
ms.date: 02/15/2018
ms.keywords: GetAt, GetAt method, GetAt method,IPortableDevicePropVariantCollection interface, IPortableDevicePropVariantCollection interface,GetAt method, IPortableDevicePropVariantCollection.GetAt, IPortableDevicePropVariantCollection::GetAt, IPortableDevicePropVariantCollectionGetAt, portabledevicetypes/IPortableDevicePropVariantCollection::GetAt, wpddk.iportabledevicepropvariantcollection_getat
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
-	IPortableDevicePropVariantCollection.GetAt
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDevicePropVariantCollection::GetAt


## -description



Retrieves an item from the collection by a zero-based index.




## -parameters




### -param dwIndex [in]

<b>DWORD</b> that contains the zero-based index of the item to retrieve.


### -param pValue [out]

Pointer to a <b>PROPVARIANT</b> structure. The caller is responsible for freeing this memory by calling <b>PropVariantClear</b>.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The zero-based index that was passed in was out of range.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/e097ee45-d8df-406d-80ca-93f128c19416">IPortableDevicePropVariantCollection Interface</a>
 

 

