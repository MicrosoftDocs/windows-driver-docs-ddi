---
UID: NF:dbgeng.IDebugRegisters2.GetFrameOffset2
title: IDebugRegisters2::GetFrameOffset2
author: windows-driver-content
description: The GetFrameOffset2 method returns the location of the stack frame for the current function.
old-location: debugger\getframeoffset2.htm
tech.root: debugger
ms.assetid: e0ab18ea-4447-4eee-bdf3-d251d4d4952f
ms.date: 5/3/2018
ms.keywords: GetFrameOffset2, GetFrameOffset2 method [Windows Debugging], GetFrameOffset2 method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters2 interface [Windows Debugging],GetFrameOffset2 method, IDebugRegisters2.GetFrameOffset2, IDebugRegisters2::GetFrameOffset2, IDebugRegisters_9b3855a5-d5e4-4485-81f3-1584b707f73a.xml, dbgeng/IDebugRegisters2::GetFrameOffset2, debugger.getframeoffset2
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugRegisters2.GetFrameOffset2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters2::GetFrameOffset2


## -description


The <b>GetFrameOffset2</b> method returns the location of the stack frame for the current function.


## -parameters




### -param Source [in]

Specifies the register source to query.

The possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Register source</th>
</tr>
<tr>
<td>
DEBUG_REGSRC_DEBUGGEE

</td>
<td>
Fetch register information from the target.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_EXPLICIT

</td>
<td>
Fetch register information from the current explicit <a href="https://msdn.microsoft.com/3690903c-4281-4c65-98b0-00ca22206168">register context</a>.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_FRAME

</td>
<td>
Fetch register information from the current scope's register context. 


<div class="alert"><b>Note</b>    Stack unwinding does not guarantee accurate updating of the register context, so the scope frame's register context might not be accurate in all cases.</div>
<div> </div>


</td>
</tr>
</table>
 


### -param Offset [out]

The location in the process's virtual address space of the stack frame for the current function.


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



The meaning of the value that is returned by this method is architecture-specific.

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff546806">GetFrameOffset</a> performs the same task as this method but always uses the target as the register source.

For an overview of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546806">GetFrameOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550835">IDebugRegisters2</a>
 

 

