---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetUnsignedIntegerValue
title: IPortableDeviceValues::SetUnsignedIntegerValue
author: windows-driver-content
description: Adds a new ULONG value (type VT_UI4) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setunsignedintegervalue.htm
tech.root: wpd_dk
ms.assetid: a442a94a-2086-4b09-a795-86f53334fadd
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IPortableDeviceValues interface,SetUnsignedIntegerValue method, IPortableDeviceValues.SetUnsignedIntegerValue, IPortableDeviceValues::SetUnsignedIntegerValue, IPortableDeviceValuesSetUnsignedIntegerValue, SetUnsignedIntegerValue, SetUnsignedIntegerValue method, SetUnsignedIntegerValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetUnsignedIntegerValue, wpddk.iportabledevicevalues_setunsignedintegervalue
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
-	IPortableDeviceValues.SetUnsignedIntegerValue
product: Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::SetUnsignedIntegerValue


## -description



Adds a new <b>ULONG</b> value (type VT_UI4) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param Value [in]

A <b>ULONG</b> that specifies the new value.


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



If an existing value has the same key that is specified by the <i>key</i> parameter, it overwrites the existing value without any warning.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/7b3ca272-8583-429e-970d-6f9b965da337">IPortableDeviceValues::GetUnsignedIntegerValue</a>
 

 

