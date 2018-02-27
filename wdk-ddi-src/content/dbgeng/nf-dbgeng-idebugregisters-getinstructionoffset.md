---
UID: NF:dbgeng.IDebugRegisters.GetInstructionOffset
title: IDebugRegisters::GetInstructionOffset method
author: windows-driver-content
description: The GetInstructionOffset method returns the location of the current thread's current instruction.
old-location: debugger\getinstructionoffset.htm
old-project: debugger
ms.assetid: f82416c9-1f4a-4083-b4df-f0d97eae2127
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetInstructionOffset method [Windows Debugging], GetInstructionOffset method [Windows Debugging], IDebugRegisters interface, GetInstructionOffset method [Windows Debugging], IDebugRegisters2 interface, GetInstructionOffset,IDebugRegisters.GetInstructionOffset, IDebugRegisters, IDebugRegisters interface [Windows Debugging], GetInstructionOffset method, IDebugRegisters2 interface [Windows Debugging], GetInstructionOffset method, IDebugRegisters2::GetInstructionOffset, IDebugRegisters::GetInstructionOffset, IDebugRegisters_229180dd-2da4-4ff1-9284-520bef0b6843.xml, dbgeng/IDebugRegisters2::GetInstructionOffset, dbgeng/IDebugRegisters::GetInstructionOffset, debugger.getinstructionoffset
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugRegisters.GetInstructionOffset
-	IDebugRegisters2.GetInstructionOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugRegisters::GetInstructionOffset method


## -description


The <b>GetInstructionOffset</b> method returns the location of the current thread's current instruction.


## -syntax


````
HRESULT GetInstructionOffset(
  [out] PULONG64 Offset
);
````


## -parameters




### -param Offset [out]

Receives the location in the target's virtual address space of the target's current instruction.


## -returns



This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

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

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff546933">GetInstructionOffset2</a> performs the same task as this method but also allows the register source to be specified.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546933">GetInstructionOffset2</a>



<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters::GetInstructionOffset method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

