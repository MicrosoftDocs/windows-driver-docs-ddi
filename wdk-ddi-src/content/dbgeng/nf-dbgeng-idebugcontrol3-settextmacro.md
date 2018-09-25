---
UID: NF:dbgeng.IDebugControl3.SetTextMacro
title: IDebugControl3::SetTextMacro
author: windows-driver-content
description: The SetTextMacro method sets the value of a fixed-name alias.
old-location: debugger\settextmacro.htm
tech.root: debugger
ms.assetid: 8319ab12-bb23-4de4-b3dc-afd3cd13d03e
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetTextMacro method, IDebugControl2 interface [Windows Debugging],SetTextMacro method, IDebugControl2::SetTextMacro, IDebugControl3 interface [Windows Debugging],SetTextMacro method, IDebugControl3.SetTextMacro, IDebugControl3::SetTextMacro, IDebugControl::SetTextMacro, IDebugControl_5eac09ea-004d-4231-b865-d191790880fc.xml, SetTextMacro, SetTextMacro method [Windows Debugging], SetTextMacro method [Windows Debugging],IDebugControl interface, SetTextMacro method [Windows Debugging],IDebugControl2 interface, SetTextMacro method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetTextMacro, dbgeng/IDebugControl3::SetTextMacro, dbgeng/IDebugControl::SetTextMacro, debugger.settextmacro
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
-	IDebugControl.SetTextMacro
-	IDebugControl2.SetTextMacro
-	IDebugControl3.SetTextMacro
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::SetTextMacro


## -description


The <b>SetTextMacro</b>  method sets the value of a fixed-name alias.


## -parameters




### -param Slot [in]

Specifies the number of the fixed-name alias.  <i>Slot</i> can take the values 0, 1, ..., 9, that represent the fixed-name aliases <b>$u0</b>, <b>$u1</b>, ..., <b>$u9</b>.


### -param Macro [in]

Specifies the new value of the alias specified by <i>Slot</i>.  The <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> makes a copy of this string.


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



Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>Slot</i> with the value of the alias (specified by <i>Macro</i>).

For an overview of aliases used by the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549270">GetTextMacro</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554663">r (Registers)</a>
 

 

