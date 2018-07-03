---
UID: NI:ntddser.IOCTL_SERIAL_SET_RTS
title: IOCTL_SERIAL_SET_RTS
author: windows-driver-content
description: The IOCTL_SERIAL_SET_RTS request sets RTS (request to send).
old-location: serports\ioctl_serial_set_rts.htm
old-project: serports
ms.assetid: a3ce8e93-12b1-4f84-82e5-0a384ac44f66
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_SET_RTS, IOCTL_SERIAL_SET_RTS control, IOCTL_SERIAL_SET_RTS control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_RTS, serports.ioctl_serial_set_rts, serref_bda4eddb-8ddc-4fd6-83ac-c4b6516fe949.xml
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
-	IOCTL_SERIAL_SET_RTS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_RTS IOCTL


## -description


The <b>IOCTL_SERIAL_SET_RTS</b> request sets RTS (request to send).

If a handshake flow control of the device is configured to automatically use RTS, a client cannot clear or set RTS.

A client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546545">IOCTL_SERIAL_CLR_RTS</a> request to clear RTS.


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

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the handshake flow control of the device is set to automatically use RTS.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546545">IOCTL_SERIAL_CLR_RTS</a>
 

 

