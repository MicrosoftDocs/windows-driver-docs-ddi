---
UID: NF:dbgeng.IDebugSystemObjects3.SetImplicitThreadDataOffset
title: IDebugSystemObjects3::SetImplicitThreadDataOffset (dbgeng.h)
description: The SetImplicitThreadDataOffset method sets the implicit thread for the current process.
old-location: debugger\setimplicitthreaddataoffset.htm
tech.root: debugger
ms.assetid: 1562a2f4-0eea-44fd-b350-ccc17d8cd65e
ms.date: 05/03/2018
ms.keywords: IDebugSystemObjects2 interface [Windows Debugging],SetImplicitThreadDataOffset method, IDebugSystemObjects2::SetImplicitThreadDataOffset, IDebugSystemObjects3 interface [Windows Debugging],SetImplicitThreadDataOffset method, IDebugSystemObjects3.SetImplicitThreadDataOffset, IDebugSystemObjects3::SetImplicitThreadDataOffset, IDebugSystemObjects4 interface [Windows Debugging],SetImplicitThreadDataOffset method, IDebugSystemObjects4::SetImplicitThreadDataOffset, IDebugSystemObjects_d78e5ee9-b18c-47a0-9987-41923aaa1aaf.xml, SetImplicitThreadDataOffset, SetImplicitThreadDataOffset method [Windows Debugging], SetImplicitThreadDataOffset method [Windows Debugging],IDebugSystemObjects2 interface, SetImplicitThreadDataOffset method [Windows Debugging],IDebugSystemObjects3 interface, SetImplicitThreadDataOffset method [Windows Debugging],IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects2::SetImplicitThreadDataOffset, dbgeng/IDebugSystemObjects3::SetImplicitThreadDataOffset, dbgeng/IDebugSystemObjects4::SetImplicitThreadDataOffset, debugger.setimplicitthreaddataoffset
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
- IDebugSystemObjects2.SetImplicitThreadDataOffset
- IDebugSystemObjects3.SetImplicitThreadDataOffset
- IDebugSystemObjects4.SetImplicitThreadDataOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::SetImplicitThreadDataOffset


## -description


The <b>SetImplicitThreadDataOffset</b> method sets the implicit thread for the current process.


## -parameters




### -param Offset [in]

Specifies the location in the target's memory address space of the data structure of the system thread that is to become the implicit thread for the current process.  If this is zero, the implicit thread for the current process is set to the default implicit thread.


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

<div class="alert"><b>Warning</b>    Because it is possible to use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsystemobjects4-setimplicitprocessdataoffset">SetImplicitProcessDataOffset</a> to set the implicit process independently of the implicit thread, the implicit thread might not belong to the implicit process.  This can cause errors if you attempt to access any of the user state for the implicit thread, because it will be incompatible with the virtual address space (specified by the implicit process).</div>
<div> </div>
For more information about the current implicit thread, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details on the KTHREAD structure and TEB, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.



