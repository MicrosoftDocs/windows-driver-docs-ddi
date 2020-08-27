---
UID: NI:d4drvif.IOCTL_DOT4_READ
title: IOCTL_DOT4_READ (d4drvif.h)
description: This topic describes IOCTL_DOT4_READ.
old-location: print\ioctl_ioctl_dot4_read.htm
tech.root: print
ms.assetid: 6E9E20E9-37F1-4C2F-B7C8-885F617A671F
ms.date: 04/20/2018
keywords: ["IOCTL_DOT4_READ IOCTL"]
ms.keywords: IOCTL_DOT4_READ, IOCTL_DOT4_READ control, IOCTL_DOT4_READ control code [Print Devices], d4drvif/IOCTL_DOT4_READ, print.ioctl_ioctl_dot4_read
f1_keywords:
 - "d4drvif/IOCTL_DOT4_READ"
 - "IOCTL_DOT4_READ"
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
- IOCTL_DOT4_READ
targetos: Windows
req.typenames: 
---

# IOCTL_DOT4_READ IOCTL


## -description


This topic describes <b>IOCTL_DOT4_READ</b>.


## -ioctlparameters




### -input-buffer




### -input-buffer-length




### -output-buffer




### -output-buffer-length




### -in-out-buffer




### -inout-buffer-length




### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

