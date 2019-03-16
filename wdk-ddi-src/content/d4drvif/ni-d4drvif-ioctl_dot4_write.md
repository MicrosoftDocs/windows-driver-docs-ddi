---
UID: NI:d4drvif.IOCTL_DOT4_WRITE
title: IOCTL_DOT4_WRITE (d4drvif.h)
description: This topic describes IOCTL_DOT4_WRITE.
old-location: print\ioctl_ioctl_dot4_write.htm
tech.root: print
ms.assetid: 40B095ED-BB8C-4FBC-BA09-A40BC70B8F9D
ms.date: 04/20/2018
ms.keywords: IOCTL_DOT4_WRITE, IOCTL_DOT4_WRITE control, IOCTL_DOT4_WRITE control code [Print Devices], d4drvif/IOCTL_DOT4_WRITE, print.ioctl_ioctl_dot4_write
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D4drvif.h
api_name:
- IOCTL_DOT4_WRITE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DOT4_WRITE IOCTL


## -description


This topic describes <b>IOCTL_DOT4_WRITE</b>.


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
 

 

