---
UID: NF:portabledevicetypes.IPortableDevicePropVariantCollection.ChangeType
title: IPortableDevicePropVariantCollection::ChangeType (portabledevicetypes.h)
description: Converts all items in the collection to the specified VARTYPE.
old-location: wpddk\iportabledevicepropvariantcollection_changetype.htm
tech.root: wpd_dk
ms.assetid: d8e6091e-92ca-49c7-8ee6-502e1567b609
ms.date: 02/15/2018
keywords: ["IPortableDevicePropVariantCollection::ChangeType"]
ms.keywords: ChangeType, ChangeType method, ChangeType method,IPortableDevicePropVariantCollection interface, IPortableDevicePropVariantCollection interface,ChangeType method, IPortableDevicePropVariantCollection.ChangeType, IPortableDevicePropVariantCollection::ChangeType, IPortableDevicePropVariantCollectionChangeType, portabledevicetypes/IPortableDevicePropVariantCollection::ChangeType, wpddk.iportabledevicepropvariantcollection_changetype
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
 - IPortableDevicePropVariantCollection::ChangeType
 - portabledevicetypes/IPortableDevicePropVariantCollection::ChangeType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDevicePropVariantCollection.ChangeType
---

# IPortableDevicePropVariantCollection::ChangeType


## -description

Converts all items in the collection to the specified <b>VARTYPE</b>.

## -parameters

### -param vt 

[in]
Specifies the <b>VARTYPE</b> to which you want to convert all items in the collection.

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

If this method fails, the collection may be left in an intermediate state, with some members converted and some not converted.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicepropvariantcollection">IPortableDevicePropVariantCollection Interface</a>

