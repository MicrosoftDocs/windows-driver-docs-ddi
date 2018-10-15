---
UID: NI:ntddser.IOCTL_SERIAL_SET_HANDFLOW
title: IOCTL_SERIAL_SET_HANDFLOW
author: windows-driver-content
description: The IOCTL_SERIAL_SET_HANDFLOW request sets the configuration of handshake flow control. The serial controller driver verifies the specified handshake flow control information.
old-location: serports\ioctl_serial_set_handflow.htm
tech.root: serports
ms.assetid: f281eab9-f724-4bdb-9dc4-2577ef2840f0
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_SET_HANDFLOW, IOCTL_SERIAL_SET_HANDFLOW control, IOCTL_SERIAL_SET_HANDFLOW control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_HANDFLOW, serports.ioctl_serial_set_handflow, serref_732613c0-4ff9-46a8-929d-e5d02be9a57c.xml
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
-	IOCTL_SERIAL_SET_HANDFLOW
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_HANDFLOW IOCTL


## -description


The <b>IOCTL_SERIAL_SET_HANDFLOW</b> request sets the configuration of handshake flow control. The serial controller driver  verifies the specified handshake flow control information.

To obtain handshake flow control information, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546574">IOCTL_SERIAL_GET_HANDFLOW</a> request.

For more information about settings for handshake flow control, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj680685">SERIAL_HANDFLOW</a>.


## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_HANDFLOW</b> structure that is used to input the handshake flow control information.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_HANDFLOW</b> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates the specified handshake flow control is not valid.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546574">IOCTL_SERIAL_GET_HANDFLOW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj680685">SERIAL_HANDFLOW</a>
 

 

