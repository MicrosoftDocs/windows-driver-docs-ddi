---
UID: NI:ntddser.IOCTL_SERIAL_SET_TIMEOUTS
title: IOCTL_SERIAL_SET_TIMEOUTS
author: windows-driver-content
description: An IOCTL_SERIAL_SET_TIMEOUTS request resets the time-out value that the system-supplied bus driver for parallel ports uses with write requests.
old-location: parports\ioctl_serial_set_timeouts.htm
old-project: parports
ms.assetid: 524efbe1-110e-4c59-a759-b083888b2e26
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_SET_TIMEOUTS, IOCTL_SERIAL_SET_TIMEOUTS control code [Parallel Ports], cisspd_d42d38bf-b276-4428-9a6e-05f4d0b4253b.xml, ntddser/IOCTL_SERIAL_SET_TIMEOUTS, parports.ioctl_serial_set_timeouts
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
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
-	ntddser.h
api_name:
-	IOCTL_SERIAL_SET_TIMEOUTS
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_TIMEOUTS IOCTL


## -description


An IOCTL_SERIAL_SET_TIMEOUTS request resets the time-out value that the system-supplied bus driver for parallel ports uses with write requests. The write time-out value is used with SPP and SW_ECP modes. The parallel port bus driver queues a set time-out request on a work queue for the parallel device.

A client uses an <a href="..\ntddser\ni-ntddser-ioctl_serial_get_timeouts.md">IOCTL_SERIAL_GET_TIMEOUTS</a> to obtain the time-out values.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> points to a SERIAL_TIMEOUTS structure that the client allocates to input time-out information. The client sets the <b>WriteTotalTimeoutConstant</b> member to a value in milliseconds.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a SERIAL_TIMEOUTS structure.


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

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to one of the following values:




#### -STATUS_BUFFER_TOO_SMALL

The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a SERIAL_TIMEOUTS structure.


#### -STATUS_INVALID_PARAMETER

The requested time-out value is less than two seconds.


## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_get_timeouts.md">IOCTL_SERIAL_GET_TIMEOUTS</a>



 

 


