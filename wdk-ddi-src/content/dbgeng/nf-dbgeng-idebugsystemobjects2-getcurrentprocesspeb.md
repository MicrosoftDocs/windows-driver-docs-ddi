---
UID: NF:dbgeng.IDebugSystemObjects2.GetCurrentProcessPeb
title: IDebugSystemObjects2::GetCurrentProcessPeb (dbgeng.h)
description: The GetCurrentProcessPeb method returns the process environment block (PEB) of the current process.
old-location: debugger\getcurrentprocesspeb.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects2::GetCurrentProcessPeb"]
ms.keywords: GetCurrentProcessPeb, GetCurrentProcessPeb method [Windows Debugging], GetCurrentProcessPeb method [Windows Debugging],IDebugSystemObjects interface, GetCurrentProcessPeb method [Windows Debugging],IDebugSystemObjects2 interface, GetCurrentProcessPeb method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentProcessPeb method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetCurrentProcessPeb method, IDebugSystemObjects2 interface [Windows Debugging],GetCurrentProcessPeb method, IDebugSystemObjects2.GetCurrentProcessPeb, IDebugSystemObjects2::GetCurrentProcessPeb, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentProcessPeb method, IDebugSystemObjects3::GetCurrentProcessPeb, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentProcessPeb method, IDebugSystemObjects4::GetCurrentProcessPeb, IDebugSystemObjects::GetCurrentProcessPeb, IDebugSystemObjects_fd672d78-9254-4f24-9f10-99a91d825f2e.xml, dbgeng/IDebugSystemObjects2::GetCurrentProcessPeb, dbgeng/IDebugSystemObjects3::GetCurrentProcessPeb, dbgeng/IDebugSystemObjects4::GetCurrentProcessPeb, dbgeng/IDebugSystemObjects::GetCurrentProcessPeb, debugger.getcurrentprocesspeb
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
 - IDebugSystemObjects2::GetCurrentProcessPeb
 - dbgeng/IDebugSystemObjects2::GetCurrentProcessPeb
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetCurrentProcessPeb
 - IDebugSystemObjects2.GetCurrentProcessPeb
 - IDebugSystemObjects3.GetCurrentProcessPeb
 - IDebugSystemObjects4.GetCurrentProcessPeb
---

# IDebugSystemObjects2::GetCurrentProcessPeb


## -description

The <b>GetCurrentProcessPeb</b> method returns the process environment block (PEB) of the current process.

## -parameters

### -param Offset 

[out]
Receives the location in the target's virtual address space of the PEB of the current process.

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

In user-mode debugging, this method provides the same information as <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentprocessdataoffset">GetCurrentProcessDataOffset</a>.

In kernel-mode debugging, the location returned is that of the PEB structure for the system process in which the last event occurred.

<div class="alert"><b>Note</b>    In kernel mode, the current process of the target is always the single virtual process the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a> created for the kernel.  However, because events may occur in different system processes, the PEB location returned by this method may change.</div>
<div> </div>
For more information about processes, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.
