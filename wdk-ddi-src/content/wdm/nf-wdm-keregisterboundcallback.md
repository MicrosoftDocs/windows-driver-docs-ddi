---
UID: NF:wdm.KeRegisterBoundCallback
title: KeRegisterBoundCallback function
author: windows-driver-content
description: The KeRegisterBoundCallback routine registers a routine to be called whenever a user-mode bound exception occurs.
old-location: kernel\keregisterboundcallback.htm
old-project: kernel
ms.assetid: 0985589E-074A-45C8-9F8A-384DC42EC884
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeRegisterBoundCallback, KeRegisterBoundCallback routine [Kernel-Mode Driver Architecture], kernel.keregisterboundcallback, wdm/KeRegisterBoundCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeRegisterBoundCallback
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRegisterBoundCallback function


## -description


The <b>KeRegisterBoundCallback</b> routine registers a routine to be called whenever a user-mode bound exception occurs.


## -parameters




### -param CallbackRoutine [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn957853">BoundCallback</a> function.


## -returns



On success, <b>KeRegisterBoundCallback</b> returns an opaque pointer that the caller passes to <a href="https://msdn.microsoft.com/library/windows/hardware/dn957855">KeDeregisterBoundCallback</a> to deregister the callback. The routine returns <b>NULL</b> if it is unable to register the callback.




## -remarks



The <b>KeRegisterBoundCallback</b> routine provides the opportunity for a kernel-mode driver to intercept and handle user-mode bound exceptions. When a bounds exception for a user-mode thread occurs, the system calls the registered  <a href="https://msdn.microsoft.com/library/windows/hardware/dn957853">BoundCallback</a> function to manage the bounds trap. The return value of the <i>BoundCallback</i> function indicates the action that the system should then perform, such as propagating the bounds exception or terminating the user-mode process. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn957855">KeDeregisterBoundCallback</a>
 

 

