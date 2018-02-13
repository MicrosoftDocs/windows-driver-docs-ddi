---
UID: NF:dbgeng.IDebugControl3.GetNumberExpressionSyntaxes
title: IDebugControl3::GetNumberExpressionSyntaxes method
author: windows-driver-content
description: The GetNumberExpressionSyntaxes method returns the number of expression syntaxes that are supported by the engine.
old-location: debugger\getnumberexpressionsyntaxes.htm
old-project: debugger
ms.assetid: eb96dd47-300a-49b7-b3c3-ee3bcb6662ba
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetNumberExpressionSyntaxes method [Windows Debugging], IDebugControl3 interface, GetNumberExpressionSyntaxes method [Windows Debugging], IDebugControl3::GetNumberExpressionSyntaxes, dbgeng/IDebugControl3::GetNumberExpressionSyntaxes, IDebugControl3, IDebugControl_af12dddf-1d15-4abf-8500-8beab99b69ea.xml, IDebugControl3 interface [Windows Debugging], GetNumberExpressionSyntaxes method, debugger.getnumberexpressionsyntaxes, GetNumberExpressionSyntaxes
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl3.GetNumberExpressionSyntaxes
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl3::GetNumberExpressionSyntaxes method


## -description


The <b>GetNumberExpressionSyntaxes</b> method returns the number of expression syntaxes that are supported by the engine.


## -syntax


````
HRESULT GetNumberExpressionSyntaxes(
  [out] PULONG Number
);
````


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



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556697">SetExpressionSyntaxByName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::GetNumberExpressionSyntaxes method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

