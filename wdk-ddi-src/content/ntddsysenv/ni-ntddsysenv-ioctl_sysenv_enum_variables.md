---
UID: NI:ntddsysenv.IOCTL_SYSENV_ENUM_VARIABLES
title: IOCTL_SYSENV_ENUM_VARIABLES
author: windows-driver-content
description: Returns information about system environment variables using SysEnv device.
old-location: kernel\ioctl_ioctl_sysenv_enum_variables.htm
old-project: kernel
ms.assetid: 605CA19C-048A-4FBA-8568-7B1867C99210
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IOCTL_SYSENV_ENUM_VARIABLES, IOCTL_SYSENV_ENUM_VARIABLES control code [Kernel-Mode Driver Architecture], kernel.ioctl_ioctl_sysenv_enum_variables, ntddsysenv/IOCTL_SYSENV_ENUM_VARIABLES
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IOCTL_SYSENV_ENUM_VARIABLES
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_GROUP, *PSTORAGE_ZONE_GROUP
---

# IOCTL_SYSENV_ENUM_VARIABLES IOCTL


## -description



Returns information about system environment variables using
    SysEnv device.





## -ioctlparameters




### -input-buffer

A boolean value indicating whether values should be included.


### -input-buffer-length

Size of BOOLEAN.


### -output-buffer

A pointer to a buffer that contains the system environment variable information. If values have been requested, the buffer points to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt791536">XVARIABLE_NAME_AND_VALUE</a> structures. Otherwise, returns an array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt791535">XVARIABLE_NAME</a>  structures. 

The location of the next entry is determined by <b>NextEntryOffset</b> of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt791536">XVARIABLE_NAME_AND_VALUE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/mt791535">XVARIABLE_NAME</a>.


### -output-buffer-length

On input, the length in bytes of the output buffer. On output,
        the length in bytes of the returned data. If the input buffer is
        large enough, then this value  indicates the amount of data copied
        into output buffer. If the input buffer is too small, then it
        indicates the required buffer length.



### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

