---
UID: NF:wdm.KeRegisterBoundCallback
title: KeRegisterBoundCallback function (wdm.h)
description: The KeRegisterBoundCallback routine registers a routine to be called whenever a user-mode bound exception occurs.
old-location: kernel\keregisterboundcallback.htm
tech.root: kernel
ms.assetid: 0985589E-074A-45C8-9F8A-384DC42EC884
ms.date: 04/30/2018
keywords: ["KeRegisterBoundCallback function"]
ms.keywords: KeRegisterBoundCallback, KeRegisterBoundCallback routine [Kernel-Mode Driver Architecture], kernel.keregisterboundcallback, wdm/KeRegisterBoundCallback
f1_keywords:
 - "wdm/KeRegisterBoundCallback"
 - "KeRegisterBoundCallback"
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeRegisterBoundCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRegisterBoundCallback function


## -description


The <b>KeRegisterBoundCallback</b> routine registers a routine to be called whenever a user-mode bound exception occurs.


## -parameters




### -param CallbackRoutine [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-bound_callback">BoundCallback</a> function.


## -returns



On success, <b>KeRegisterBoundCallback</b> returns an opaque pointer that the caller passes to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterboundcallback">KeDeregisterBoundCallback</a> to deregister the callback. The routine returns <b>NULL</b> if it is unable to register the callback.




## -remarks



The <b>KeRegisterBoundCallback</b> routine provides the opportunity for a kernel-mode driver to intercept and handle user-mode bound exceptions. When a bounds exception for a user-mode thread occurs, the system calls the registered  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-bound_callback">BoundCallback</a> function to manage the bounds trap. The return value of the <i>BoundCallback</i> function indicates the action that the system should then perform, such as propagating the bounds exception or terminating the user-mode process. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterboundcallback">KeDeregisterBoundCallback</a>
 

 

