---
UID: NI:d4drvif.IOCTL_DOT4_USER_BASE
title: IOCTL_DOT4_USER_BASE (d4drvif.h)
description: This topic describes IOCTL_DOT4_USER_BASE.
old-location: print\ioctl_ioctl_dot4_user_base.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IOCTL_DOT4_USER_BASE IOCTL"]
ms.keywords: IOCTL_DOT4_USER_BASE, IOCTL_DOT4_USER_BASE control, IOCTL_DOT4_USER_BASE control code [Print Devices], d4drvif/IOCTL_DOT4_USER_BASE, print.ioctl_ioctl_dot4_user_base
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_DOT4_USER_BASE
 - d4drvif/IOCTL_DOT4_USER_BASE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D4drvif.h
api_name:
 - IOCTL_DOT4_USER_BASE
---

# IOCTL_DOT4_USER_BASE IOCTL


## -description

This topic describes <b>IOCTL_DOT4_USER_BASE</b>.

## -ioctlparameters

### -input-buffer

### -input-buffer-length

### -output-buffer

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
