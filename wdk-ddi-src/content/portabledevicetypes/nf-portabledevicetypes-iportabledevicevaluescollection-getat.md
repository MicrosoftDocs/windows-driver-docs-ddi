---
UID: NF:portabledevicetypes.IPortableDeviceValuesCollection.GetAt
title: IPortableDeviceValuesCollection::GetAt (portabledevicetypes.h)
description: Retrieves an item from the collection by a zero-based index.
old-location: wpddk\iportabledevicevaluescollection_getat.htm
tech.root: wpd_dk
ms.assetid: 772d6140-cd65-4fc7-b4d9-04d683d12e30
ms.date: 02/15/2018
keywords: ["IPortableDeviceValuesCollection::GetAt"]
ms.keywords: GetAt, GetAt method, GetAt method,IPortableDeviceValuesCollection interface, IPortableDeviceValuesCollection interface,GetAt method, IPortableDeviceValuesCollection.GetAt, IPortableDeviceValuesCollection::GetAt, IPortableDeviceValuesCollectionGetAt, portabledevicetypes/IPortableDeviceValuesCollection::GetAt, wpddk.iportabledevicevaluescollection_getat
f1_keywords:
 - "portabledevicetypes/IPortableDeviceValuesCollection.GetAt"
 - "IPortableDeviceValuesCollection.GetAt"
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
- IPortableDeviceValuesCollection.GetAt
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValuesCollection::GetAt


## -description



Retrieves an item from the collection by a zero-based index.




## -parameters




### -param dwIndex [in]

<b>DWORD</b> that specifies a zero-based index in the collection.


### -param ppValues [out]

Address of a variable that receives a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> interface from the collection. The caller is responsible for calling <b>Release</b> on this interface when done with it.


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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The zero-based index that was passed in was out of range.

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
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
The collection contains a <b>NULL</b> <b>IPortableDeviceValues</b> pointer.

</td>
</tr>
</table>
 




## -remarks



Any changes that are made to values in the retrieved interface will be made to the version stored in the collection.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevaluescollection">IPortableDeviceValuesCollection Interface</a>
 

 

