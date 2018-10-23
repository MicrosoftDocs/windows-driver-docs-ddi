---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetBoolValue
title: IPortableDeviceValues::SetBoolValue
author: windows-driver-content
description: Adds a new Boolean value (type VT_BOOL) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setboolvalue.htm
tech.root: wpd_dk
ms.assetid: 98c7be46-c99a-4cf4-b77b-2d3ea896b198
ms.date: 02/15/2018
ms.keywords: IPortableDeviceValues interface,SetBoolValue method, IPortableDeviceValues.SetBoolValue, IPortableDeviceValues::SetBoolValue, IPortableDeviceValuesSetBoolValue, SetBoolValue, SetBoolValue method, SetBoolValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetBoolValue, wpddk.iportabledevicevalues_setboolvalue
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
-	IPortableDeviceValues.SetBoolValue
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::SetBoolValue


## -description



Adds a new <b>Boolean</b> value (type VT_BOOL) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param Value [in]

A <b>BOOL</b> that specifies the new value.


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



If an existing value has the same key specified by the <i>key</i> parameter, it overwrites the existing value without any warning. The existing key memory is released appropriately.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/ff66e4b8-25f9-4c53-8755-46c860ec37d9">IPortableDeviceValues::GetBoolValue</a>
 

 

