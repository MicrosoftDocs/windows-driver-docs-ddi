---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetStringValue
title: IPortableDeviceValues::SetStringValue
author: windows-driver-content
description: Adds a new string value (type VT_LPWSTR) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setstringvalue.htm
tech.root: wpd_dk
ms.assetid: ee477e82-124e-46ca-8aef-02357f67bb8f
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IPortableDeviceValues interface,SetStringValue method, IPortableDeviceValues.SetStringValue, IPortableDeviceValues::SetStringValue, IPortableDeviceValuesSetStringValue, SetStringValue, SetStringValue method, SetStringValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetStringValue, wpddk.iportabledevicevalues_setstringvalue
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
-	IPortableDeviceValues.SetStringValue
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::SetStringValue


## -description



Adds a new string value (type VT_LPWSTR) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param Value [in]

A <b>LPCWSTR</b> that specifies the new value. The string is copied, so the caller can release the memory allocated for this value after calling this method.


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



Any existing key memory will be released appropriately.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/6c63adae-ab57-4826-aaa2-6953ab918ddd">IPortableDeviceValues::GetStringValue</a>
 

 

