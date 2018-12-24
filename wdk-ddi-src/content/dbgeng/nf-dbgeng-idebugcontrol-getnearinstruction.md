---
UID: NF:dbgeng.IDebugControl.GetNearInstruction
title: IDebugControl::GetNearInstruction
description: The GetNearInstruction method returns the location of a processor instruction relative to a given location.
old-location: debugger\getnearinstruction.htm
tech.root: debugger
ms.assetid: 76387681-cac6-4c35-9095-28942a856c30
ms.date: 05/03/2018
ms.keywords: GetNearInstruction, GetNearInstruction method [Windows Debugging], GetNearInstruction method [Windows Debugging],IDebugControl interface, GetNearInstruction method [Windows Debugging],IDebugControl2 interface, GetNearInstruction method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetNearInstruction method, IDebugControl.GetNearInstruction, IDebugControl2 interface [Windows Debugging],GetNearInstruction method, IDebugControl2::GetNearInstruction, IDebugControl3 interface [Windows Debugging],GetNearInstruction method, IDebugControl3::GetNearInstruction, IDebugControl::GetNearInstruction, IDebugControl_2c12e1fe-0f9b-45d6-9ff4-477bc42b2275.xml, dbgeng/IDebugControl2::GetNearInstruction, dbgeng/IDebugControl3::GetNearInstruction, dbgeng/IDebugControl::GetNearInstruction, debugger.getnearinstruction
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.GetNearInstruction
-	IDebugControl2.GetNearInstruction
-	IDebugControl3.GetNearInstruction
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::GetNearInstruction


## -description


The <b>GetNearInstruction</b> method returns the location of a processor instruction relative to a given location.


## -parameters




### -param Offset [in]

Specifies the location in the process's virtual address space from which to start looking for the desired instruction.


### -param Delta [in]

Specifies the number of instructions from <i>Offset</i> of the desired instruction.  If <i>Delta</i> is negative, the returned offset is before <i>Offset</i> (see the Remarks section for more information).


### -param NearOffset [out]

Receives the location in the process's virtual address space of the instruction that is <i>Delta</i> instructions away from <i>Offset</i>.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



On some architectures, like x86 and x64, the size of an instruction may vary.  On these architectures, when <i>Delta</i> is negative, the desired instruction location might not be uniquely defined.  In this case, the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> will search backward from <i>Offset</i> until it encounters a location such that there are the <i>Delta</i> number of instructions between that location and <i>Offset</i>.



