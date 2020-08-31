---
UID: NF:portabledevicetypes.IWpdSerializer.GetSerializedSize
title: IWpdSerializer::GetSerializedSize (portabledevicetypes.h)
description: Calculates the buffer size that is required to hold a serialized IPortableDeviceValues interface.
old-location: wpddk\iwpdserializer_getserializedsize.htm
tech.root: wpd_dk
ms.assetid: 85b87586-d4aa-4590-9a4b-73439fa8cf6a
ms.date: 02/15/2018
keywords: ["IWpdSerializer::GetSerializedSize"]
ms.keywords: GetSerializedSize, GetSerializedSize method, GetSerializedSize method,IWpdSerializer interface, IWpdSerializer interface,GetSerializedSize method, IWpdSerializer.GetSerializedSize, IWpdSerializer::GetSerializedSize, IWpdSerializerGetSerializedSize, portabledevicetypes/IWpdSerializer::GetSerializedSize, wpddk.iwpdserializer_getserializedsize
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
 - IWpdSerializer::GetSerializedSize
 - portabledevicetypes/IWpdSerializer::GetSerializedSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IWpdSerializer.GetSerializedSize
---

# IWpdSerializer::GetSerializedSize


## -description

Calculates the buffer size that is required to hold a serialized <b>IPortableDeviceValues</b> interface.

## -parameters

### -param pSource 

[in]
Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> interface whose size you want to request.

### -param pdwSize 

[out]
Pointer to a <b>DWORD</b> that indicates the buffer size that is required to serialize <i>pSource</i>, in bytes.

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
There was not enough available memory to create the buffer.

</td>
</tr>
</table>

## -remarks

None.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iwpdserializer">IWpdSerializer Interface</a>

