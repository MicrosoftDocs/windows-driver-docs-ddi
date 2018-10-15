---
UID: NI:ntddser.IOCTL_SERIAL_SET_BAUD_RATE
title: IOCTL_SERIAL_SET_BAUD_RATE
author: windows-driver-content
description: The IOCTL_SERIAL_SET_BAUD_RATE request sets the baud rate on a serial controller device. The serial controller driver verifies the specified baud rate.
old-location: serports\ioctl_serial_set_baud_rate.htm
tech.root: serports
ms.assetid: cf3a4b6e-fefa-4a81-84cf-3a4d5529c8a7
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_SET_BAUD_RATE, IOCTL_SERIAL_SET_BAUD_RATE control, IOCTL_SERIAL_SET_BAUD_RATE control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_BAUD_RATE, serports.ioctl_serial_set_baud_rate, serref_e71e6ea2-4cac-440d-abc2-40fba2990518.xml
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
-	IOCTL_SERIAL_SET_BAUD_RATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_BAUD_RATE IOCTL


## -description


The <b>IOCTL_SERIAL_SET_BAUD_RATE</b> request sets the baud rate on a serial controller device. The serial controller driver verifies the specified baud rate.

To obtain the baud rate, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546554">IOCTL_SERIAL_GET_BAUD_RATE</a> request.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439592">SERIAL_BAUD_RATE</a> structure that a client allocates and sets to input the baud rate.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439592">SERIAL_BAUD_RATE</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546554">IOCTL_SERIAL_GET_BAUD_RATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439592">SERIAL_BAUD_RATE</a>
 

 

