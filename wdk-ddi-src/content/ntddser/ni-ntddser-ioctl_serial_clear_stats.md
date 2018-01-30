---
UID: NI:ntddser.IOCTL_SERIAL_CLEAR_STATS
title: IOCTL_SERIAL_CLEAR_STATS
author: windows-driver-content
description: The IOCTL_SERIAL_CLEAR_STATS request clears the performance statistics for a serial device.
old-location: serports\ioctl_serial_clear_stats.htm
old-project: serports
ms.assetid: b5549ab2-8978-4fe2-ac08-56e28179714e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.ioctl_serial_clear_stats, IOCTL_SERIAL_CLEAR_STATS control code [Serial Ports], IOCTL_SERIAL_CLEAR_STATS, ntddser/IOCTL_SERIAL_CLEAR_STATS, serref_c6feaf5c-cde0-4ee9-8db7-fd96fa41ef9e.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddser.h
apiname:
-	IOCTL_SERIAL_CLEAR_STATS
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_CLEAR_STATS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_SERIAL_CLEAR_STATS</b> request clears the performance statistics for a serial device.

To obtain the performance statistics, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_get_stats.md">IOCTL_SERIAL_GET_STATS</a> request.


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


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to zero.

The <b>Status</b> field is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_get_stats.md">IOCTL_SERIAL_GET_STATS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_CLEAR_STATS control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

