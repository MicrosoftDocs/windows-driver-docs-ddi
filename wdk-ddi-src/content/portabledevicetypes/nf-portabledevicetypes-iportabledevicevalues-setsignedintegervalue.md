---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetSignedIntegerValue
title: IPortableDeviceValues::SetSignedIntegerValue (portabledevicetypes.h)
description: Adds a new LONG value (type VT_I4) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setsignedintegervalue.htm
tech.root: wpd_dk
ms.assetid: f86a5e41-5040-4374-96a5-c405f68f62fe
ms.date: 02/15/2018
ms.keywords: IPortableDeviceValues interface,SetSignedIntegerValue method, IPortableDeviceValues.SetSignedIntegerValue, IPortableDeviceValues::SetSignedIntegerValue, IPortableDeviceValuesSetSignedIntegerValue, SetSignedIntegerValue, SetSignedIntegerValue method, SetSignedIntegerValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetSignedIntegerValue, wpddk.iportabledevicevalues_setsignedintegervalue
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- PortableDeviceTypes.h
api_name:
- IPortableDeviceValues.SetSignedIntegerValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::SetSignedIntegerValue


## -description



Adds a new <b>LONG</b> value (type VT_I4) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param Value [in]

A <b>LONG</b> that specifies the new value.


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



<a href="https://msdn.microsoft.com/4867effa-a471-498f-9b06-e66204fa139c">IPortableDeviceValues::GetSignedIntegerValue</a>
 

 

