---
UID: NF:dbgeng.IDebugControl2.OutputTextReplacements
title: IDebugControl2::OutputTextReplacements
description: The OutputTextReplacements method prints all the currently defined user-named aliases to the debugger's output stream.
old-location: debugger\outputtextreplacements.htm
tech.root: debugger
ms.assetid: ea01fa02-8f4b-45c3-9690-30c8a1e6b4e5
ms.date: 05/03/2018
ms.keywords: IDebugControl2 interface [Windows Debugging],OutputTextReplacements method, IDebugControl2.OutputTextReplacements, IDebugControl2::OutputTextReplacements, IDebugControl3 interface [Windows Debugging],OutputTextReplacements method, IDebugControl3::OutputTextReplacements, IDebugControl_57964e7b-e11a-446f-afab-7d3326fab695.xml, OutputTextReplacements, OutputTextReplacements method [Windows Debugging], OutputTextReplacements method [Windows Debugging],IDebugControl2 interface, OutputTextReplacements method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::OutputTextReplacements, dbgeng/IDebugControl3::OutputTextReplacements, debugger.outputtextreplacements
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
-	IDebugControl2.OutputTextReplacements
-	IDebugControl3.OutputTextReplacements
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::OutputTextReplacements


## -description


The <b>OutputTextReplacements</b> method prints all the currently defined user-named aliases to the debugger's output stream.  


## -parameters




### -param OutputControl [in]

Specifies the output control to use when printing the aliases.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


### -param Flags [in]

Must be set to DEBUG_OUT_TEXT_REPL_DEFAULT.


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



For an overview of aliases used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538014">al (List Aliases)</a>
 

 

