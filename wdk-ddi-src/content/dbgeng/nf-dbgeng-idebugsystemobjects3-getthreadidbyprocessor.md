---
UID: NF:dbgeng.IDebugSystemObjects3.GetThreadIdByProcessor
title: IDebugSystemObjects3::GetThreadIdByProcessor (dbgeng.h)
description: The GetThreadIdByProcessor method returns the engine thread ID for the kernel-modevirtual thread corresponding to the specified processor.
old-location: debugger\getthreadidbyprocessor.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects3::GetThreadIdByProcessor"]
ms.keywords: GetThreadIdByProcessor, GetThreadIdByProcessor method [Windows Debugging], GetThreadIdByProcessor method [Windows Debugging],IDebugSystemObjects interface, GetThreadIdByProcessor method [Windows Debugging],IDebugSystemObjects2 interface, GetThreadIdByProcessor method [Windows Debugging],IDebugSystemObjects3 interface, GetThreadIdByProcessor method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetThreadIdByProcessor method, IDebugSystemObjects2 interface [Windows Debugging],GetThreadIdByProcessor method, IDebugSystemObjects2::GetThreadIdByProcessor, IDebugSystemObjects3 interface [Windows Debugging],GetThreadIdByProcessor method, IDebugSystemObjects3.GetThreadIdByProcessor, IDebugSystemObjects3::GetThreadIdByProcessor, IDebugSystemObjects4 interface [Windows Debugging],GetThreadIdByProcessor method, IDebugSystemObjects4::GetThreadIdByProcessor, IDebugSystemObjects::GetThreadIdByProcessor, IDebugSystemObjects_59fff866-93b2-48fb-8f49-bf778e2f0f7f.xml, dbgeng/IDebugSystemObjects2::GetThreadIdByProcessor, dbgeng/IDebugSystemObjects3::GetThreadIdByProcessor, dbgeng/IDebugSystemObjects4::GetThreadIdByProcessor, dbgeng/IDebugSystemObjects::GetThreadIdByProcessor, debugger.getthreadidbyprocessor
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugSystemObjects3::GetThreadIdByProcessor
 - dbgeng/IDebugSystemObjects3::GetThreadIdByProcessor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetThreadIdByProcessor
 - IDebugSystemObjects2.GetThreadIdByProcessor
 - IDebugSystemObjects3.GetThreadIdByProcessor
 - IDebugSystemObjects4.GetThreadIdByProcessor
---

# IDebugSystemObjects3::GetThreadIdByProcessor


## -description

The <b>GetThreadIdByProcessor</b> method returns the engine thread ID for the kernel-modevirtual thread corresponding to the specified processor.

## -parameters

### -param Processor 

[in]
Specifies the processor corresponding to the desired thread.

### -param Id 

[out]
Receives the engine thread ID.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
</table>

## -remarks

This method is only available in kernel-mode debugging.

For more information about threads, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.
