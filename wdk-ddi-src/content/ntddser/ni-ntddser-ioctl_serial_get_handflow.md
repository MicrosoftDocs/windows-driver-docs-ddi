---
UID: NI:ntddser.IOCTL_SERIAL_GET_HANDFLOW
title: IOCTL_SERIAL_GET_HANDFLOW (ntddser.h)
description: The IOCTL_SERIAL_GET_HANDFLOW request returns information about the configuration of the handshake flow control set for a serial device.
old-location: serports\ioctl_serial_get_handflow.htm
tech.root: serports
ms.assetid: d1d918fb-1ccb-46e6-ad28-e48daf226b3a
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_GET_HANDFLOW, IOCTL_SERIAL_GET_HANDFLOW control, IOCTL_SERIAL_GET_HANDFLOW control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_HANDFLOW, serports.ioctl_serial_get_handflow, serref_caa7cdf7-cf60-4baa-88bf-43a7db423a37.xml
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddser.h
api_name:
- IOCTL_SERIAL_GET_HANDFLOW
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_GET_HANDFLOW IOCTL


## -description


The <b>IOCTL_SERIAL_GET_HANDFLOW</b> request returns information about the configuration of the handshake flow control set for a serial device.

To set the configuration of the handshake flow control, a client can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_set_handflow">IOCTL_SERIAL_SET_HANDFLOW</a> request.

For more information about the settings for handshake flow control, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ns-ntddser-_serial_handflow">SERIAL_HANDFLOW</a>.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_HANDFLOW</b> structure that the serial controller driver uses to output information about the configuration of handshake flow control.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_HANDFLOW</b> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a <b>SERIAL_HANDFLOW</b> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_set_handflow">IOCTL_SERIAL_SET_HANDFLOW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ns-ntddser-_serial_handflow">SERIAL_HANDFLOW</a>
 

 

