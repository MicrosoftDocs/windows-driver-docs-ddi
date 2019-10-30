---
UID: NI:ntddser.IOCTL_SERIAL_SET_XOFF
title: IOCTL_SERIAL_SET_XOFF (ntddser.h)
description: The IOCTL_SERIAL_SET_XOFF request emulates the reception of an XOFF (transmit off) character.
old-location: serports\ioctl_serial_set_xoff.htm
tech.root: serports
ms.assetid: cfddecbd-e225-484f-ba5c-6223a724b414
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_SET_XOFF, IOCTL_SERIAL_SET_XOFF control, IOCTL_SERIAL_SET_XOFF control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_XOFF, serports.ioctl_serial_set_xoff, serref_a2b3591a-cd26-4073-a7ab-af7f2b3f43b6.xml
ms.topic: ioctl
f1_keywords:
 - "ntddser/IOCTL_SERIAL_SET_XOFF"
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
- IOCTL_SERIAL_SET_XOFF
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_XOFF IOCTL


## -description


The <b>IOCTL_SERIAL_SET_XOFF</b> request emulates the reception of an XOFF (transmit off) character. The request stops reception of data. If automatic XON/XOFF flow control is not set, then a client <u>must</u> use a subsequent <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_xon">IOCTL_SERIAL_SET_XON</a> request to restart reception of data.


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








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_xon">IOCTL_SERIAL_SET_XON</a>
 

 

