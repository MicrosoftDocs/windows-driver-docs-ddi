---
UID: NF:dbgeng.IDebugSystemObjects2.GetThreadIdByDataOffset
title: IDebugSystemObjects2::GetThreadIdByDataOffset (dbgeng.h)
description: The GetThreadIdByDataOffset method returns the engine thread ID for the specified thread. The thread is specified by its system data structure.
old-location: debugger\getthreadidbydataoffset.htm
tech.root: debugger
ms.assetid: f559e0da-ca5c-4fea-aa17-257abfd45f96
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects2::GetThreadIdByDataOffset"]
ms.keywords: GetThreadIdByDataOffset, GetThreadIdByDataOffset method [Windows Debugging], GetThreadIdByDataOffset method [Windows Debugging],IDebugSystemObjects interface, GetThreadIdByDataOffset method [Windows Debugging],IDebugSystemObjects2 interface, GetThreadIdByDataOffset method [Windows Debugging],IDebugSystemObjects3 interface, GetThreadIdByDataOffset method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetThreadIdByDataOffset method, IDebugSystemObjects2 interface [Windows Debugging],GetThreadIdByDataOffset method, IDebugSystemObjects2.GetThreadIdByDataOffset, IDebugSystemObjects2::GetThreadIdByDataOffset, IDebugSystemObjects3 interface [Windows Debugging],GetThreadIdByDataOffset method, IDebugSystemObjects3::GetThreadIdByDataOffset, IDebugSystemObjects4 interface [Windows Debugging],GetThreadIdByDataOffset method, IDebugSystemObjects4::GetThreadIdByDataOffset, IDebugSystemObjects::GetThreadIdByDataOffset, IDebugSystemObjects_bb1b0f35-219b-4883-8df7-d90a96441720.xml, dbgeng/IDebugSystemObjects2::GetThreadIdByDataOffset, dbgeng/IDebugSystemObjects3::GetThreadIdByDataOffset, dbgeng/IDebugSystemObjects4::GetThreadIdByDataOffset, dbgeng/IDebugSystemObjects::GetThreadIdByDataOffset, debugger.getthreadidbydataoffset
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
 - IDebugSystemObjects2::GetThreadIdByDataOffset
 - dbgeng/IDebugSystemObjects2::GetThreadIdByDataOffset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetThreadIdByDataOffset
 - IDebugSystemObjects2.GetThreadIdByDataOffset
 - IDebugSystemObjects3.GetThreadIdByDataOffset
 - IDebugSystemObjects4.GetThreadIdByDataOffset
---

# IDebugSystemObjects2::GetThreadIdByDataOffset


## -description

The <b>GetThreadIdByDataOffset</b> method returns the engine thread ID for the specified thread.  The thread is specified by its system data structure.

## -parameters

### -param Offset 

[in]
Specifies the location of the system data structure for the thread.

### -param Id 

[out]
Receives the engine thread ID.

## -returns

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

In kernel-mode debugging, this method returns the engine thread ID for the virtual thread representing the processor on which the specified thread is executing.  If the thread is not executing on a processor, this method will fail. 

For more information about threads, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.

