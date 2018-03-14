---
UID: NF:dbgeng.IDebugControl3.GetExpressionSyntax
title: IDebugControl3::GetExpressionSyntax method
author: windows-driver-content
description: The GetExpressionSyntax method returns the current syntax that the engine is using for evaluating expressions.
old-location: debugger\getexpressionsyntax.htm
old-project: debugger
ms.assetid: e04e4567-5ae6-4349-9876-0c2b55c340e0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetExpressionSyntax method [Windows Debugging], GetExpressionSyntax method [Windows Debugging], IDebugControl3 interface, GetExpressionSyntax,IDebugControl3.GetExpressionSyntax, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetExpressionSyntax method, IDebugControl3::GetExpressionSyntax, IDebugControl_9eae3270-fd1f-4d50-875b-3bd9908ba76d.xml, dbgeng/IDebugControl3::GetExpressionSyntax, debugger.getexpressionsyntax
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
-	IDebugControl3.GetExpressionSyntax
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetExpressionSyntax method


## -description


The <b>GetExpressionSyntax</b> method returns the current syntax that the engine is using for evaluating expressions.


## -syntax


````
HRESULT GetExpressionSyntax(
  [out] PULONG Flags
);
````


## -parameters




### -param Flags [out]

Receives the expression syntax.  It is set to one of the following values:





#### DEBUG_EXPR_MASM

Expressions will be evaluated according to MASM syntax. For details of this syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552157">MASM Numbers and Operators</a>.



#### DEBUG_EXPR_CPLUSPLUS

Expressions will be evaluated according to C++ syntax. For details of this syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540372">C++ Numbers and Operators</a>.


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
 




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556697">SetExpressionSyntaxByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556696">SetExpressionSyntax</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::GetExpressionSyntax method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

