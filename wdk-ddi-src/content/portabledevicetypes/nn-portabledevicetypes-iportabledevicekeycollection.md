---
UID: NN:portabledevicetypes.IPortableDeviceKeyCollection
title: IPortableDeviceKeyCollection (portabledevicetypes.h)
description: Holds a collection of PROPERTYKEY values. This interface can be retrieved from a method or, if a new object is required, call CoCreate with CLSID_PortableDeviceKeyCollection.
old-location: wpddk\iportabledevicekeycollection.htm
tech.root: wpd_dk
ms.assetid: 50ce4946-18a7-4b63-ba5a-c5684dd0b79c
ms.date: 02/15/2018
ms.keywords: IPortableDeviceKeyCollection, IPortableDeviceKeyCollection interface, IPortableDeviceKeyCollection interface,described, IPortableDeviceKeyCollectionInterface, portabledevicetypes/IPortableDeviceKeyCollection, wpddk.iportabledevicekeycollection
ms.topic: interface
f1_keywords:
 - "portabledevicetypes/IPortableDeviceKeyCollection"
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
- IPortableDeviceKeyCollection
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceKeyCollection interface


## -description



Holds a collection of <b>PROPERTYKEY</b> values. This interface can be retrieved from a method or, if a new object is required, call <b>CoCreate</b> with <b>CLSID_PortableDeviceKeyCollection</b>.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortableDeviceKeyCollection</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortableDeviceKeyCollection</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPortableDeviceKeyCollection</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/test/wpt/add">Add</a>
</td>
<td align="left" width="63%">
Adds a property key to the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Clear</a>
</td>
<td align="left" width="63%">
Deletes all items from the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/radio/hh406567(v=vs.85)">GetAt</a>
</td>
<td align="left" width="63%">
Retrieves a <b>PROPERTYKEY</b> from the collection by index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getcount">GetCount</a>
</td>
<td align="left" width="63%">
Retrieves the number of keys in this collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicepropvariantcollection-removeat">RemoveAt</a>
</td>
<td align="left" width="63%">
Removes the element stored at the location specified by the given index.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597553(v=vs.85)">Collection Interfaces</a>
 

 

