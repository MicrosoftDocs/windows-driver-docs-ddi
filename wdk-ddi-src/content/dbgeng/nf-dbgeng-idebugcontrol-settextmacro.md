---
UID: NF:dbgeng.IDebugControl.SetTextMacro
title: IDebugControl::SetTextMacro method
author: windows-driver-content
description: The SetTextMacro method sets the value of a fixed-name alias.
old-location: debugger\settextmacro.htm
old-project: Debugger
ms.assetid: 8319ab12-bb23-4de4-b3dc-afd3cd13d03e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: dbgeng/IDebugControl::SetTextMacro, IDebugControl2::SetTextMacro, IDebugControl, SetTextMacro method [Windows Debugging], SetTextMacro, dbgeng/IDebugControl2::SetTextMacro, IDebugControl_5eac09ea-004d-4231-b865-d191790880fc.xml, IDebugControl2 interface [Windows Debugging], SetTextMacro method, IDebugControl::SetTextMacro, SetTextMacro method [Windows Debugging], IDebugControl3 interface, IDebugControl interface [Windows Debugging], SetTextMacro method, IDebugControl3::SetTextMacro, IDebugControl3 interface [Windows Debugging], SetTextMacro method, SetTextMacro method [Windows Debugging], IDebugControl interface, SetTextMacro method [Windows Debugging], IDebugControl2 interface, debugger.settextmacro, dbgeng/IDebugControl3::SetTextMacro
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
-	IDebugControl.SetTextMacro
-	IDebugControl2.SetTextMacro
-	IDebugControl3.SetTextMacro
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl::SetTextMacro method


## -description


The <b>SetTextMacro</b>  method sets the value of a fixed-name alias.


## -syntax


````
HRESULT SetTextMacro(
  [in] ULONG Slot,
  [in] PCSTR Macro
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554663">r (Registers)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549270">GetTextMacro</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl::SetTextMacro method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

