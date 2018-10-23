---
UID: NI:ntddpar.IOCTL_PAR_SET_WRITE_ADDRESS
title: IOCTL_PAR_SET_WRITE_ADDRESS
author: windows-driver-content
description: The IOCTL_PAR_SET_WRITE_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) write address (channel) for a parallel device. The parallel port bus driver queues this request on a work queue for the parallel device.
old-location: parports\ioctl_par_set_write_address.htm
tech.root: parports
ms.assetid: ea4a071e-aa6b-4c9f-b497-523af7e42430
ms.date: 02/15/2018
ms.keywords: IOCTL_PAR_SET_WRITE_ADDRESS, IOCTL_PAR_SET_WRITE_ADDRESS control code [Parallel Ports], cisspd_396ff93f-623f-48a5-925e-9338672fa974.xml, ntddpar/IOCTL_PAR_SET_WRITE_ADDRESS, parports.ioctl_par_set_write_address
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
-	IOCTL_PAR_SET_WRITE_ADDRESS
product:
- Windows
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# IOCTL_PAR_SET_WRITE_ADDRESS IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The IOCTL_PAR_SET_WRITE_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) write address (channel) for a parallel device. The parallel port bus driver queues this request on a work queue for the parallel device.




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a UCHAR buffer that the client allocates to input a write address. The client sets the buffer to an ECP or EPP write address.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a UCHAR.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:




#### -STATUS_INVALID_PARAMETER

<b>Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of a UCHAR.


## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_set_read_address.md">IOCTL_PAR_SET_READ_ADDRESS</a>



 

 


