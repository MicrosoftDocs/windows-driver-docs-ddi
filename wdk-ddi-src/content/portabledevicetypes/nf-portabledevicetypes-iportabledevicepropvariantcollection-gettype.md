---
UID: NF:portabledevicetypes.IPortableDevicePropVariantCollection.GetType
title: IPortableDevicePropVariantCollection::GetType (portabledevicetypes.h)
description: Retrieves the data type of the items in the collection.
old-location: wpddk\iportabledevicepropvariantcollection_gettype.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["IPortableDevicePropVariantCollection::GetType"]
ms.keywords: GetType, GetType method, GetType method,IPortableDevicePropVariantCollection interface, IPortableDevicePropVariantCollection interface,GetType method, IPortableDevicePropVariantCollection.GetType, IPortableDevicePropVariantCollection::GetType, IPortableDevicePropVariantCollectionGetType, portabledevicetypes/IPortableDevicePropVariantCollection::GetType, wpddk.iportabledevicepropvariantcollection_gettype
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - IPortableDevicePropVariantCollection::GetType
 - portabledevicetypes/IPortableDevicePropVariantCollection::GetType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDevicePropVariantCollection::GetType
---

# IPortableDevicePropVariantCollection::GetType


## -description

Retrieves the data type of the items in the collection.

## -parameters

### -param pvt 

[out]
A Platform SDK <b>VARTYPE</b> enumeration value that indicates the data type of all the items in the collection.

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

All items that are stored in an <b>IPortableDevicePropVariantCollection</b> are the same type.

## -see-also

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicepropvariantcollection">IPortableDevicePropVariantCollection Interface</a>

