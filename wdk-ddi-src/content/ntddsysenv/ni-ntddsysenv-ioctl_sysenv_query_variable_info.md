---
UID: NI:ntddsysenv.IOCTL_SYSENV_QUERY_VARIABLE_INFO
title: IOCTL_SYSENV_QUERY_VARIABLE_INFO
author: windows-driver-content
description: Returns information about system environment variables using SysEnv device.
old-location: kernel\ioctl_ioctl_sysenv_query_variable_info.htm
old-project: kernel
ms.assetid: 4056202F-2292-40A5-BE1D-8C1A6FA79B50
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IOCTL_SYSENV_QUERY_VARIABLE_INFO, IOCTL_SYSENV_QUERY_VARIABLE_INFO control code [Kernel-Mode Driver Architecture], kernel.ioctl_ioctl_sysenv_query_variable_info, ntddsysenv/IOCTL_SYSENV_QUERY_VARIABLE_INFO
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
-	IOCTL_SYSENV_QUERY_VARIABLE_INFO
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_GROUP, *PSTORAGE_ZONE_GROUP
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

A pointer to a <a href="..\ntddsysenv\ns-ntddsysenv-_sysenv_variable_info.md">SYSENV_VARIABLE_INFO</a> structure that contains variable information.


### -output-buffer-length

The size of the <a href="..\ntddsysenv\ns-ntddsysenv-_sysenv_variable_info.md">SYSENV_VARIABLE_INFO</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IOCTL_SYSENV_QUERY_VARIABLE_INFO control code%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

