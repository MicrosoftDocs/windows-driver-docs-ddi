---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetFloatValue
title: IPortableDeviceValues::GetFloatValue (portabledevicetypes.h)
description: The GetFloatValue method retrieves a FLOAT value (type VT_R4) specified by a key.
old-location: wpddk\iportabledevicevalues_getfloatvalue.htm
tech.root: wpd_dk
ms.assetid: f281c407-7d1c-48e8-ab5e-c18bf0c080e0
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::GetFloatValue"]
ms.keywords: GetFloatValue, GetFloatValue method, GetFloatValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetFloatValue method, IPortableDeviceValues.GetFloatValue, IPortableDeviceValues::GetFloatValue, IPortableDeviceValuesGetFloatValue, portabledevicetypes/IPortableDeviceValues::GetFloatValue, wpddk.iportabledevicevalues_getfloatvalue
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
 - IPortableDeviceValues::GetFloatValue
 - portabledevicetypes/IPortableDeviceValues::GetFloatValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues.GetFloatValue
---

# IPortableDeviceValues::GetFloatValue


## -description

The <b>GetFloatValue</b> method retrieves a <b>FLOAT</b> value (type VT_R4) specified by a key.

## -parameters

### -param key 

[in]
A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.

### -param pValue 

[out]
Pointer to the retrieved <b>FLOAT</b> value.

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
The property specified by <i>key</i> is not a <b>FLOAT</b> type.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setfloatvalue">IPortableDeviceValues::SetFloatValue</a>

