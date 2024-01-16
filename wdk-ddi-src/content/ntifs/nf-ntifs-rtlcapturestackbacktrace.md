---
UID: NF:ntifs.RtlCaptureStackBackTrace
title: RtlCaptureStackBackTrace function (ntifs.h)
description: Learn more about the RtlCaptureStackBackTrace function.
tech.root: ifsk
ms.date: 01/16/2024
keywords: ["RtlCaptureStackBackTrace function"]
ms.keywords: RtlCaptureStackBackTrace, RtlCaptureStackBackTrace routine [Installable File System Drivers], ifsk.rtlcapturestackbacktrace, ntifs/RtlCaptureStackBackTrace, rtlref_c329ad74-ebb1-478d-a0d2-fd2ae2c8da2a.xml
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
req.lib: NtosKrnl.lib; OneCoreUAP.lib on Windows 10
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql:
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlCaptureStackBackTrace
 - ntifs/RtlCaptureStackBackTrace
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtDll.dll
 - NtosKrnl.exe
 - API-MS-Win-Core-RTLSupport-l1-1-0.dll
 - API-MS-Win-Core-RTLSupport-l1-2-0.dll
api_name:
 - RtlCaptureStackBackTrace
---

# RtlCaptureStackBackTrace function

## -description

The **RtlCaptureStackBackTrace** routine captures a stack trace by walking the stack and recording the information for each frame.

## -parameters

### -param FramesToSkip [in]

Number of frames to skip from the start (current call point) of the back trace.

### -param FramesToCapture [in]

Number of frames to be captured.

### -param BackTrace [out]

Caller-allocated array in which pointers to the return addresses captured from the current stack trace are returned.

### -param BackTraceHash [out, optional]

Optional value that can be used to organize hash tables. If this parameter is NULL, **RtlCaptureStackBackTrace** doesn't compute and return a hash value.

This hash value is calculated based on the values of the pointers returned in the **BackTrace** array. Two identical stack traces will generate identical hash values.

## -returns

The number of captured frames.

## -remarks

**RtlCaptureStackBackTrace** captures a stack trace for the caller by walking the stack (walking back in call time), and recording information for each frame. Specifically, **RtlCaptureStackBackTrace** returns pointers to the return addresses of each call on the stack, where the first pointer in the **BackTrace** array points to the return address of the most recent call, and so on.

Back trace hash values can be used to quickly determine whether two stack traces are identical or different. You can use the hash returned in **BackTraceHash** to compare stack traces. If you don't want to use hashes, or want to compute your own hash values, set **BackTraceHash** to NULL.

Typically, on 64-bit computers, you can't capture the kernel stack in certain contexts when page faults aren't allowed. To enable walking the kernel stack on x64, set the [DisablePagingExecutive](/previous-versions/windows/it-pro/windows-server-2003/cc757875(v=ws.10)) Memory Management registry value to 1. The DisablePagingExecutive registry value is located under the following registry key: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management. This should only be done for temporary diagnosis purposes because it increases memory usage of the system.
