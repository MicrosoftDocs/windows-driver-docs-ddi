---
UID: NF:dbgeng.IDebugSystemObjects2.SetImplicitProcessDataOffset
title: IDebugSystemObjects2::SetImplicitProcessDataOffset (dbgeng.h)
description: The SetImplicitProcessDataOffset method sets the implicit process for the current target.
old-location: debugger\setimplicitprocessdataoffset.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects2::SetImplicitProcessDataOffset"]
ms.keywords: IDebugSystemObjects2 interface [Windows Debugging],SetImplicitProcessDataOffset method, IDebugSystemObjects2.SetImplicitProcessDataOffset, IDebugSystemObjects2::SetImplicitProcessDataOffset, IDebugSystemObjects3 interface [Windows Debugging],SetImplicitProcessDataOffset method, IDebugSystemObjects3::SetImplicitProcessDataOffset, IDebugSystemObjects4 interface [Windows Debugging],SetImplicitProcessDataOffset method, IDebugSystemObjects4::SetImplicitProcessDataOffset, IDebugSystemObjects_10effa04-b87c-4555-9860-c2d5057a2529.xml, SetImplicitProcessDataOffset, SetImplicitProcessDataOffset method [Windows Debugging], SetImplicitProcessDataOffset method [Windows Debugging],IDebugSystemObjects2 interface, SetImplicitProcessDataOffset method [Windows Debugging],IDebugSystemObjects3 interface, SetImplicitProcessDataOffset method [Windows Debugging],IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects2::SetImplicitProcessDataOffset, dbgeng/IDebugSystemObjects3::SetImplicitProcessDataOffset, dbgeng/IDebugSystemObjects4::SetImplicitProcessDataOffset, debugger.setimplicitprocessdataoffset
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
 - IDebugSystemObjects2::SetImplicitProcessDataOffset
 - dbgeng/IDebugSystemObjects2::SetImplicitProcessDataOffset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects2.SetImplicitProcessDataOffset
 - IDebugSystemObjects3.SetImplicitProcessDataOffset
 - IDebugSystemObjects4.SetImplicitProcessDataOffset
---

# IDebugSystemObjects2::SetImplicitProcessDataOffset


## -description

The <b>SetImplicitProcessDataOffset</b> method sets the implicit process for the current target.

## -parameters

### -param Offset 

[in]
Specifies the location in the target's memory address space of the data structure of the system process that is to become the implicit process for the current target.  If this is zero, the implicit process for the current target is set to the default implicit process.

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

In kernel-mode debugging, the data structure is the KPROCESS structure for the process.

In user-mode debugging, the data structure is the process environment block (PEB) for the process.

<div class="alert"><b>Warning</b>    Because it is possible to use <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-setimplicitthreaddataoffset">SetImplicitThreadDataOffset</a> to set the implicit thread independently of the implicit process, the implicit thread might not belong to the implicit process.  This can cause errors if you attempt to access any of the user state for the implicit thread, because it will be incompatible with the virtual address space (specified by the implicit process).</div>
<div> </div>
For more information about the current implicit process, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details on the KPROCESS and PEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.
