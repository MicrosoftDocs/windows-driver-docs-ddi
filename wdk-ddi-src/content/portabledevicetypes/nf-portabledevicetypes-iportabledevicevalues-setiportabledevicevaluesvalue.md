---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetIPortableDeviceValuesValue
title: IPortableDeviceValues::SetIPortableDeviceValuesValue
author: windows-driver-content
description: Adds a new IPortableDeviceValues value (type VT_UNKNOWN) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setiportabledevicevaluesvalue.htm
tech.root: wpd_dk
ms.assetid: 2ab54174-9e1b-4b52-894c-489d67b7f1be
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IPortableDeviceValues interface,SetIPortableDeviceValuesValue method, IPortableDeviceValues.SetIPortableDeviceValuesValue, IPortableDeviceValues::SetIPortableDeviceValuesValue, IPortableDeviceValuesSetIPortableDeviceValuesValue, SetIPortableDeviceValuesValue, SetIPortableDeviceValuesValue method, SetIPortableDeviceValuesValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetIPortableDeviceValuesValue, wpddk.iportabledevicevalues_setiportabledevicevaluesvalue
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
-	IPortableDeviceValues.SetIPortableDeviceValuesValue
product: Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::SetIPortableDeviceValuesValue


## -description



Adds a new <b>IPortableDeviceValues</b> value (type VT_UNKNOWN) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param pValue [in]

Pointer to an <b>IPortableDeviceValues</b> interface that specifies the new value. The SDK copies a reference to the submitted interface and calls <b>AddRef</b> on it.


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



If an existing value has the same key that is specified by the <i>key</i> parameter, it overwrites the existing value without any warning. The existing key memory is released appropriately.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/f0ec918d-57a2-40a4-b7ca-878484fc46ac">IPortableDeviceValues::GetIPortableDeviceValuesValue</a>
 

 

