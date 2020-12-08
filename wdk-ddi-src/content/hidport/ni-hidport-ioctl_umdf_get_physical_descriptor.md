---
UID: NI:hidport.IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
title: IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR (hidport.h)
description: The IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code obtains the physical descriptor of a HIDClass device.
old-location: hid\ioctl_umdf_get_physical_descriptor.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR IOCTL"]
ms.keywords: IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR, IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control, IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code, hid.ioctl_umdf_get_physical_descriptor, hidport/IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR, umdf.ioctl_umdf_get_physical_descriptor
req.header: hidport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
f1_keywords:
 - IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
 - hidport/IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hidport.h
api_name:
 - IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
---

# IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR IOCTL


## -description

The <b>IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR</b> 
   control code obtains the physical descriptor of a HIDClass device.

## -ioctlparameters

### -input-buffer

A UMDF-based driver obtains the size, in bytes, of the buffer by calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getdeviceiocontrolparameters">IWDFRequest::GetDeviceIoControlParameters</a> and providing the  <i>pOutBufferSize</i> parameter.

### -input-buffer-length

### -output-buffer

The driver copies the physical descriptor to the user buffer that is retrieved by calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a>.

### -output-buffer-length

The size of the buffer that is retrieved by calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

HID minidrivers that carry out the I/O to the device must also:

<ul>
<li>Call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-setinformation">IWDFRequest::SetInformation</a> to set the number of bytes transferred from the device.</li>
<li>Call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_get_physical_descriptor">IOCTL_GET_PHYSICAL_DESCRIPTOR</a>
