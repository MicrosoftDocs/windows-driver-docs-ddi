---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetBufferValue
title: IPortableDeviceValues::GetBufferValue (portabledevicetypes.h)
description: The GetBufferValue interface retrieves a byte array value (type VT_VECTOR | VT_UI1) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getbuffervalue.htm
tech.root: wpd_dk
ms.assetid: 3ce1e4c4-21e0-4e4f-8cf2-3f78b47ee817
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::GetBufferValue"]
ms.keywords: GetBufferValue, GetBufferValue method, GetBufferValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetBufferValue method, IPortableDeviceValues.GetBufferValue, IPortableDeviceValues::GetBufferValue, IPortableDeviceValuesGetBufferValue, portabledevicetypes/IPortableDeviceValues::GetBufferValue, wpddk.iportabledevicevalues_getbuffervalue
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
 - IPortableDeviceValues::GetBufferValue
 - portabledevicetypes/IPortableDeviceValues::GetBufferValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues.GetBufferValue
---

# IPortableDeviceValues::GetBufferValue


## -description

The GetBufferValue interface retrieves a <b>byte array</b> value (type VT_VECTOR | VT_UI1) that is specified by a key.

## -parameters

### -param key 

[in]
A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.

### -param ppValue 

[out]
A pointer to the retrieved <b>BYTE*</b> value. The caller must free the memory by calling <b>CoTaskMemFree</b>.

### -param pcbValue 

[out]
A pointer to the size of <i>ppValue</i>, in bytes.

## -returns

The method returns an <b>HRESULT</b>. Possible return values are shown in the following table.

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
The property that is specified by <i>key</i> is not a <b>BYTE</b>* type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
The property that is specified by <i>key</i> is not in the collection.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One or more arguments specified are not valid.

</td>
</tr>
</table>

## -remarks

Retrieving a <b>NULL</b> buffer or a zero-sized buffer is not supported  and will return E_INVALIDARG.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setbuffervalue">IPortableDeviceValues::SetBufferValue</a>

