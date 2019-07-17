---
UID: NF:portabledevicetypes.IPortableDeviceValuesCollection.Add
title: IPortableDeviceValuesCollection::Add (portabledevicetypes.h)
description: Adds an item to the collection.
old-location: wpddk\iportabledevicevaluescollection_add.htm
tech.root: wpd_dk
ms.assetid: 1e95fb27-b6a6-41da-8765-e17bac4f35a1
ms.date: 02/15/2018
ms.keywords: Add, Add method, Add method,IPortableDeviceValuesCollection interface, IPortableDeviceValuesCollection interface,Add method, IPortableDeviceValuesCollection.Add, IPortableDeviceValuesCollection::Add, IPortableDeviceValuesCollectionAdd, portabledevicetypes/IPortableDeviceValuesCollection::Add, wpddk.iportabledevicevaluescollection_add
ms.topic: method
f1_keywords:
 - "portabledevicetypes/IPortableDeviceValuesCollection.Add"
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
- IPortableDeviceValuesCollection.Add
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValuesCollection::Add


## -description



Adds an item to the collection.




## -parameters




### -param pValues [in]

Pointer to an <b>IPortableDeviceValues</b> interface to add to the collection. The interface is not actually copied, but <b>AddRef</b> is called on it.


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
There is not enough memory available to add the value to the collection.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicevaluescollection">IPortableDeviceValuesCollection Interface</a>
 

 

