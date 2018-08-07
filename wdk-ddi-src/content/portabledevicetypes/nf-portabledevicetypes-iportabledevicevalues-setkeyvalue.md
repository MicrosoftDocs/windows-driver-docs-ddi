---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetKeyValue
title: IPortableDeviceValues::SetKeyValue
author: windows-driver-content
description: Adds a new REFPROPERTYKEY value (type VT_UNKNOWN) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setkeyvalue.htm
tech.root: wpd_dk
ms.assetid: 4c8ccaa6-a99e-42b5-9044-fe11d17e9aa7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IPortableDeviceValues interface,SetKeyValue method, IPortableDeviceValues.SetKeyValue, IPortableDeviceValues::SetKeyValue, IPortableDeviceValuesSetKeyValue, SetKeyValue, SetKeyValue method, SetKeyValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetKeyValue, wpddk.iportabledevicevalues_setkeyvalue
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
-	IPortableDeviceValues.SetKeyValue
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::SetKeyValue


## -description



Adds a new <b>REFPROPERTYKEY</b> value (type VT_UNKNOWN) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param Value [in]

A <b>REFPROPERTYKEY</b> that specifies the new value.


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



<a href="https://msdn.microsoft.com/00d0f564-05ab-4f87-8477-efedc172e296">IPortableDeviceValues::GetKeyValue</a>
 

 

