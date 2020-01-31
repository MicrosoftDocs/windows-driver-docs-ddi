---
UID: NF:dbgeng.IDebugRegisters.GetFrameOffset
title: IDebugRegisters::GetFrameOffset (dbgeng.h)
description: The GetFrameOffset method returns the location of the stack frame for the current function.
old-location: debugger\getframeoffset.htm
tech.root: debugger
ms.assetid: 09473106-3ab8-43ee-a424-2930b6bd3fcf
ms.date: 05/03/2018
ms.keywords: GetFrameOffset, GetFrameOffset method [Windows Debugging], GetFrameOffset method [Windows Debugging],IDebugRegisters interface, GetFrameOffset method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters interface [Windows Debugging],GetFrameOffset method, IDebugRegisters.GetFrameOffset, IDebugRegisters2 interface [Windows Debugging],GetFrameOffset method, IDebugRegisters2::GetFrameOffset, IDebugRegisters::GetFrameOffset, IDebugRegisters_c3f31f5b-76d4-4910-b1a1-f3050c20e815.xml, dbgeng/IDebugRegisters2::GetFrameOffset, dbgeng/IDebugRegisters::GetFrameOffset, debugger.getframeoffset
f1_keywords:
 - "dbgeng/IDebugRegisters.GetFrameOffset"
req.header: dbgeng.h
req.include-header: DbgEng.h
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
- IDebugRegisters.GetFrameOffset
- IDebugRegisters2.GetFrameOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters::GetFrameOffset


## -description


The <b>GetFrameOffset</b> method returns the location of the stack frame for the current function.


## -parameters




### -param Offset [out]

The location in the target's virtual address space of the stack frame for the current function.


## -returns



This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">HRESULT Values</a>.

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



The meaning of value returned by this method is architecture-specific.

The method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getframeoffset2">GetFrameOffset2</a> performs the same task as this method but also allows the register source to be specified.

For an overview of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">Registers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getframeoffset2">GetFrameOffset2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>
 

 

