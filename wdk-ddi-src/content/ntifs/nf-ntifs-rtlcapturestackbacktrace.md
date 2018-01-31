---
UID: NF:ntifs.RtlCaptureStackBackTrace
title: RtlCaptureStackBackTrace function
author: windows-driver-content
description: The RtlCaptureStackBackTrace routine captures a stack back trace by walking up the stack and recording the information for each frame.
old-location: ifsk\rtlcapturestackbacktrace.htm
old-project: ifsk
ms.assetid: e4ad1eac-1788-4dfe-9444-f40e0de156c4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlCaptureStackBackTrace, rtlref_c329ad74-ebb1-478d-a0d2-fd2ae2c8da2a.xml, ntifs/RtlCaptureStackBackTrace, ifsk.rtlcapturestackbacktrace, RtlCaptureStackBackTrace routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtDll.dll
-	NtosKrnl.exe
-	API-MS-Win-Core-RTLSupport-l1-1-0.dll
-	API-MS-Win-Core-RTLSupport-l1-2-0.dll
apiname:
-	RtlCaptureStackBackTrace
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlCaptureStackBackTrace function


## -description


The <b>RtlCaptureStackBackTrace</b> routine captures a stack back trace by walking up the stack and recording the information for each frame.


## -syntax


````
USHORT RtlCaptureStackBackTrace(
  _In_      ULONG  FramesToSkip,
  _In_      ULONG  FramesToCapture,
  _Out_     PVOID  *BackTrace,
  _Out_opt_ PULONG BackTraceHash
);
````


## -parameters




#### - FramesToSkip [in]

The number of frames to skip from the start of the back trace.


#### - FramesToCapture [in]

The number of frames to be captured. 


#### - BackTrace [out]

An array of pointers captured from the current stack trace.


#### - BackTraceHash [out, optional]

An optional value that can be used to organize hash tables. If this parameter is <b>NULL</b>, no hash value is computed.

This value is calculated based on the values of the pointers returned in the <i>BackTrace</i> array. Two identical stack traces will generate identical hash values.


## -returns


The number of captured frames.


