---
UID: NI:parallel.IOCTL_INTERNAL_DISCONNECT_IDLE
title: IOCTL_INTERNAL_DISCONNECT_IDLE
author: windows-driver-content
description: The IOCTL_INTERNAL_DISCONNECT_IDLE request disconnects the IEEE 1284 operating modes that are set for a parallel device.
old-location: parports\ioctl_internal_disconnect_idle.htm
old-project: parports
ms.assetid: 02fd4277-502d-4a9e-b809-10134ed0900b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: parports.ioctl_internal_disconnect_idle, IOCTL_INTERNAL_DISCONNECT_IDLE control code [Parallel Ports], IOCTL_INTERNAL_DISCONNECT_IDLE, parallel/IOCTL_INTERNAL_DISCONNECT_IDLE, cisspd_ff4b2feb-d3b4-4b80-9f6f-f4fd16bab4c1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: parallel.h
req.include-header: Parallel.h
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
-	parallel.h
apiname: 
-	IOCTL_INTERNAL_DISCONNECT_IDLE
product: Windows
targetos: Windows
req.typenames: *LPRILGBATOKEN, RILGBATOKEN
---

# IOCTL_INTERNAL_DISCONNECT_IDLE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_INTERNAL_DISCONNECT_IDLE</b> request disconnects the IEEE 1284 operating modes that are set for a parallel device. The system-supplied bus driver for parallel ports sets the default operating mode to IEEE 1284-compatible.

For more information, see <a href="https://msdn.microsoft.com/2ff53ed0-dbb7-4c8f-b6e4-5f7d20124a7c">Setting and Clearing a Communication Mode for a Parallel Device</a>.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices.


## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_device_caps.md">IOCTL_PAR_GET_DEVICE_CAPS</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_DISCONNECT_IDLE control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

