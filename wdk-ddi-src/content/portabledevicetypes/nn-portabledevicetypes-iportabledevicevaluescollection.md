---
UID: NN:portabledevicetypes.IPortableDeviceValuesCollection
title: IPortableDeviceValuesCollection
author: windows-driver-content
description: Holds a collection of indexed IPortableDeviceValues interfaces. This interface can be retrieved from a method, or if a new object is required, call CoCreate with CLSID_PortableDeviceValuesCollection.
old-location: wpddk\iportabledevicevaluescollection.htm
tech.root: wpd_dk
ms.assetid: f6115732-00d2-48db-9087-6e33a769ca4b
ms.date: 02/15/2018
ms.keywords: IPortableDeviceValuesCollection, IPortableDeviceValuesCollection interface, IPortableDeviceValuesCollection interface,described, IPortableDeviceValuesCollectionInterface, portabledevicetypes/IPortableDeviceValuesCollection, wpddk.iportabledevicevaluescollection
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	PortableDeviceTypes.h
api_name:
-	IPortableDeviceValuesCollection
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValuesCollection interface


## -description



Holds a collection of indexed <b>IPortableDeviceValues</b> interfaces. This interface can be retrieved from a method, or if a new object is required, call <b>CoCreate</b> with <b>CLSID_PortableDeviceValuesCollection</b>.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortableDeviceValuesCollection</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPortableDeviceValuesCollection</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPortableDeviceValuesCollection</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn938485">Add</a>
</td>
<td align="left" width="63%">
Adds an item to the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406339">Clear</a>
</td>
<td align="left" width="63%">
Deletes all items from the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406567">GetAt</a>
</td>
<td align="left" width="63%">
Retrieves an item from the collection by a zero-based index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597609">GetCount</a>
</td>
<td align="left" width="63%">
Retrieves the number of items in the collection.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff597553">Collection Interfaces</a>
 

 

