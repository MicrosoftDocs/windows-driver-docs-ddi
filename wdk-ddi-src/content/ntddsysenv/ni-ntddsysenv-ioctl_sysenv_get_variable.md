---
UID: NI:ntddsysenv.IOCTL_SYSENV_GET_VARIABLE
title: IOCTL_SYSENV_GET_VARIABLE
description: Gets the value of the specified system environment variables using SysEnv device.
old-location: kernel\ioctl_ioctl_sysenv_get_variable.htm
tech.root: kernel
ms.assetid: B6249E4B-DF79-4B74-AE52-137FEF299169
ms.date: 04/30/2018
ms.keywords: IOCTL_SYSENV_GET_VARIABLE, IOCTL_SYSENV_GET_VARIABLE control, IOCTL_SYSENV_GET_VARIABLE control code [Kernel-Mode Driver Architecture], kernel.ioctl_ioctl_sysenv_get_variable, ntddsysenv/IOCTL_SYSENV_GET_VARIABLE
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddsysenv.h
api_name:
-	IOCTL_SYSENV_GET_VARIABLE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SYSENV_GET_VARIABLE IOCTL


## -description



Gets the value of the specified system environment variables using
    SysEnv device.





## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt791533">SYSENV_VARIABLE</a> structure that specifies the variable..


### -input-buffer-length

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt791533">SYSENV_VARIABLE</a> structure.


### -output-buffer

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt791532">SYSENV_VALUE</a> structure that receives the value of the variable.


### -output-buffer-length

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt791532">SYSENV_VALUE</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

