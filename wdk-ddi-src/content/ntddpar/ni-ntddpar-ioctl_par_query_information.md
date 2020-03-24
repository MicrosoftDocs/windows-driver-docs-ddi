---
UID: NI:ntddpar.IOCTL_PAR_QUERY_INFORMATION
title: IOCTL_PAR_QUERY_INFORMATION (ntddpar.h)
description: The IOCTL_PAR_QUERY_INFORMATION request returns the status of an IEEE 1284 end-of-chain device.
old-location: parports\ioctl_par_query_information.htm
tech.root: parports
ms.assetid: 272e7810-1242-4e56-8431-bd7c5908247a
ms.date: 02/15/2018
keywords: ["IOCTL_PAR_QUERY_INFORMATION IOCTL"]
ms.keywords: IOCTL_PAR_QUERY_INFORMATION, IOCTL_PAR_QUERY_INFORMATION control code [Parallel Ports], cisspd_50a28bb8-8015-4b25-9850-9038b1c1789a.xml, ntddpar/IOCTL_PAR_QUERY_INFORMATION, parports.ioctl_par_query_information
f1_keywords:
 - "ntddpar/IOCTL_PAR_QUERY_INFORMATION"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddpar.h
api_name:
- IOCTL_PAR_QUERY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# IOCTL_PAR_QUERY_INFORMATION IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The IOCTL_PAR_QUERY_INFORMATION request returns the status of an IEEE 1284 end-of-chain device.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a PAR_QUERY_INFORMATION structure that the client allocates to output status information. The system-supplied bus driver for parallel ports sets the <b>Status</b> member to a bitwise OR of one or more of the following operating conditions:

PARALLEL_BUSY

PARALLEL_NOT_CONNECTED

PARALLEL_OFF_LINE

PARALLEL_PAPER_EMPTY

PARALLEL_POWER_OFF

PARALLEL_SELECTED


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\ntddpar\ns-ntddpar-_par_query_information.md">PAR_QUERY_INFORMATION</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a PAR_QUERY_INFORMATION structure. Otherwise, the <b>Information</b> is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:




#### -STATUS_BUFFER_TOO_SMALL

The value of the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than the size, in bytes, of a PAR_QUERY_INFORMATION structure.


## -see-also

<a href="..\ntddpar\ns-ntddpar-_par_query_information.md">PAR_QUERY_INFORMATION</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_location.md">IOCTL_PAR_QUERY_LOCATION</a>



 

 


