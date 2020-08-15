---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetGuidValue
title: IPortableDeviceValues::SetGuidValue (portabledevicetypes.h)
description: Adds a new GUID value (type VT_CLSID) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setguidvalue.htm
tech.root: wpd_dk
ms.assetid: 08b5184b-6baa-45dc-be26-cbf7d9c96616
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::SetGuidValue"]
ms.keywords: IPortableDeviceValues interface,SetGuidValue method, IPortableDeviceValues.SetGuidValue, IPortableDeviceValues::SetGuidValue, IPortableDeviceValuesSetGuidValue, SetGuidValue, SetGuidValue method, SetGuidValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetGuidValue, wpddk.iportabledevicevalues_setguidvalue
f1_keywords:
 - "portabledevicetypes/IPortableDeviceValues.SetGuidValue"
 - "IPortableDeviceValues.SetGuidValue"
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
- IPortableDeviceValues.SetGuidValue
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::SetGuidValue


## -description



Adds a new <b>GUID</b> value (type VT_CLSID) or overwrites an existing one.




## -parameters




### -param key 
[in]
A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param Value 
[in]
A <b>REFGUID</b> that contains the new value.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getguidvalue">IPortableDeviceValues::GetGuidValue</a>
 

 

