---
UID: NF:portabledevicetypes.IWpdSerializer.GetIPortableDeviceValuesFromBuffer
title: IWpdSerializer::GetIPortableDeviceValuesFromBuffer (portabledevicetypes.h)
description: Deserializes a byte array to an IPortableDeviceValues interface.
old-location: wpddk\iwpdserializer_getiportabledevicevaluesfrombuffer.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["IWpdSerializer::GetIPortableDeviceValuesFromBuffer"]
ms.keywords: GetIPortableDeviceValuesFromBuffer, GetIPortableDeviceValuesFromBuffer method, GetIPortableDeviceValuesFromBuffer method,IWpdSerializer interface, IWpdSerializer interface,GetIPortableDeviceValuesFromBuffer method, IWpdSerializer.GetIPortableDeviceValuesFromBuffer, IWpdSerializer::GetIPortableDeviceValuesFromBuffer, IWpdSerializerGetIPortableDeviceValuesFromBuffer, portabledevicetypes/IWpdSerializer::GetIPortableDeviceValuesFromBuffer, wpddk.iwpdserializer_getiportabledevicevaluesfrombuffer
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
 - IWpdSerializer::GetIPortableDeviceValuesFromBuffer
 - portabledevicetypes/IWpdSerializer::GetIPortableDeviceValuesFromBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IWpdSerializer::GetIPortableDeviceValuesFromBuffer
---

# IWpdSerializer::GetIPortableDeviceValuesFromBuffer


## -description

Deserializes a byte array to an <b>IPortableDeviceValues</b> interface.

## -parameters

### -param pBuffer 

[in]
Pointer to the buffer to deserialize.

### -param dwInputBufferLength 

[in]
<b>DWORD</b> that specifies the size of the buffer, in bytes.

### -param ppParams 

[out]
Address of a variable that receives a pointer to an <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> interface created from the buffer. The application is responsible for calling <b>Release</b> on the interface.

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
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
An unspecified conversion error occurred.

</td>
</tr>
</table>

## -remarks

None.

## -see-also

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iwpdserializer">IWpdSerializer Interface</a>

