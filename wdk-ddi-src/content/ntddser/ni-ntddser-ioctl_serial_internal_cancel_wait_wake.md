---
UID: NI:ntddser.IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE
title: IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE
author: windows-driver-content
description: The IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE request disables the wait/wake operation of a serial device.
old-location: serports\ioctl_serial_internal_cancel_wait_wake.htm
tech.root: serports
ms.assetid: 007701f4-4ee0-46e1-963c-e2af2a441a81
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE, IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE control, IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE control code [Serial Ports], ntddser/IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE, serports.ioctl_serial_internal_cancel_wait_wake, serref_0976b701-5c14-4912-854f-4d5a356744d2.xml
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
-	ntddser.h
api_name:
-	IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE IOCTL


## -description



The IOCTL_SERIAL_INTERNAL_CANCEL_WAIT_WAKE request disables the wait/wake operation of a serial device.




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

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546636">IOCTL_SERIAL_INTERNAL_DO_WAIT_WAKE</a>
 

 

