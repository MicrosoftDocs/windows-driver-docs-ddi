---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetBoolValue
title: IPortableDeviceValues::SetBoolValue (portabledevicetypes.h)
description: Adds a new Boolean value (type VT_BOOL) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setboolvalue.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::SetBoolValue"]
ms.keywords: IPortableDeviceValues interface,SetBoolValue method, IPortableDeviceValues.SetBoolValue, IPortableDeviceValues::SetBoolValue, IPortableDeviceValuesSetBoolValue, SetBoolValue, SetBoolValue method, SetBoolValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetBoolValue, wpddk.iportabledevicevalues_setboolvalue
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - IPortableDeviceValues::SetBoolValue
 - portabledevicetypes/IPortableDeviceValues::SetBoolValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues.SetBoolValue
---

# IPortableDeviceValues::SetBoolValue


## -description

Adds a new <b>Boolean</b> value (type VT_BOOL) or overwrites an existing one.

## -parameters

### -param key 

[in]
A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.

### -param Value 

[in]
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

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getboolvalue">IPortableDeviceValues::GetBoolValue</a>
