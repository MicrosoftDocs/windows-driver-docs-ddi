---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetSignedIntegerValue
title: IPortableDeviceValues::SetSignedIntegerValue (portabledevicetypes.h)
description: Adds a new LONG value (type VT_I4) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setsignedintegervalue.htm
tech.root: wpd_dk
ms.assetid: f86a5e41-5040-4374-96a5-c405f68f62fe
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::SetSignedIntegerValue"]
ms.keywords: IPortableDeviceValues interface,SetSignedIntegerValue method, IPortableDeviceValues.SetSignedIntegerValue, IPortableDeviceValues::SetSignedIntegerValue, IPortableDeviceValuesSetSignedIntegerValue, SetSignedIntegerValue, SetSignedIntegerValue method, SetSignedIntegerValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetSignedIntegerValue, wpddk.iportabledevicevalues_setsignedintegervalue
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
 - IPortableDeviceValues::SetSignedIntegerValue
 - portabledevicetypes/IPortableDeviceValues::SetSignedIntegerValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues.SetSignedIntegerValue
---

# IPortableDeviceValues::SetSignedIntegerValue


## -description

Adds a new <b>LONG</b> value (type VT_I4) or overwrites an existing one.

## -parameters

### -param key 

[in]
A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.

### -param Value 

[in]
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

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getsignedintegervalue">IPortableDeviceValues::GetSignedIntegerValue</a>