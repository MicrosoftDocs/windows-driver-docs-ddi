---
UID: NI:ntddpar.IOCTL_PAR_GET_DEVICE_CAPS
title: IOCTL_PAR_GET_DEVICE_CAPS
author: windows-driver-content
description: The IOCTL_PAR_GET_DEVICE_CAPS request does the following:Specifies the protocols that the system-supplied bus driver for parallel ports must not use with a parallel deviceReturns the operating protocols that the parallel device supportsFor more information, see Setting and Clearing a Communication Mode for a Parallel Device.
old-location: parports\ioctl_par_get_device_caps.htm
tech.root: parports
ms.assetid: 6446d667-1a35-4055-b9e7-41d372df9db2
ms.date: 2/15/2018
ms.keywords: IOCTL_PAR_GET_DEVICE_CAPS, IOCTL_PAR_GET_DEVICE_CAPS control code [Parallel Ports], cisspd_ea215140-7641-4554-bf95-362942d13143.xml, ntddpar/IOCTL_PAR_GET_DEVICE_CAPS, parports.ioctl_par_get_device_caps
ms.topic: ioctl
req.header: ntddpar.h
req.include-header: Ntddpar.h
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
-	ntddpar.h
api_name:
-	IOCTL_PAR_GET_DEVICE_CAPS
product:
- Windows
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# IOCTL_PAR_GET_DEVICE_CAPS IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The IOCTL_PAR_GET_DEVICE_CAPS request does the following:

<ul>
<li>
Specifies the protocols that the system-supplied bus driver for parallel ports must not use with a parallel device

</li>
<li>
Returns the operating protocols that the parallel device supports

</li>
</ul>
For more information, see <a href="https://msdn.microsoft.com/2ff53ed0-dbb7-4c8f-b6e4-5f7d20124a7c">Setting and Clearing a Communication Mode for a Parallel Device</a>.




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a USHORT buffer that the client allocates to input and output mode information. The request sets the input buffer to a bitwise OR of the modes that the parallel port bus driver must not use with a parallel device.


### -input-buffer-length

The length of a USHORT.


### -output-buffer

<b>AssociatedIrp.SystemBuffer</b> points to the USHORT buffer that the parallel port bus driver uses to output mode information. The parallel port bus driver sets the buffer to indicate which operating protocols the parallel device supports.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a USHORT.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to the size, in bytes, of a USHORT.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:




#### -STATUS_BUFFER_TOO_SMALL

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than the size, in bytes, of a USHORT.


## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>



 

 


