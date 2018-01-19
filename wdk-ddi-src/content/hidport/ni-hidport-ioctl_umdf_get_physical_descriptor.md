---
UID: NI:hidport.IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
title: IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code obtains the physical descriptor of a HIDClass device.
old-location: hid\ioctl_umdf_get_physical_descriptor.htm
old-project: hid
ms.assetid: F5852D3B-FD30-4308-A08E-B7DEA86A35E6
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidRegisterMinidriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
req.alt-loc: Hidport.h
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
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
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

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
HID minidrivers that carry out the I/O to the device must also:


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_get_physical_descriptor.md">IOCTL_GET_PHYSICAL_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\wdf]:%20IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

