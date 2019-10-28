---
UID: NF:dbgeng.IDebugControl3.OutputTextReplacements
title: IDebugControl3::OutputTextReplacements (dbgeng.h)
description: The OutputTextReplacements method prints all the currently defined user-named aliases to the debugger's output stream.
old-location: debugger\outputtextreplacements.htm
tech.root: debugger
ms.assetid: ea01fa02-8f4b-45c3-9690-30c8a1e6b4e5
ms.date: 05/03/2018
ms.keywords: IDebugControl2 interface [Windows Debugging],OutputTextReplacements method, IDebugControl2::OutputTextReplacements, IDebugControl3 interface [Windows Debugging],OutputTextReplacements method, IDebugControl3.OutputTextReplacements, IDebugControl3::OutputTextReplacements, IDebugControl_57964e7b-e11a-446f-afab-7d3326fab695.xml, OutputTextReplacements, OutputTextReplacements method [Windows Debugging], OutputTextReplacements method [Windows Debugging],IDebugControl2 interface, OutputTextReplacements method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::OutputTextReplacements, dbgeng/IDebugControl3::OutputTextReplacements, debugger.outputtextreplacements
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl2.OutputTextReplacements"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl2.OutputTextReplacements
- IDebugControl3.OutputTextReplacements
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::OutputTextReplacements


## -description


The <b>OutputTextReplacements</b> method prints all the currently defined user-named aliases to the debugger's output stream.  


## -parameters




### -param OutputControl [in]

Specifies the output control to use when printing the aliases.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.


### -param Flags [in]

Must be set to DEBUG_OUT_TEXT_REPL_DEFAULT.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



For an overview of aliases used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-aliases">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/interacting-with-the-engine">Interacting with the Engine</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumbertextreplacements">GetNumberTextReplacements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-gettextreplacement">GetTextReplacement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removetextreplacements">RemoveTextReplacements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-settextreplacement">SetTextReplacement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/al--list-aliases-">al (List Aliases)</a>
 

 

