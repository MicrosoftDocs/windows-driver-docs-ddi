---
UID: NF:dbgeng.IDebugControl3.GetNumberExpressionSyntaxes
title: IDebugControl3::GetNumberExpressionSyntaxes (dbgeng.h)
description: The GetNumberExpressionSyntaxes method returns the number of expression syntaxes that are supported by the engine.
old-location: debugger\getnumberexpressionsyntaxes.htm
tech.root: debugger
ms.assetid: eb96dd47-300a-49b7-b3c3-ee3bcb6662ba
ms.date: 05/03/2018
ms.keywords: GetNumberExpressionSyntaxes, GetNumberExpressionSyntaxes method [Windows Debugging], GetNumberExpressionSyntaxes method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],GetNumberExpressionSyntaxes method, IDebugControl3.GetNumberExpressionSyntaxes, IDebugControl3::GetNumberExpressionSyntaxes, IDebugControl_af12dddf-1d15-4abf-8500-8beab99b69ea.xml, dbgeng/IDebugControl3::GetNumberExpressionSyntaxes, debugger.getnumberexpressionsyntaxes
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
-	IDebugControl3.GetNumberExpressionSyntaxes
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetNumberExpressionSyntaxes


## -description


The <b>GetNumberExpressionSyntaxes</b> method returns the number of expression syntaxes that are supported by the engine.


## -parameters




### -param Number [out]

Receives the number of expression syntaxes.


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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546708">GetExpressionSyntaxNames</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556697">SetExpressionSyntaxByName</a>
 

 

