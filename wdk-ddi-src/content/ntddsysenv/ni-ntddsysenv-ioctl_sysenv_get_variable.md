---
UID: NI:ntddsysenv.IOCTL_SYSENV_GET_VARIABLE
title: IOCTL_SYSENV_GET_VARIABLE (ntddsysenv.h)
description: Gets the value of the specified system environment variables using SysEnv device.
old-location: kernel\ioctl_ioctl_sysenv_get_variable.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IOCTL_SYSENV_GET_VARIABLE IOCTL"]
ms.keywords: IOCTL_SYSENV_GET_VARIABLE, IOCTL_SYSENV_GET_VARIABLE control, IOCTL_SYSENV_GET_VARIABLE control code [Kernel-Mode Driver Architecture], kernel.ioctl_ioctl_sysenv_get_variable, ntddsysenv/IOCTL_SYSENV_GET_VARIABLE
req.header: ntddsysenv.h
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
 - IOCTL_SYSENV_GET_VARIABLE
 - ntddsysenv/IOCTL_SYSENV_GET_VARIABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddsysenv.h
api_name:
 - IOCTL_SYSENV_GET_VARIABLE
---

# IOCTL_SYSENV_GET_VARIABLE IOCTL


## -description

Gets the value of the specified system environment variables using
    SysEnv device.

## -ioctlparameters

### -input-buffer

A pointer to a <a href="/windows-hardware/drivers/ddi/ntddsysenv/ns-ntddsysenv-_sysenv_variable">SYSENV_VARIABLE</a> structure that specifies the variable..

### -input-buffer-length

The size of the <a href="/windows-hardware/drivers/ddi/ntddsysenv/ns-ntddsysenv-_sysenv_variable">SYSENV_VARIABLE</a> structure.

### -output-buffer

A pointer to a <a href="/windows-hardware/drivers/ddi/ntddsysenv/ns-ntddsysenv-_sysenv_value">SYSENV_VALUE</a> structure that receives the value of the variable.

### -output-buffer-length

The size of the <a href="/windows-hardware/drivers/ddi/ntddsysenv/ns-ntddsysenv-_sysenv_value">SYSENV_VALUE</a> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
