---
UID: NF:dbgeng.IDebugRegisters2.GetStackOffset
title: IDebugRegisters2::GetStackOffset (dbgeng.h)
description: The GetStackOffset method returns the current thread's current stack location.
old-location: debugger\getstackoffset.htm
tech.root: debugger
ms.assetid: 7368a2d6-fea3-411e-85d9-c09764bb3b8e
ms.date: 05/03/2018
keywords: ["IDebugRegisters2::GetStackOffset"]
ms.keywords: GetStackOffset, GetStackOffset method [Windows Debugging], GetStackOffset method [Windows Debugging],IDebugRegisters interface, GetStackOffset method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters interface [Windows Debugging],GetStackOffset method, IDebugRegisters2 interface [Windows Debugging],GetStackOffset method, IDebugRegisters2.GetStackOffset, IDebugRegisters2::GetStackOffset, IDebugRegisters::GetStackOffset, IDebugRegisters_40c9da48-e41f-4890-ace2-b15a2e1cc4ba.xml, dbgeng/IDebugRegisters2::GetStackOffset, dbgeng/IDebugRegisters::GetStackOffset, debugger.getstackoffset
f1_keywords:
 - "dbgeng/IDebugRegisters.GetStackOffset"
 - "IDebugRegisters.GetStackOffset"
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
- IDebugRegisters.GetStackOffset
- IDebugRegisters2.GetStackOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters2::GetStackOffset


## -description


The <b>GetStackOffset</b> method returns the current thread's current stack location.


## -parameters




### -param Offset [out]

Receives the location in the process's virtual address space of the current thread's current stack location.


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



The meaning of value returned by this method is architecture specific.

The method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getstackoffset2">GetStackOffset2</a> performs the same task as this method but also allows the register source to be specified.

For an overview of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">Registers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getstackoffset2">GetStackOffset2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>
 

 

