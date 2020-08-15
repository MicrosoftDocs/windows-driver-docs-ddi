---
UID: NF:wdm.ObUnRegisterCallbacks
title: ObUnRegisterCallbacks function (wdm.h)
description: The ObUnRegisterCallbacks routine unregisters a set of callback routines that were registered with the ObRegisterCallbacks routine.
old-location: kernel\obunregistercallbacks.htm
tech.root: kernel
ms.assetid: 01121323-da0c-4ae9-b0c0-f6302583237c
ms.date: 04/30/2018
keywords: ["ObUnRegisterCallbacks function"]
ms.keywords: ObUnRegisterCallbacks, ObUnRegisterCallbacks routine [Kernel-Mode Driver Architecture], k107_f0c1fdd0-3dcc-466c-a7a1-fab0b38e4e88.xml, kernel.obunregistercallbacks, wdm/ObUnRegisterCallbacks
f1_keywords:
 - "wdm/ObUnRegisterCallbacks"
 - "ObUnRegisterCallbacks"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating system.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ObUnRegisterCallbacks
targetos: Windows
req.typenames: 
---

# ObUnRegisterCallbacks function


## -description


The <b>ObUnRegisterCallbacks</b> routine unregisters a set of callback routines that were registered with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obregistercallbacks">ObRegisterCallbacks</a> routine.


## -parameters




### -param RegistrationHandle 
[in]
A value that identifies the set of callback routines to unregister. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obregistercallbacks">ObRegisterCallbacks</a> routine provides this value when it originally registered the callback routines.


## -remarks



A driver that calls the <b>ObRegisterCallbacks</b> routine must call the <b>ObUnRegisterCallbacks</b> routine before the driver is unloaded.

> [!CAUTION]
> Do not call **ObRegisterCallbacks** more than once. This is a "double free" and results in [Bug Check 0x7E: SYSTEM_THREAD_EXCEPTION_NOT_HANDLED](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0x7e--system-thread-exception-not-handled).



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obregistercallbacks">ObRegisterCallbacks</a>
 

 

