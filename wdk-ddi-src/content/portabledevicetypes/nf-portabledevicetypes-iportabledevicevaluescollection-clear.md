---
UID: NF:portabledevicetypes.IPortableDeviceValuesCollection.Clear
title: IPortableDeviceValuesCollection::Clear (portabledevicetypes.h)
description: Releases all items from the collection.
old-location: wpddk\iportabledevicevaluescollection_clear.htm
tech.root: wpd_dk
ms.assetid: 510458d4-1b3a-4aea-ae52-ad32db6d8db4
ms.date: 02/15/2018
ms.keywords: Clear, Clear method, Clear method,IPortableDeviceValuesCollection interface, IPortableDeviceValuesCollection interface,Clear method, IPortableDeviceValuesCollection.Clear, IPortableDeviceValuesCollection::Clear, IPortableDeviceValuesCollectionClear, portabledevicetypes/IPortableDeviceValuesCollection::Clear, wpddk.iportabledevicevaluescollection_clear
ms.topic: method
f1_keywords:
 - "portabledevicetypes/IPortableDeviceValuesCollection.Clear"
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
- IPortableDeviceValuesCollection.Clear
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValuesCollection::Clear


## -description



Releases all items from the collection.




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



The method releases all memory that is allocated for the items in the collection.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicevaluescollection">IPortableDeviceValuesCollection Interface</a>
 

 

