---
UID: NI:ntddser.IOCTL_SERIAL_GET_BAUD_RATE
title: IOCTL_SERIAL_GET_BAUD_RATE
author: windows-driver-content
description: The IOCTL_SERIAL_GET_BAUD_RATE request returns the baud rate at which the serial port is currently configured to transmit and receive data.
old-location: serports\ioctl_serial_get_baud_rate.htm
old-project: serports
ms.assetid: 074ab68e-7cd5-44e4-b3f6-2d6ddc5f3095
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_GET_BAUD_RATE, IOCTL_SERIAL_GET_BAUD_RATE control, IOCTL_SERIAL_GET_BAUD_RATE control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_BAUD_RATE, serports.ioctl_serial_get_baud_rate, serref_d3a435b0-2934-465a-9c60-91210895755e.xml
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
-	IOCTL_SERIAL_GET_BAUD_RATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_GET_BAUD_RATE IOCTL


## -description


The <b>IOCTL_SERIAL_GET_BAUD_RATE</b> request returns the baud rate at which the serial port is currently configured to transmit and receive data.

To set the baud rate, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546672">IOCTL_SERIAL_SET_BAUD_RATE</a> request.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_BAUD_RATE</b> structure that the serial controller driver uses to output the baud rate information.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439592">SERIAL_BAUD_RATE</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size in bytes of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439592">SERIAL_BAUD_RATE</a> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546672">IOCTL_SERIAL_SET_BAUD_RATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439592">SERIAL_BAUD_RATE</a>
 

 

