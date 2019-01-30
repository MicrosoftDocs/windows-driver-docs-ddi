---
UID: NI:d4drvif.IOCTL_DOT4_OPEN_CHANNEL
title: IOCTL_DOT4_OPEN_CHANNEL (d4drvif.h)
description: This topic describes IOCTL_DOT4_OPEN_CHANNEL.
old-location: print\ioctl_ioctl_dot4_open_channel.htm
tech.root: print
ms.assetid: 9E71A230-5412-4248-A412-B92BE9E119FD
ms.date: 04/20/2018
ms.keywords: IOCTL_DOT4_OPEN_CHANNEL, IOCTL_DOT4_OPEN_CHANNEL control, IOCTL_DOT4_OPEN_CHANNEL control code [Print Devices], d4drvif/IOCTL_DOT4_OPEN_CHANNEL, print.ioctl_ioctl_dot4_open_channel
ms.topic: ioctl
req.header: d4drvif.h
req.include-header: 
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
-	D4drvif.h
api_name:
-	IOCTL_DOT4_OPEN_CHANNEL
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DOT4_OPEN_CHANNEL IOCTL


## -description


This topic describes <b>IOCTL_DOT4_OPEN_CHANNEL</b>.


## -ioctlparameters




### -input-buffer




### -input-buffer-length




### -output-buffer




### -output-buffer-length




### -in-out-buffer




### -inout-buffer-length




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

