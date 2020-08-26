---
UID: NF:portabledevicetypes.IPortableDeviceKeyCollection.Add
title: IPortableDeviceKeyCollection::Add (portabledevicetypes.h)
description: Adds a property key to the collection.
old-location: wpddk\iportabledevicekeycollection_add.htm
tech.root: wpd_dk
ms.assetid: 632888bc-4a2a-4554-b6c6-8ca54f021342
ms.date: 02/15/2018
keywords: ["IPortableDeviceKeyCollection::Add"]
ms.keywords: Add, Add method, Add method,IPortableDeviceKeyCollection interface, IPortableDeviceKeyCollection interface,Add method, IPortableDeviceKeyCollection.Add, IPortableDeviceKeyCollection::Add, IPortableDeviceKeyCollectionAdd, portabledevicetypes/IPortableDeviceKeyCollection::Add, wpddk.iportabledevicekeycollection_add
f1_keywords:
 - "portabledevicetypes/IPortableDeviceKeyCollection.Add"
 - "IPortableDeviceKeyCollection.Add"
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
- IPortableDeviceKeyCollection.Add
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceKeyCollection::Add


## -description



Adds a property key to the collection.




## -parameters




### -param Key 
[in]
A <b>REFPROPERTYKEY</b> to add to the collection. This method copies the key to the collection.


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
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
There is not enough memory available to add the key to the collection.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicekeycollection">IPortableDeviceKeyCollection Interface</a>
 

 

