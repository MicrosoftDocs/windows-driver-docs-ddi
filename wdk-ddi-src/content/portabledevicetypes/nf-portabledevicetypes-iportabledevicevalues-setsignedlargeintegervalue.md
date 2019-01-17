---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetSignedLargeIntegerValue
title: IPortableDeviceValues::SetSignedLargeIntegerValue
description: Adds a new LONGLONG value (type VT_I8) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setsignedlargeintegervalue.htm
tech.root: wpd_dk
ms.assetid: 9a27e7c3-73fe-4875-83e2-94fd4929ce9c
ms.date: 02/15/2018
ms.keywords: IPortableDeviceValues interface,SetSignedLargeIntegerValue method, IPortableDeviceValues.SetSignedLargeIntegerValue, IPortableDeviceValues::SetSignedLargeIntegerValue, IPortableDeviceValuesSetSignedLargeIntegerValue, SetSignedLargeIntegerValue, SetSignedLargeIntegerValue method, SetSignedLargeIntegerValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetSignedLargeIntegerValue, wpddk.iportabledevicevalues_setsignedlargeintegervalue
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
-	IPortableDeviceValues.SetSignedLargeIntegerValue
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::SetSignedLargeIntegerValue


## -description



Adds a new <b>LONGLONG</b> value (type VT_I8) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param Value [in]

A <b>LONGLONG</b> that specifies the new value.


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



<a href="https://msdn.microsoft.com/3a086a7e-22e3-4d60-9f10-4db442fcc6f9">IPortableDeviceValues::GetSignedLargeIntegerValue</a>
 

 

