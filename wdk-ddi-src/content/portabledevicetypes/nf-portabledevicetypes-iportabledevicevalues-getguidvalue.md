---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetGuidValue
title: IPortableDeviceValues::GetGuidValue (portabledevicetypes.h)
description: Retrieves a GUID value (type VT_CLSID) specified by a key.
old-location: wpddk\iportabledevicevalues_getguidvalue.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::GetGuidValue"]
ms.keywords: GetGuidValue, GetGuidValue method, GetGuidValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetGuidValue method, IPortableDeviceValues.GetGuidValue, IPortableDeviceValues::GetGuidValue, IPortableDeviceValuesGetGuidValue, portabledevicetypes/IPortableDeviceValues::GetGuidValue, wpddk.iportabledevicevalues_getguidvalue
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
 - IPortableDeviceValues::GetGuidValue
 - portabledevicetypes/IPortableDeviceValues::GetGuidValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues::GetGuidValue
---

# IPortableDeviceValues::GetGuidValue


## -description

Retrieves a <b>GUID</b> value (type VT_CLSID) specified by a key.

## -parameters

### -param key 

[in]
A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.

### -param pValue 

[out]
Pointer to the retrieved <b>GUID</b> value.

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
<tr>
<td width="40%">
<dl>
<dt><b>DISP_E_TYPEMISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not a <b>GUID</b> type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not in the collection.

</td>
</tr>
</table>

## -remarks

None.

## -see-also

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setguidvalue">IPortableDeviceValues::SetGuidValue</a>

