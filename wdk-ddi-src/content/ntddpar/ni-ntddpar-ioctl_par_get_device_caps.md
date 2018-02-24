---
UID: NI:ntddpar.IOCTL_PAR_GET_DEVICE_CAPS
title: IOCTL_PAR_GET_DEVICE_CAPS
author: windows-driver-content
description: The IOCTL_PAR_GET_DEVICE_CAPS request does the following:Specifies the protocols that the system-supplied bus driver for parallel ports must not use with a parallel deviceReturns the operating protocols that the parallel device supportsFor more information, see Setting and Clearing a Communication Mode for a Parallel Device.
old-location: parports\ioctl_par_get_device_caps.htm
old-project: parports
ms.assetid: 6446d667-1a35-4055-b9e7-41d372df9db2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: parports.ioctl_par_get_device_caps, IOCTL_PAR_GET_DEVICE_CAPS control code [Parallel Ports], IOCTL_PAR_GET_DEVICE_CAPS, ntddpar/IOCTL_PAR_GET_DEVICE_CAPS, cisspd_ea215140-7641-4554-bf95-362942d13143.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddpar.h
apiname:
-	IOCTL_PAR_GET_DEVICE_CAPS
product: Windows
targetos: Windows
req.typenames: "*POFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION"
---

# IOCTL_PAR_GET_DEVICE_CAPS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> member is set to the size, in bytes, of a USHORT. 

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:




#### -STATUS_BUFFER_TOO_SMALL

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than the size, in bytes, of a USHORT.


## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_PAR_GET_DEVICE_CAPS control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

