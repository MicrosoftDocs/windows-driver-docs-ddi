---
UID: NF:dbgeng.IDebugControl.SetCodeLevel
title: IDebugControl::SetCodeLevel (dbgeng.h)
description: The SetCodeLevel method sets the current code level and is mainly used when stepping through code.
old-location: debugger\setcodelevel.htm
tech.root: debugger
ms.assetid: b2f318d2-9ee2-4b4b-86ff-4561f1bbe084
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetCodeLevel method, IDebugControl.SetCodeLevel, IDebugControl2 interface [Windows Debugging],SetCodeLevel method, IDebugControl2::SetCodeLevel, IDebugControl3 interface [Windows Debugging],SetCodeLevel method, IDebugControl3::SetCodeLevel, IDebugControl::SetCodeLevel, IDebugControl_40aa5eed-ef3f-4ec4-84eb-0cfec638bc4a.xml, SetCodeLevel, SetCodeLevel method [Windows Debugging], SetCodeLevel method [Windows Debugging],IDebugControl interface, SetCodeLevel method [Windows Debugging],IDebugControl2 interface, SetCodeLevel method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetCodeLevel, dbgeng/IDebugControl3::SetCodeLevel, dbgeng/IDebugControl::SetCodeLevel, debugger.setcodelevel
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
-	IDebugControl.SetCodeLevel
-	IDebugControl2.SetCodeLevel
-	IDebugControl3.SetCodeLevel
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::SetCodeLevel


## -description


The <b>SetCodeLevel</b> method sets the current code level and is mainly used when stepping through code.


## -parameters




### -param Level [in]

Specifies the current code level.  <i>Level</i> can take one of the values in the following table.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545670">GetCodeLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

