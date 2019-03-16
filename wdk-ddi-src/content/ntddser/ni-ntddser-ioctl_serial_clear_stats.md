---
UID: NI:ntddser.IOCTL_SERIAL_CLEAR_STATS
title: IOCTL_SERIAL_CLEAR_STATS (ntddser.h)
description: The IOCTL_SERIAL_CLEAR_STATS request clears the performance statistics for a serial device.
old-location: serports\ioctl_serial_clear_stats.htm
tech.root: serports
ms.assetid: b5549ab2-8978-4fe2-ac08-56e28179714e
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_CLEAR_STATS, IOCTL_SERIAL_CLEAR_STATS control, IOCTL_SERIAL_CLEAR_STATS control code [Serial Ports], ntddser/IOCTL_SERIAL_CLEAR_STATS, serports.ioctl_serial_clear_stats, serref_c6feaf5c-cde0-4ee9-8db7-fd96fa41ef9e.xml
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
- IOCTL_SERIAL_CLEAR_STATS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_CLEAR_STATS IOCTL


## -description


The <b>IOCTL_SERIAL_CLEAR_STATS</b> request clears the performance statistics for a serial device.

To obtain the performance statistics, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546600">IOCTL_SERIAL_GET_STATS</a> request.


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

The <b>Information</b> field is set to zero.

The <b>Status</b> field is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546600">IOCTL_SERIAL_GET_STATS</a>
 

 

