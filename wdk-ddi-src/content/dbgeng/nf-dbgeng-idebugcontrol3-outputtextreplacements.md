---
UID: NF:dbgeng.IDebugControl3.OutputTextReplacements
title: IDebugControl3::OutputTextReplacements method
author: windows-driver-content
description: The OutputTextReplacements method prints all the currently defined user-named aliases to the debugger's output stream.
old-location: debugger\outputtextreplacements.htm
old-project: Debugger
ms.assetid: ea01fa02-8f4b-45c3-9690-30c8a1e6b4e5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.outputtextreplacements, IDebugControl3, IDebugControl2, IDebugControl3::OutputTextReplacements, OutputTextReplacements method [Windows Debugging], IDebugControl2 interface, OutputTextReplacements method [Windows Debugging], IDebugControl3 interface, dbgeng/IDebugControl3::OutputTextReplacements, dbgeng/IDebugControl2::OutputTextReplacements, IDebugControl2::OutputTextReplacements, IDebugControl2 interface [Windows Debugging], OutputTextReplacements method, OutputTextReplacements method [Windows Debugging], OutputTextReplacements, IDebugControl3 interface [Windows Debugging], OutputTextReplacements method, IDebugControl_57964e7b-e11a-446f-afab-7d3326fab695.xml
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
-	IDebugControl2.OutputTextReplacements
-	IDebugControl3.OutputTextReplacements
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::OutputTextReplacements method


## -description


The <b>OutputTextReplacements</b> method prints all the currently defined user-named aliases to the debugger's output stream.  


## -syntax


````
HRESULT OutputTextReplacements(
  [in] ULONG OutputControl,
  [in] ULONG Flags
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538014">al (List Aliases)</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugControl2::OutputTextReplacements method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

