---
UID: NI:ntddser.IOCTL_SERIAL_GET_TIMEOUTS
title: IOCTL_SERIAL_GET_TIMEOUTS
author: windows-driver-content
description: The IOCTL_SERIAL_GET_TIMEOUTS request returns the time-out values that the serial controller driver uses with read and write requests.
old-location: serports\ioctl_serial_get_timeouts.htm
old-project: serports
ms.assetid: b3cff263-6393-4217-a86a-43f9a0bff926
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_GET_TIMEOUTS, IOCTL_SERIAL_GET_TIMEOUTS control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_TIMEOUTS, serports.ioctl_serial_get_timeouts, serref_7e3bc962-fbe3-4474-bf7b-1fc035a39a29.xml
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
-	Ntddser.h
api_name:
-	IOCTL_SERIAL_GET_TIMEOUTS
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_TIMEOUTS IOCTL


## -description


The <b>IOCTL_SERIAL_GET_TIMEOUTS</b> request returns the time-out values that the serial controller driver uses with read and write requests.

To set time-outs, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544126">IOCTL_SERIAL_SET_TIMEOUTS</a> request. 

For more information about time-outs, see <a href="https://msdn.microsoft.com/ed5b80a9-93cb-4e3f-9038-e715be35f206">Setting Read and Write Time-Outs for a Serial Device</a>.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_TIMEOUTS</b> structure that the serial controller driver uses to output information about read and write time-out values.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544126">IOCTL_SERIAL_SET_TIMEOUTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439614">SERIAL_TIMEOUTS</a>
 

 

