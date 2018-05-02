---
UID: NF:dbgeng.IDebugRegisters2.GetStackOffset2
title: IDebugRegisters2::GetStackOffset2
author: windows-driver-content
description: The GetStackOffset2 method returns the current thread's current stack location.
old-location: debugger\getstackoffset2.htm
old-project: debugger
ms.assetid: c90119a8-c93b-4432-b164-b1f4c562ef2d
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetStackOffset2, GetStackOffset2 method [Windows Debugging], GetStackOffset2 method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters2 interface [Windows Debugging],GetStackOffset2 method, IDebugRegisters2.GetStackOffset2, IDebugRegisters2::GetStackOffset2, IDebugRegisters_ec4e5846-b785-4b82-9670-04e7087b7d99.xml, dbgeng/IDebugRegisters2::GetStackOffset2, debugger.getstackoffset2
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
-	IDebugRegisters2.GetStackOffset2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters2::GetStackOffset2


## -description


The <b>GetStackOffset2</b> method returns the current thread's current stack location.


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

Receives the location in the process's virtual address space of the current thread's current stack.


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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548403">GetStackOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550835">IDebugRegisters2</a>
 

 

