---
UID: NI:ntddser.IOCTL_SERIAL_SET_BREAK_ON
title: IOCTL_SERIAL_SET_BREAK_ON (ntddser.h)
description: The IOCTL_SERIAL_SET_BREAK_ON request sets the line control break signal active.
old-location: serports\ioctl_serial_set_break_on.htm
tech.root: serports
ms.assetid: bee9cb3c-0ccd-4304-ba7e-7896a16ab123
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_SET_BREAK_ON, IOCTL_SERIAL_SET_BREAK_ON control, IOCTL_SERIAL_SET_BREAK_ON control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_BREAK_ON, serports.ioctl_serial_set_break_on, serref_47487a08-4b73-4e3a-be2e-4343dd678b44.xml
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
-	IOCTL_SERIAL_SET_BREAK_ON
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_SET_BREAK_ON IOCTL


## -description


The <b>IOCTL_SERIAL_SET_BREAK_ON</b> request sets the line control break signal active.

To set the line control break signal inactive, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546680">IOCTL_SERIAL_SET_BREAK_OFF</a> request.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546680">IOCTL_SERIAL_SET_BREAK_OFF</a>
 

 

