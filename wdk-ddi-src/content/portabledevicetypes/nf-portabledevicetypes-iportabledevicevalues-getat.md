---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetAt
title: IPortableDeviceValues::GetAt (portabledevicetypes.h)
description: Retrieves a value from the collection, by a zero-based index.
old-location: wpddk\iportabledevicevalues_getat.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::GetAt"]
ms.keywords: GetAt, GetAt method, GetAt method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetAt method, IPortableDeviceValues.GetAt, IPortableDeviceValues::GetAt, IPortableDeviceValuesGetAt, portabledevicetypes/IPortableDeviceValues::GetAt, wpddk.iportabledevicevalues_getat
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
 - IPortableDeviceValues::GetAt
 - portabledevicetypes/IPortableDeviceValues::GetAt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues.GetAt
---

# IPortableDeviceValues::GetAt


## -description

Retrieves a value from the collection, by a zero-based index.

## -parameters

### -param index 

[in]
A <b>DWORD</b> that specifies a zero-based index in the collection.

### -param pKey 

[in, out]
An optional <b>PROPERTYKEY</b> pointer that retrieves the key of the specified item.

### -param pValue 

[in, out]
An optional <b>PROPVARIANT</b> that retrieves the value of the specified item. The caller must free the memory by calling <b>PropVariantClear</b> when done with it.

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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
An invalid index number was specified.

</td>
</tr>
</table>

## -remarks

If a property indicates a value of type VT_UNKNOWN, the property will be one of the Windows Portable Devices interfaces (<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicekeycollection">IPortableDeviceKeyCollection</a>, <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicepropvariantcollection">IPortableDevicePropVariantCollection</a>, <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a>, or <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevaluescollection">IPortableDeviceValuesCollection</a>). No other interfaces can be returned by Windows Portable Devices.

## -see-also

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getstringvalue">IPortableDeviceValues::GetStringValue</a>
