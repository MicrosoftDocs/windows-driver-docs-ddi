---
UID: NF:evntrace.OpenTraceW
title: OpenTraceW function
author: windows-driver-content
description: TBD
ms.assetid: 1aafed54-88ce-41cd-b392-088ae6ed3f95
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: OpenTraceW
req.header: evntrace.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:NtosKrnl.exe
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	OpenTraceW
product: Windows
targetos: Windows

---

# OpenTraceW function


## -description

The **OpenTrace** function opens a real-time trace session or log file for consuming.

## -parameters

### -param Logfile
[_Inout_] Pointer to an [EVENT_TRACE_LOGFILE](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364089) structure. The structure specifies the source from which to consume events (from a log file or the session in real time) and specifies the callbacks the consumer wants to use to receive the events. .

## -returns
If the function succeeds, it returns a handle to the trace.
If the function fails, it returns INVALID_PROCESSTRACE_HANDLE.
>Note  
If your code base supports Windows 7 and Windows Vista, and also supports earlier operating systems such as Windows XP and Windows Server 2003, do not use the constants described above. Instead, determine the operating system on which you are running and compare the return value to the following values.
Operating system
|Application|Return value to compare|
|---|---|
|Windows 7 and Windows Vista| 32-bit 0x00000000FFFFFFFF|
|Windows 7 and Windows Vista|64-bit 0XFFFFFFFFFFFFFFFF|
|Windows XP and Windows Server 2003 | 32- or 64-bit 0XFFFFFFFFFFFFFFFF|
 
If the function returns INVALID_PROCESSTRACE_HANDLE, you can use the GetLastError function to obtain extended error information. The following table lists some common errors and their causes.
|Return code|Description|
|---|---|
|ERROR_INVALID_PARAMETER|The Logfile parameter is NULL.|
|ERROR_BAD_PATHNAME |If you did not specify the LoggerName member of EVENT_TRACE_LOGFILE, you must specify a valid log file name.|
|ERROR_ACCESS_DENIED|Only users with administrative privileges, users in the Performance Log Users group, and services running as LocalSystem, LocalService, NetworkService can consume events in real time. To grant a restricted user the ability to consume events in real time, add them to the Performance Log Users group. Windows XP and Windows 2000:  Anyone can consume real time events.|

## -remarks
Consumers call this function.
After calling OpenTrace, call the ProcessTrace function to process the events. When you have finished processing events, call the CloseTrace function.
Note that you can process events from only one real-time session.
Windows Vista and earlier: If the function fails it will returns INVALID_HANDLE_VALUE. To avoid compile-time errors, cast INVALID_HANDLE_VALUE to TRACEHANDLE as follows: (TRACEHANDLE)INVALID_HANDLE_VALUE.

For an example that uses OpenTrace, see Using [TdhFormatProperty to Consume Event Data](https://msdn.microsoft.com/en-us/library/windows/desktop/ee441328) or [Retrieving Event Data Using MOF](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364114)

## -see-also

[CloseTrace]() 

[EVENT_TRACE_LOGFILE](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364089)