---
UID: NF:wdm.ExGetPreviousMode
title: ExGetPreviousMode function (wdm.h)
description: The ExGetPreviousMode routine returns the previous processor mode for the current thread.
old-location: kernel\exgetpreviousmode.htm
tech.root: kernel
ms.assetid: 0f4c7bc2-a29d-4b0c-81c3-01cdfefa1322
ms.date: 04/30/2018
keywords: ["ExGetPreviousMode function"]
ms.keywords: ExGetPreviousMode, ExGetPreviousMode routine [Kernel-Mode Driver Architecture], k102_080fbfa6-6261-453d-a2c7-e08818d34b6f.xml, kernel.exgetpreviousmode, wdm/ExGetPreviousMode
f1_keywords:
 - "wdm/ExGetPreviousMode"
 - "ExGetPreviousMode"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExGetPreviousMode
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExGetPreviousMode function


## -description


The <b>ExGetPreviousMode</b> routine returns the previous processor mode for the current thread.


## -returns



<b>ExGetPreviousMode</b> returns a <b>KPROCESSOR_MODE</b> value, one of <b>KernelMode</b> or <b>UserMode</b>. This value specifies the previous processor mode for the current thread.




## -remarks



If an I/O request can originate either in user mode or kernel mode and the caller passes pointers to data structures used for I/O, the driver must be able to determine whether the caller's pointers are valid in user mode or kernel mode.

If drivers are processing I/O requests using the normal IRP-based I/O dispatch method, they can determine the previous processor mode by checking the <i>RequestorMode</i> parameter in the IRP header. (The <i>RequestorMode</i> parameter is set by the I/O manager.)

Alternatively, <b>ExGetPreviousMode</b> can be used to determine the previous processor mode. This routine is particularly useful in situations where a previous mode parameter is not available, for example, in a file driver that uses fast I/O.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentthread">KeGetCurrentThread</a>
 

 

