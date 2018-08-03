---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetIPortableDeviceKeyCollectionValue
title: IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue
author: windows-driver-content
description: Retrieves an IPortableDeviceKeyCollection value (type VT_UNKNOWN) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getiportabledevicekeycollectionvalue.htm
tech.root: wpd_dk
ms.assetid: 059e46f3-39d9-4d5e-9841-0ccb35ccb851
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetIPortableDeviceKeyCollectionValue, GetIPortableDeviceKeyCollectionValue method, GetIPortableDeviceKeyCollectionValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetIPortableDeviceKeyCollectionValue method, IPortableDeviceValues.GetIPortableDeviceKeyCollectionValue, IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue, IPortableDeviceValuesGetIPortableDeviceKeyCollectionValue, portabledevicetypes/IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue, wpddk.iportabledevicevalues_getiportabledevicekeycollectionvalue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	IPortableDeviceValues.GetIPortableDeviceKeyCollectionValue
product: Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue


## -description



Retrieves an <b>IPortableDeviceKeyCollection</b> value (type VT_UNKNOWN) that is specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param ppValue [out]

Pointer to the retrieved <a href="https://msdn.microsoft.com/library/windows/hardware/ff597583">IPortableDeviceKeyCollection</a> interface pointer. The caller is responsible for calling <b>Release</b> on the retrieved interface.


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
<dt><b>DISP_E_TYPEMISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not an <b>IPortableDeviceKeyCollection</b> interface.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not in the collection.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/b6a99ac0-3efd-4b58-bd90-3c7d172cd7ea">IPortableDeviceValues::SetIPortableDeviceKeyCollectionValue</a>
 

 

