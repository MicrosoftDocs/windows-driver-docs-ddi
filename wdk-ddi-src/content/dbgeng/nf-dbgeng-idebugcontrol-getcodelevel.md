---
UID: NF:dbgeng.IDebugControl.GetCodeLevel
title: IDebugControl::GetCodeLevel
description: The GetCodeLevel method returns the current code level and is mainly used when stepping through code.
old-location: debugger\getcodelevel.htm
tech.root: debugger
ms.assetid: 965565ee-ef4c-4a1d-a6f1-77b6d63c6ee8
ms.date: 05/03/2018
ms.keywords: GetCodeLevel, GetCodeLevel method [Windows Debugging], GetCodeLevel method [Windows Debugging],IDebugControl interface, GetCodeLevel method [Windows Debugging],IDebugControl2 interface, GetCodeLevel method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetCodeLevel method, IDebugControl.GetCodeLevel, IDebugControl2 interface [Windows Debugging],GetCodeLevel method, IDebugControl2::GetCodeLevel, IDebugControl3 interface [Windows Debugging],GetCodeLevel method, IDebugControl3::GetCodeLevel, IDebugControl::GetCodeLevel, IDebugControl_8533dd3f-f004-4d89-9f02-b7835fc6169e.xml, dbgeng/IDebugControl2::GetCodeLevel, dbgeng/IDebugControl3::GetCodeLevel, dbgeng/IDebugControl::GetCodeLevel, debugger.getcodelevel
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
-	IDebugControl.GetCodeLevel
-	IDebugControl2.GetCodeLevel
-	IDebugControl3.GetCodeLevel
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::GetCodeLevel


## -description


The <b>GetCodeLevel</b> method returns the current code level and is mainly used when stepping through code.


## -parameters




### -param Level [out]

Receives the current code level.  <i>Level</i> can take one of the values in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_LEVEL_SOURCE

</td>
<td>
<i>Source mode</i>.  When stepping through code on the target, the size of a single step will be a line of source code.

</td>
</tr>
<tr>
<td>
DEBUG_LEVEL_ASSEMBLY

</td>
<td>
<i>Assembly mode</i>.  When stepping through code on the target, the size of a single step will be a single processor instruction.

</td>
</tr>
</table>
 


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



For more information about the code level, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556629">SetCodeLevel</a>
 

 

