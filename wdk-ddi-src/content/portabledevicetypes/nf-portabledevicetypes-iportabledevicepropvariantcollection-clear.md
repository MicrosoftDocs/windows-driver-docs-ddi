---
UID: NF:portabledevicetypes.IPortableDevicePropVariantCollection.Clear
title: IPortableDevicePropVariantCollection::Clear (portabledevicetypes.h)
description: Removes or frees all items in the collection. The collection is considered empty after calling this method.
old-location: wpddk\iportabledevicepropvariantcollection_clear.htm
tech.root: wpd_dk
ms.assetid: 5d663753-963a-474e-ab35-25a2cefd8b5e
ms.date: 02/15/2018
ms.keywords: Clear, Clear method, Clear method,IPortableDevicePropVariantCollection interface, IPortableDevicePropVariantCollection interface,Clear method, IPortableDevicePropVariantCollection.Clear, IPortableDevicePropVariantCollection::Clear, IPortableDevicePropVariantCollectionClear, portabledevicetypes/IPortableDevicePropVariantCollection::Clear, wpddk.iportabledevicepropvariantcollection_clear
ms.topic: method
f1_keywords:
 - "portabledevicetypes/IPortableDevicePropVariantCollection.Clear"
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
- IPortableDevicePropVariantCollection.Clear
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDevicePropVariantCollection::Clear


## -description



Removes or frees all items in the collection. The collection is considered empty after calling this method.




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



After calling <b>Clear</b> the collection is considered type-less, meaning that the <b>VARTYPE</b> it was previously set to is no longer restricting <b>Add</b> operations. A call to <b>Add</b> after calling <b>Clear</b> is considered the "first" <b>Add</b> for this collection.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicepropvariantcollection">IPortableDevicePropVariantCollection Interface</a>
 

 

