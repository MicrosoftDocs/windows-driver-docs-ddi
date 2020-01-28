---
UID: NI:d4drvif.IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST
title: IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST (d4drvif.h)
description: This topic describes IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST.
old-location: print\ioctl_ioctl_dot4_wait_activity_broadcast.htm
tech.root: print
ms.assetid: 4E39AC46-BE78-4503-AA3A-D45BC79DBDEF
ms.date: 04/20/2018
ms.keywords: IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST, IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST control, IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST control code [Print Devices], d4drvif/IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST, print.ioctl_ioctl_dot4_wait_activity_broadcast
f1_keywords:
 - "d4drvif/IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST"
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
- IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST IOCTL


## -description


This topic describes <b>IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST</b>.


## -ioctlparameters




### -input-buffer




### -input-buffer-length




### -output-buffer




### -output-buffer-length




### -in-out-buffer




### -inout-buffer-length




### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

