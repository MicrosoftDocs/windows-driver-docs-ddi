---
UID: NF:dbgeng.IDebugRegisters.GetInstructionOffset
title: IDebugRegisters::GetInstructionOffset (dbgeng.h)
description: The GetInstructionOffset method returns the location of the current thread's current instruction.
old-location: debugger\getinstructionoffset.htm
tech.root: debugger
ms.assetid: f82416c9-1f4a-4083-b4df-f0d97eae2127
ms.date: 05/03/2018
ms.keywords: GetInstructionOffset, GetInstructionOffset method [Windows Debugging], GetInstructionOffset method [Windows Debugging],IDebugRegisters interface, GetInstructionOffset method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters interface [Windows Debugging],GetInstructionOffset method, IDebugRegisters.GetInstructionOffset, IDebugRegisters2 interface [Windows Debugging],GetInstructionOffset method, IDebugRegisters2::GetInstructionOffset, IDebugRegisters::GetInstructionOffset, IDebugRegisters_229180dd-2da4-4ff1-9284-520bef0b6843.xml, dbgeng/IDebugRegisters2::GetInstructionOffset, dbgeng/IDebugRegisters::GetInstructionOffset, debugger.getinstructionoffset
ms.topic: method
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
- IDebugRegisters.GetInstructionOffset
- IDebugRegisters2.GetInstructionOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters::GetInstructionOffset


## -description


The <b>GetInstructionOffset</b> method returns the location of the current thread's current instruction.


## -parameters




### -param Offset [out]

Receives the location in the target's virtual address space of the target's current instruction.


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



The meaning of the value returned by this method is architecture-dependent.  In particular, for an Itanium processor, the virtual address returned can indicate an address within a bundle.

The method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getinstructionoffset2">GetInstructionOffset2</a> performs the same task as this method but also allows the register source to be specified.

For an overview of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">Registers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getinstructionoffset2">GetInstructionOffset2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>
 

 

