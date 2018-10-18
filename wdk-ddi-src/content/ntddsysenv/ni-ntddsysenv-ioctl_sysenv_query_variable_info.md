---
UID: NI:ntddsysenv.IOCTL_SYSENV_QUERY_VARIABLE_INFO
title: IOCTL_SYSENV_QUERY_VARIABLE_INFO
author: windows-driver-content
description: Returns information about system environment variables using SysEnv device.
old-location: kernel\ioctl_ioctl_sysenv_query_variable_info.htm
tech.root: kernel
ms.assetid: 4056202F-2292-40A5-BE1D-8C1A6FA79B50
ms.date: 4/30/2018
ms.keywords: IOCTL_SYSENV_QUERY_VARIABLE_INFO, IOCTL_SYSENV_QUERY_VARIABLE_INFO control, IOCTL_SYSENV_QUERY_VARIABLE_INFO control code [Kernel-Mode Driver Architecture], kernel.ioctl_ioctl_sysenv_query_variable_info, ntddsysenv/IOCTL_SYSENV_QUERY_VARIABLE_INFO
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
-	IOCTL_SYSENV_QUERY_VARIABLE_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SYSENV_QUERY_VARIABLE_INFO IOCTL


## -description



Returns information about system environment variables using
    SysEnv device.





## -ioctlparameters




### -input-buffer

A pointer to a ULONG variable that contains the attributes of the system environment variable.


### -input-buffer-length

Size of ULONG.


### -output-buffer

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt791534">SYSENV_VARIABLE_INFO</a> structure that contains variable information.


### -output-buffer-length

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt791534">SYSENV_VARIABLE_INFO</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

