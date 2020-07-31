---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetIUnknownValue
title: IPortableDeviceValues::SetIUnknownValue (portabledevicetypes.h)
description: Adds a new IUnknown value (type VT_UNKNOWN) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setiunknownvalue.htm
tech.root: wpd_dk
ms.assetid: 776d4097-a582-4708-8965-0dc956d73e0d
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::SetIUnknownValue"]
ms.keywords: IPortableDeviceValues interface,SetIUnknownValue method, IPortableDeviceValues.SetIUnknownValue, IPortableDeviceValues::SetIUnknownValue, IPortableDeviceValuesSetIUnknownValue, SetIUnknownValue, SetIUnknownValue method, SetIUnknownValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetIUnknownValue, wpddk.iportabledevicevalues_setiunknownvalue
f1_keywords:
 - "portabledevicetypes/IPortableDeviceValues.SetIUnknownValue"
 - "IPortableDeviceValues.SetIUnknownValue"
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
- IPortableDeviceValues.SetIUnknownValue
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::SetIUnknownValue


## -description



Adds a new <b>IUnknown</b> value (type VT_UNKNOWN) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param pValue [in]

A pointer to an <b>IUnknown</b> interface that specifies the new value. The SDK copies a reference to the submitted interface and calls <b>AddRef</b> on it.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getiunknownvalue">IPortableDeviceValues::GetIUnknownValue</a>
 

 

