---
UID: NN:portabledevicetypes.IPortableDevicePropVariantCollection
title: IPortableDevicePropVariantCollection (portabledevicetypes.h)
description: Holds a collection of PROPVARIANT values of the same VARTYPE.
old-location: wpddk\iportabledevicepropvariantcollection.htm
tech.root: wpd_dk
ms.assetid: e097ee45-d8df-406d-80ca-93f128c19416
ms.date: 02/15/2018
ms.keywords: IPortableDevicePropVariantCollection, IPortableDevicePropVariantCollection interface, IPortableDevicePropVariantCollection interface,described, IPortableDevicePropVariantCollectionInterface, portabledevicetypes/IPortableDevicePropVariantCollection, wpddk.iportabledevicepropvariantcollection
ms.topic: interface
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
- IPortableDevicePropVariantCollection
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDevicePropVariantCollection interface


## -description



Holds a collection of <b>PROPVARIANT</b> values of the same <b>VARTYPE</b>. The <b>VARTYPE</b> of the first item that is added to the collection determines the VARTYPE of the collection. An attempt to add an item of a different <b>VARTYPE</b> may fail if the <b>PROPVARIANT</b> value cannot be changed to the collection's current <b>VARTYPE</b>. To change the <b>VARTYPE</b> of the collection manually, call <b>ChangeType</b>.

This interface can be retrieved from a method or, if a new object is required, call CoCreate with CLSID_PortableDevicePropVariantCollection.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortableDevicePropVariantCollection</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortableDevicePropVariantCollection</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPortableDevicePropVariantCollection</b> interface has these methods.
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
Adds an item to the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicepropvariantcollection-changetype">ChangeType</a>
</td>
<td align="left" width="63%">
Converts all items in the collection to the specified type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Clear</a>
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
Retrieves an item from the collection by index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getcount">GetCount</a>
</td>
<td align="left" width="63%">
Retrieves the number of items in this collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a>
</td>
<td align="left" width="63%">
Retrieves the data type of the items in the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicepropvariantcollection-removeat">RemoveAt</a>
</td>
<td align="left" width="63%">
Removes the element stored at the location specified by the given index.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597553(v=vs.85)">Collection Interfaces</a>
 

 

