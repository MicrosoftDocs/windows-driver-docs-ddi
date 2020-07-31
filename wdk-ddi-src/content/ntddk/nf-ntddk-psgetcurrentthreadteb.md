---
UID: NF:ntddk.PsGetCurrentThreadTeb
title: PsGetCurrentThreadTeb function (ntddk.h)
description: The PsGetCurrentThreadTeb routine returns the Thread Environment Block (TEB) of the current thread. The call must be made in kernel-mode.
old-location: kernel\psgetcurrentthreadteb.htm
tech.root: kernel
ms.assetid: 822B75D4-A825-4BB1-8265-A1389F4982C7
ms.date: 04/30/2018
keywords: ["PsGetCurrentThreadTeb function"]
ms.keywords: PsGetCurrentThreadTeb, PsGetCurrentThreadTeb routine [Kernel-Mode Driver Architecture], kernel.psgetcurrentthreadteb, ntddk/PsGetCurrentThreadTeb
f1_keywords:
 - "ntddk/PsGetCurrentThreadTeb"
 - "PsGetCurrentThreadTeb"
req.header: ntddk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: Any level (see Remarks)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PsGetCurrentThreadTeb
targetos: Windows
req.typenames: 
---

# PsGetCurrentThreadTeb function


## -description


The <b>PsGetCurrentThreadTeb</b> routine returns the Thread Environment Block (TEB) of the current thread, or NULL. The call must be made in kernel-mode.


## -returns



A pointer to the thread environment block of the current thread. The TEB should be accessed within a try/catch exception block. 

<b>PsGetCurrentThreadTeb</b> returns NULL in the following cases:

* The current thread does not have a TEB (for example a system thread).
* The current thread cannot safely access its own TEB. This might happen if the driver attached the thread to the address space of another process, for example by calling [**KeStackAttachProcess**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kestackattachprocess).

## -remarks

While <b>PsGetCurrentThreadTeb</b> can be called at any IRQL without causing a bugcheck, the TEB is not safe to access at DISPATCH_LEVEL or above (it could be paged out).
Also, if you're calling at elevated IRQL from the context of an interrupt or DPC, the current thread is whatever happened to be running on the current processor when your interrupt was delivered there.
As a result, it is recommended that you call <b>PsGetCurrentThreadTeb</b> from thread context below DISPATCH_LEVEL.



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Process and Thread Manager Routines</a>
 

 

