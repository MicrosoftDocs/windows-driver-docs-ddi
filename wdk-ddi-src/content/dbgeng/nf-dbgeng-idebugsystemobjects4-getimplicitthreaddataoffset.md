---
UID: NF:dbgeng.IDebugSystemObjects4.GetImplicitThreadDataOffset
title: IDebugSystemObjects4::GetImplicitThreadDataOffset (dbgeng.h)
description: The GetImplicitThreadDataOffset method returns the implicit thread for the current process.
old-location: debugger\getimplicitthreaddataoffset.htm
tech.root: debugger
ms.assetid: fe7a1afe-dc87-412c-9e35-4a1af05f9474
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects4::GetImplicitThreadDataOffset"]
ms.keywords: GetImplicitThreadDataOffset, GetImplicitThreadDataOffset method [Windows Debugging], GetImplicitThreadDataOffset method [Windows Debugging],IDebugSystemObjects2 interface, GetImplicitThreadDataOffset method [Windows Debugging],IDebugSystemObjects3 interface, GetImplicitThreadDataOffset method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects2 interface [Windows Debugging],GetImplicitThreadDataOffset method, IDebugSystemObjects2::GetImplicitThreadDataOffset, IDebugSystemObjects3 interface [Windows Debugging],GetImplicitThreadDataOffset method, IDebugSystemObjects3::GetImplicitThreadDataOffset, IDebugSystemObjects4 interface [Windows Debugging],GetImplicitThreadDataOffset method, IDebugSystemObjects4.GetImplicitThreadDataOffset, IDebugSystemObjects4::GetImplicitThreadDataOffset, IDebugSystemObjects_fd957a10-62ec-464c-b5d0-c1b36a13013f.xml, dbgeng/IDebugSystemObjects2::GetImplicitThreadDataOffset, dbgeng/IDebugSystemObjects3::GetImplicitThreadDataOffset, dbgeng/IDebugSystemObjects4::GetImplicitThreadDataOffset, debugger.getimplicitthreaddataoffset
f1_keywords:
 - "dbgeng/IDebugSystemObjects2.GetImplicitThreadDataOffset"
 - "IDebugSystemObjects2.GetImplicitThreadDataOffset"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSystemObjects2.GetImplicitThreadDataOffset
- IDebugSystemObjects3.GetImplicitThreadDataOffset
- IDebugSystemObjects4.GetImplicitThreadDataOffset
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects4::GetImplicitThreadDataOffset


## -description


The <b>GetImplicitThreadDataOffset</b> method returns the implicit thread for the current process.


## -parameters




### -param Offset 
[out]
Receives the location in the target's memory address space of the data structure of the system thread that is the implicit thread for the current process.


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



In kernel-mode debugging, the data structure is the KTHREAD structure for the process.

In user-mode debugging, the data structure is the thread environment block (TEB) for the process.

For more information about the implicit thread, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details on the KTHREAD structure and TEB, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.



