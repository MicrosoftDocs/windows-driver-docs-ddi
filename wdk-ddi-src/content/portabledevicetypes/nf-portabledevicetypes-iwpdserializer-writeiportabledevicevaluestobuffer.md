---
UID: NF:portabledevicetypes.IWpdSerializer.WriteIPortableDeviceValuesToBuffer
title: IWpdSerializer::WriteIPortableDeviceValuesToBuffer (portabledevicetypes.h)
description: Serializes an IPortableDeviceValues interface to a caller-allocated byte array.
old-location: wpddk\iwpdserializer_writeiportabledevicevaluestobuffer.htm
tech.root: wpd_dk
ms.assetid: ceddaff0-2c97-4de9-9a2e-3727f48eab87
ms.date: 02/15/2018
keywords: ["IWpdSerializer::WriteIPortableDeviceValuesToBuffer"]
ms.keywords: IWpdSerializer interface,WriteIPortableDeviceValuesToBuffer method, IWpdSerializer.WriteIPortableDeviceValuesToBuffer, IWpdSerializer::WriteIPortableDeviceValuesToBuffer, IWpdSerializerWriteIPortableDeviceValuesToBuffer, WriteIPortableDeviceValuesToBuffer, WriteIPortableDeviceValuesToBuffer method, WriteIPortableDeviceValuesToBuffer method,IWpdSerializer interface, portabledevicetypes/IWpdSerializer::WriteIPortableDeviceValuesToBuffer, wpddk.iwpdserializer_writeiportabledevicevaluestobuffer
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
 - IWpdSerializer::WriteIPortableDeviceValuesToBuffer
 - portabledevicetypes/IWpdSerializer::WriteIPortableDeviceValuesToBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IWpdSerializer.WriteIPortableDeviceValuesToBuffer
---

# IWpdSerializer::WriteIPortableDeviceValuesToBuffer


## -description

Serializes an <b>IPortableDeviceValues</b> interface to a caller-allocated byte array.

## -parameters

### -param dwOutputBufferLength 

[in]
<b>DWORD</b> that specifies the size of <i>pBuffer</i>, in bytes.

### -param pResults 

[in]
Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> interface to serialize.

### -param pBuffer 

[out]
Pointer to a caller-allocated buffer. To learn the size of the required buffer, call <b>GetSerializedSize</b>.

### -param pdwBytesWritten 

[out]
Pointer to a <b>DWORD</b> that indicates the number of bytes that were actually written to the caller-allocated buffer.

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
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A required pointer argument was <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The caller-provided buffer was not big enough.

</td>
</tr>
</table>

## -remarks

This method copies an <b>IPortableDeviceValues</b> interface into an existing buffer. If you want to allocate a new buffer, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iwpdserializer-getbufferfromiportabledevicevalues">GetBufferFromIPortableDeviceValues</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iwpdserializer">IWpdSerializer Interface</a>

