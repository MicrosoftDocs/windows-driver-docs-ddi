---
UID: NI:usbscan.IOCTL_GET_PIPE_CONFIGURATION
title: IOCTL_GET_PIPE_CONFIGURATION
description: Returns a description of every transfer pipe supported for a device.
old-location: image\ioctl_get_pipe_configuration.htm
tech.root: image
ms.assetid: 60d320d2-24ca-4c7a-bdcf-ed3322a02f00
ms.date: 05/03/2018
ms.keywords: IOCTL_GET_PIPE_CONFIGURATION, IOCTL_GET_PIPE_CONFIGURATION control, IOCTL_GET_PIPE_CONFIGURATION control code [Imaging Devices], image.ioctl_get_pipe_configuration, stifnc_d8b8d478-b15d-402e-b449-052a25ff38fc.xml, usbscan/IOCTL_GET_PIPE_CONFIGURATION
ms.topic: ioctl
req.header: usbscan.h
req.include-header: Usbscan.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbscan.h
api_name:
-	IOCTL_GET_PIPE_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GET_PIPE_CONFIGURATION IOCTL


## -description


Returns a description of every transfer pipe supported for a device.


## -ioctlparameters




### -input-buffer

<b>NULL</b>.


### -input-buffer-length

Zero.


### -output-buffer

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548541">USBSCAN_PIPE_CONFIGURATION</a> structure.


### -output-buffer-length

Size of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



<h3><a id="ddk_ioctl_get_pipe_configuration_si"></a><a id="DDK_IOCTL_GET_PIPE_CONFIGURATION_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_GET_PIPE_CONFIGURATION I/O control code, the caller must specify the address of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548541">USBSCAN_PIPE_CONFIGURATION</a> structure as the function's <i>lpOutbuffer</i> parameter. The kernel-mode driver fills in the structure.

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.



