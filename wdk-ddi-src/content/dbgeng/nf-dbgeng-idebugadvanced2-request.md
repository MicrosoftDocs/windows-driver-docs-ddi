---
UID: NF:dbgeng.IDebugAdvanced2.Request
title: IDebugAdvanced2::Request method
author: windows-driver-content
description: The Request method performs a variety of different operations.
old-location: debugger\request.htm
old-project: debugger
ms.assetid: efb3c93c-5405-418b-a063-afa8e5e9e59a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IDebugAdvanced2, IDebugAdvanced2 interface [Windows Debugging], Request method, IDebugAdvanced2::Request, IDebugAdvanced3 interface [Windows Debugging], Request method, IDebugAdvanced3::Request, IDebugAdvanced_8fbf249e-5550-42c0-b16d-d42aaa4de660.xml, Request method [Windows Debugging], Request method [Windows Debugging], IDebugAdvanced2 interface, Request method [Windows Debugging], IDebugAdvanced3 interface, Request,IDebugAdvanced2.Request, dbgeng/IDebugAdvanced2::Request, dbgeng/IDebugAdvanced3::Request, debugger.request
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugAdvanced2.Request
-	IDebugAdvanced3.Request
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugAdvanced2::Request method


## -description


The <b>Request</b> method performs a variety of different operations.


## -syntax


````
HRESULT Request(
  [in]            ULONG  Request,
  [in, optional]  PVOID  InBuffer,
  [in]            ULONG  InBufferSize,
  [out, optional] PVOID  OutBuffer,
  [in]            ULONG  OutBufferSize,
  [out, optional] PULONG OutSize
);
````


## -parameters




### -param Request [in]

Specifies which operation to perform.  <b>Request</b> can be one of the values in the following table.  Details of each operation can be found by following the link in the "Request" column.

<table>
<tr>
<th>Request</th>
<th>Action</th>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541597">DEBUG_REQUEST_SOURCE_PATH_HAS_SOURCE_SERVER</a>


</td>
<td>
Check the source path for a source server.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541606">DEBUG_REQUEST_TARGET_EXCEPTION_CONTEXT</a>


</td>
<td>
Return the <a href="https://msdn.microsoft.com/f14b6361-9962-4fa3-bb1a-dfde066754b9">thread context</a> for the stored event in a user-mode minidump file.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541623">DEBUG_REQUEST_TARGET_EXCEPTION_THREAD</a>


</td>
<td>
Return the operating system thread ID for the stored event in a user-mode minidump file.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541616">DEBUG_REQUEST_TARGET_EXCEPTION_RECORD</a>


</td>
<td>
Return the exception record for the stored event in a user-mode minidump file.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541553">DEBUG_REQUEST_GET_ADDITIONAL_CREATE_OPTIONS</a>


</td>
<td>
Return the default process creation options.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541586">DEBUG_REQUEST_SET_ADDITIONAL_CREATE_OPTIONS</a>


</td>
<td>
Set the default process creation options.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541563">DEBUG_REQUEST_GET_WIN32_MAJOR_MINOR_VERSIONS</a>


</td>
<td>
Return the version of Windows that is currently running on the target.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541575">DEBUG_REQUEST_READ_USER_MINIDUMP_STREAM</a>


</td>
<td>
Read a stream from a user-mode minidump target.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541602">DEBUG_REQUEST_TARGET_CAN_DETACH</a>


</td>
<td>
Check to see if it is possible for the debugger engine to detach from the current process (leaving the process running but no longer being debugged).

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541592">DEBUG_REQUEST_SET_LOCAL_IMPLICIT_COMMAND_LINE</a>


</td>
<td>
Set the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>'s implicit command line.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541561">DEBUG_REQUEST_GET_CAPTURED_EVENT_CODE_OFFSET</a>


</td>
<td>
Return the current event's instruction pointer.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541572">DEBUG_REQUEST_READ_CAPTURED_EVENT_CODE_STREAM</a>


</td>
<td>
Return up to 64 bytes of memory at the current event's instruction pointer.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541547">DEBUG_REQUEST_EXT_TYPED_DATA_ANSI</a>


</td>
<td>
Perform a variety of different operations that aid in the interpretation of typed data.

</td>
</tr>
</table>
 


### -param InBuffer [in, optional]

Specifies the input to this method.  The type and interpretation of the input depends on the <i>Request</i> parameter.


### -param InBufferSize [in]

Specifies the size of the input buffer <i>InBuffer</i>.  If the request requires no input, <i>InBufferSize</i> should be set to zero.


### -param OutBuffer [out, optional]

Receives the output from this method.  The type and interpretation of the output depends on the <i>Request</i> parameter.  If <i>OutBuffer</i> is <b>NULL</b>, the output is not returned.


### -param OutBufferSize [in]

Specifies the size of the output buffer <i>OutBufferSize</i>.  If the type of the output returned to <i>OutBuffer</i> has a known size, <i>OutBufferSize</i> is usually expected to be exactly that size, even if <i>OutBuffer</i> is set to <b>NULL</b>.


### -param OutSize [out, optional]

Receives the size of the output returned in the output buffer <i>OutBuffer</i>.  If <i>OutSize</i> is <b>NULL</b>, this information is not returned.


## -returns



The interpretation of the return value depends on the value of the <i>Request</i> parameter.  Unless otherwise stated, the following values may be returned.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the output would not fit in the output buffer <i>OutBuffer</i>, so truncated output was returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The size of the input buffer <i>InBufferSize</i> or the size of the output buffer <i>OutBufferSize</i> was not the expected value.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541597">DEBUG_REQUEST_SOURCE_PATH_HAS_SOURCE_SERVER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541616">DEBUG_REQUEST_TARGET_EXCEPTION_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541553">DEBUG_REQUEST_GET_ADDITIONAL_CREATE_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541602">DEBUG_REQUEST_TARGET_CAN_DETACH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541592">DEBUG_REQUEST_SET_LOCAL_IMPLICIT_COMMAND_LINE</a>



<a href="..\dbgeng\nn-dbgeng-idebugadvanced3.md">IDebugAdvanced3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541575">DEBUG_REQUEST_READ_USER_MINIDUMP_STREAM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541561">DEBUG_REQUEST_GET_CAPTURED_EVENT_CODE_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541606">DEBUG_REQUEST_TARGET_EXCEPTION_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541572">DEBUG_REQUEST_READ_CAPTURED_EVENT_CODE_STREAM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541563">DEBUG_REQUEST_GET_WIN32_MAJOR_MINOR_VERSIONS</a>



<a href="..\dbgeng\nn-dbgeng-idebugadvanced2.md">IDebugAdvanced2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541586">DEBUG_REQUEST_SET_ADDITIONAL_CREATE_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541623">DEBUG_REQUEST_TARGET_EXCEPTION_THREAD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugAdvanced2::Request method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

