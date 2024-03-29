---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetErrorValue
title: IPortableDeviceValues::SetErrorValue (portabledevicetypes.h)
description: Adds a new HRESULT value (type VT_ERROR) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_seterrorvalue.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::SetErrorValue"]
ms.keywords: IPortableDeviceValues interface,SetErrorValue method, IPortableDeviceValues.SetErrorValue, IPortableDeviceValues::SetErrorValue, IPortableDeviceValuesSetErrorValue, SetErrorValue, SetErrorValue method, SetErrorValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetErrorValue, wpddk.iportabledevicevalues_seterrorvalue
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
 - IPortableDeviceValues::SetErrorValue
 - portabledevicetypes/IPortableDeviceValues::SetErrorValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues::SetErrorValue
---

# IPortableDeviceValues::SetErrorValue


## -description

Adds a new <b>HRESULT</b> value (type VT_ERROR) or overwrites an existing one.

## -parameters

### -param key [in]


A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.

### -param Value [in]


An <b>HRESULT</b> that contains the new value.

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

If an existing value has the same key specified by the <i>key</i> parameter, it overwrites the existing value without any warning.

## -see-also

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-geterrorvalue">IPortableDeviceValues::GetErrorValue</a>

