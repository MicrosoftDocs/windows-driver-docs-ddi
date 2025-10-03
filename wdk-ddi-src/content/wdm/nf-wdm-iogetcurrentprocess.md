---
UID: NF:wdm.IoGetCurrentProcess
title: IoGetCurrentProcess function (wdm.h)
description: The IoGetCurrentProcess routine returns a pointer to the current process.
tech.root: kernel
ms.date: 09/22/2025
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetCurrentProcess
 - wdm/IoGetCurrentProcess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetCurrentProcess
---

# IoGetCurrentProcess function

## -description

The **IoGetCurrentProcess** routine returns a pointer to the current process. Call **PsGetCurrentProcess** instead of **IoGetCurrentProcess**.

## -returns

**IoGetCurrentProcess** returns a pointer to the current process.

## -remarks

This routine is identical to **PsGetCurrentProcess**:

``#define PsGetCurrentProcess IoGetCurrentProcess``

**PsGetCurrentProcess** (and **IoGetCurrentProcess**) retrieves the current process from the thread's APC state. This returns the process that the current thread is attached to, which might be different from the process that originally created the thread.

The process returned by **PsGetCurrentProcess** may differ from the process whose ID is returned by [**PsGetCurrentProcessId**](../ntddk/nf-ntddk-psgetcurrentprocessid.md). Use **PsGetCurrentProcessId** to get the process ID of the process that created the current thread. Use **PsGetProcessId(PsGetCurrentProcess())** to get the process ID of the process that the thread is currently attached to.

## -see-also

[**PsGetCurrentProcessId**](../ntddk/nf-ntddk-psgetcurrentprocessid.md)

[**PsGetCurrentThread**](../ntddk/nf-ntddk-psgetcurrentthread.md)

[**PsGetProcessId**](../ntddk/nf-ntddk-psgetprocessid.md)
