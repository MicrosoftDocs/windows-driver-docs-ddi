---
UID: NI:ntddser.IOCTL_SERIAL_SET_DTR
title: IOCTL_SERIAL_SET_DTR (ntddser.h)
description: The IOCTL_SERIAL_SET_DTR request sets DTR (data terminal ready).
old-location: serports\ioctl_serial_set_dtr.htm
tech.root: serports
ms.assetid: cec61f34-389b-43a9-9b24-d42779c018d2
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_SET_DTR, IOCTL_SERIAL_SET_DTR control, IOCTL_SERIAL_SET_DTR control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_DTR, serports.ioctl_serial_set_dtr, serref_6af1af3b-1345-41df-8dcf-66ec296c27f8.xml
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
-	IOCTL_SERIAL_SET_DTR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_DTR IOCTL


## -description


The <b>IOCTL_SERIAL_SET_DTR</b> request sets DTR (data terminal ready).

If the handshake flow control of the device is configured to automatically use DTR, a client cannot clear or set DTR.

To clear DTR, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546541">IOCTL_SERIAL_CLR_DTR</a> request.


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

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that the handshake flow control of the device is set to automatically use DTR.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546541">IOCTL_SERIAL_CLR_DTR</a>
 

 

