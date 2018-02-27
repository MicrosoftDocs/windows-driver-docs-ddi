---
UID: NI:parallel.IOCTL_INTERNAL_INIT_1284_3_BUS
title: IOCTL_INTERNAL_INIT_1284_3_BUS
author: windows-driver-content
description: The IOCTL_INTERNAL_INIT_1284_3_BUS request initializes and assigns an IEEE 1284.3 device ID to all the 1284.3 daisy chain devices that are attached to a parallel port.
old-location: parports\ioctl_internal_init_1284_3_bus.htm
old-project: parports
ms.assetid: 9c936e4e-8a49-4c6a-a8d0-b314548b5e6a
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_INIT_1284_3_BUS, IOCTL_INTERNAL_INIT_1284_3_BUS control code [Parallel Ports], cisspd_bbc4a115-34b5-4f7b-9fd4-bbf4d4293e81.xml, parallel/IOCTL_INTERNAL_INIT_1284_3_BUS, parports.ioctl_internal_init_1284_3_bus
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
-	IOCTL_INTERNAL_INIT_1284_3_BUS
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_INIT_1284_3_BUS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_INTERNAL_INIT_1284_3_BUS</b> request initializes and assigns an IEEE 1284.3 device ID to all the 1284.3 daisy chain devices that are attached to a parallel port.

Windows 2000 supports from zero to four daisy chain devices and an end-of-chain device simultaneously attached to a parallel port. Windows XP supports from zero to two daisy chain devices and an end-of-chain device simultaneously attached to a parallel port.
<div class="alert"><b>Note</b>    This request is included primarily for test purposes, and Microsoft does not recommend using it during the normal operation of a parallel port.</div><div> </div>For more information, see <a href="https://msdn.microsoft.com/80222ed9-f900-4d97-b459-2d8ca780e1d1">Device Stacks for ParallelPorts and Devices</a>.


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

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports.


## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_deselect_device.md">IOCTL_INTERNAL_DESELECT_DEVICE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_INIT_1284_3_BUS control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

