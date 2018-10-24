---
UID: NI:hidport.IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
title: IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code obtains the physical descriptor of a HIDClass device.
old-location: hid\ioctl_umdf_get_physical_descriptor.htm
tech.root: hid
ms.assetid: F5852D3B-FD30-4308-A08E-B7DEA86A35E6
ms.date: 04/30/2018
ms.keywords: IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR, IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control, IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code, hid.ioctl_umdf_get_physical_descriptor, hidport/IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR, umdf.ioctl_umdf_get_physical_descriptor
ms.topic: ioctl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Hidport.h
api_name:
-	IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR IOCTL


## -description


The <b>IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR</b> 
   control code obtains the physical descriptor of a HIDClass device.


## -ioctlparameters




### -input-buffer

A UMDF-based driver obtains the size, in bytes, of the buffer by calling <a href="https://msdn.microsoft.com/96de6f7a-da1d-44a6-b1f7-44859312a662">IWDFRequest::GetDeviceIoControlParameters</a> and providing the  <i>pOutBufferSize</i> parameter.


### -input-buffer-length








### -output-buffer

The driver copies the physical descriptor to the user buffer that is retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>.


### -output-buffer-length

The size of the buffer that is retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

HID minidrivers that carry out the I/O to the device must also:

<ul>
<li>Call <a href="https://msdn.microsoft.com/dc2c907c-1e3b-418c-85f8-9902dc83f7ab">IWDFRequest::SetInformation</a> to set the number of bytes transferred from the device.</li>
<li>Call <a href="https://msdn.microsoft.com/2fa389f8-8277-4795-a89e-ac5d92004310">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541064">IOCTL_GET_PHYSICAL_DESCRIPTOR</a>
 

 

