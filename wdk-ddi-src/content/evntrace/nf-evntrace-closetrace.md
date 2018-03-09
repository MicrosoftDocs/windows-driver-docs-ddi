---
UID: NF:evntrace.CloseTrace
title: CloseTrace function
author: windows-driver-content
description: TBD
ms.assetid: cf01c57d-82ed-4205-bc17-db31c4e6c044
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: CloseTrace
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
-	CloseTrace
product: Windows
targetos: Windows

---

# CloseTrace function

## -description

Closes a trace previously opened by calling [**OpenTrace**](nf-evntrace-opentracew.md).

## -parameters

### -param TraceHandle
Handle to the trace to close. The OpenTrace function returns this handle.

## -returns
This function returns a ULONG value.
If the function succeeds, the return value is ERROR_SUCCESS.
If the function fails, the return value is one of the [system error codes](https://msdn.microsoft.com/en-us/library/windows/desktop/ms681381). The following table includes some common errors and their causes.

|Return code|Description|
|---|---|
|ERROR_INVALID_HANDLE|One of the following is true:<li>TraceHandle is NULL.</li><li>TraceHandle is INVALID_HANDLE_VALUE.</li>|
|ERROR_BUSY|Prior to Windows Vista, you cannot close the trace until the ProcessTrace function completes. |
|ERROR_CTX_CLOSE_PENDING|The call was successful. The ProcessTrace function will stop after it has processed all real-time events in its buffers (it will not receive any new events).|

## -remarks

Consumers call this function.
If you are processing events from a log file, you call this function only after the [**ProcessTrace**](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364093) function returns. However, if you are processing real-time events, you can call this function before **ProcessTrace** returns. If you call this function before **ProcessTrace** returns, the **CloseTrace** function returns ERROR_CTX_CLOSE_PENDING. The ERROR_CTX_CLOSE_PENDING code indicates that the **CloseTrace** function call was successful; the **ProcessTrace** function will stop processing events after it processes all events in its buffers (**ProcessTrace** will not receive any new events after you call the **CloseTrace** function). You can call the **CloseTrace** function from your [BufferCallback(https://msdn.microsoft.com/en-us/library/windows/desktop/aa363685), [EventCallback](https://msdn.microsoft.com/en-us/library/windows/desktop/aa363721), or [EventClassCallback](https://msdn.microsoft.com/en-us/library/windows/desktop/aa363722) callback.
If you are processing events from a log file, you call this function only after the **ProcessTrace**(https://msdn.microsoft.com/en-us/library/windows/desktop/aa364093) function returns. However, if you are processing real-time events, you can call this function before **ProcessTrace** returns. If you call this function before **ProcessTrace** returns, the **CloseTrace** function returns ERROR_CTX_CLOSE_PENDING. The ERROR_CTX_CLOSE_PENDING code indicates that the **CloseTrace** function call was successful; the **ProcessTrace** function will stop processing events after it processes all events in its buffers (**ProcessTrace** will not receive any new events after you call the **CloseTrace** function). You can call the **CloseTrace** function from your [BufferCallback(https://msdn.microsoft.com/en-us/library/windows/desktop/aa363685), [EventCallback](https://msdn.microsoft.com/en-us/library/windows/desktop/aa363721), or [EventClassCallback](https://msdn.microsoft.com/en-us/library/windows/desktop/aa363722) callback.
Prior to Windows Vista:  You can call **CloseTrace** only after [**ProcessTrace**](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364093) returns.
Examples
For an example that uses **CloseTrace**, see [Retrieving Event Data Using MOF](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364114(v=vs.85).aspx).

## -see-also
[**OpenTrace**](nf-evntrace-opentracew.md)