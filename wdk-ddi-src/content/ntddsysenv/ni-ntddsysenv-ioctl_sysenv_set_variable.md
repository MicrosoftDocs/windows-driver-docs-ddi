---
UID: NI:ntddsysenv.IOCTL_SYSENV_SET_VARIABLE
title: IOCTL_SYSENV_SET_VARIABLE (ntddsysenv.h)
description: Sets the value of the specified system environment variables using SysEnv device.
old-location: kernel\ioctl_ioctl_sysenv_set_variable.htm
tech.root: kernel
ms.assetid: 2BA555D8-CFD3-4D27-BC38-3B261D2F95EF
ms.date: 04/30/2018
keywords: ["IOCTL_SYSENV_SET_VARIABLE IOCTL"]
ms.keywords: IOCTL_SYSENV_SET_VARIABLE, IOCTL_SYSENV_SET_VARIABLE control, IOCTL_SYSENV_SET_VARIABLE control code [Kernel-Mode Driver Architecture], kernel.ioctl_ioctl_sysenv_set_variable, ntddsysenv/IOCTL_SYSENV_SET_VARIABLE
f1_keywords:
 - "ntddsysenv/IOCTL_SYSENV_SET_VARIABLE"
 - "IOCTL_SYSENV_SET_VARIABLE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddsysenv.h
api_name:
- IOCTL_SYSENV_SET_VARIABLE
targetos: Windows
req.typenames: 
---

# IOCTL_SYSENV_SET_VARIABLE IOCTL


## -description



Sets the value of the specified system environment variables using
    SysEnv device.





## -ioctlparameters




### -input-buffer

A pointer to a  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ns-ntddsysenv-_xvariable_name_and_value">XVARIABLE_NAME_AND_VALUE</a> structure that contains the information to set.


### -input-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ns-ntddsysenv-_xvariable_name_and_value">XVARIABLE_NAME_AND_VALUE</a> structure.


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
 

 

