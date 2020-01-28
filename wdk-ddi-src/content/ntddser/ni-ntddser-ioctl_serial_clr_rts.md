---
UID: NI:ntddser.IOCTL_SERIAL_CLR_RTS
title: IOCTL_SERIAL_CLR_RTS (ntddser.h)
description: The IOCTL_SERIAL_CLR_RTS request clears the request to send (RTS) control signal.
old-location: serports\ioctl_serial_clr_rts.htm
tech.root: serports
ms.assetid: 7ecb357f-ba84-4b3d-b6db-73f6682988b8
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_CLR_RTS, IOCTL_SERIAL_CLR_RTS control, IOCTL_SERIAL_CLR_RTS control code [Serial Ports], ntddser/IOCTL_SERIAL_CLR_RTS, serports.ioctl_serial_clr_rts, serref_c6ddd78f-7cea-4358-9c02-9c211399f6c8.xml
f1_keywords:
 - "ntddser/IOCTL_SERIAL_CLR_RTS"
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
- IOCTL_SERIAL_CLR_RTS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_CLR_RTS IOCTL


## -description


The <b>IOCTL_SERIAL_CLR_RTS</b> request clears the <i>request to send</i> (RTS) control signal.

To set RTS, a client can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_rts">IOCTL_SERIAL_SET_RTS</a> request.

If the handshake flow control of the device is configured to automatically use RTS, a client cannot clear or set RTS.


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




#### -The Status member is set to one of the Generic Status Values for Serial Device Control Requests. A status of STATUS_INVALID_PARAMETER indicates that the handshake flow control of the device is set to automatically use RTS.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_rts">IOCTL_SERIAL_SET_RTS</a>
 

 

