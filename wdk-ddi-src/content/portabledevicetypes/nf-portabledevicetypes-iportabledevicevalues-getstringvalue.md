---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetStringValue
title: IPortableDeviceValues::GetStringValue (portabledevicetypes.h)
description: Retrieves a string value (type VT_LPWSTR) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getstringvalue.htm
tech.root: wpd_dk
ms.assetid: 6c63adae-ab57-4826-aaa2-6953ab918ddd
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::GetStringValue"]
ms.keywords: GetStringValue, GetStringValue method, GetStringValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetStringValue method, IPortableDeviceValues.GetStringValue, IPortableDeviceValues::GetStringValue, IPortableDeviceValuesGetStringValue, portabledevicetypes/IPortableDeviceValues::GetStringValue, wpddk.iportabledevicevalues_getstringvalue
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
 - IPortableDeviceValues::GetStringValue
 - portabledevicetypes/IPortableDeviceValues::GetStringValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues.GetStringValue
---

# IPortableDeviceValues::GetStringValue


## -description

Retrieves a string value (type VT_LPWSTR) that is specified by a key.

## -parameters

### -param key 

[in]
A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.

### -param pValue 

[out]
Pointer to the retrieved <b>LPWSTR</b> value. The caller is responsible for calling <b>CoTaskMemFree</b> to release the memory.

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
The property specified by <i>key</i> is not a <b>LPWSTR</b> type.

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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getat">IPortableDeviceValues::GetAt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setstringvalue">IPortableDeviceValues::SetStringValue</a>

