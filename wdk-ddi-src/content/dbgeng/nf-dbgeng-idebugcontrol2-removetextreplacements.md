---
UID: NF:dbgeng.IDebugControl2.RemoveTextReplacements
title: IDebugControl2::RemoveTextReplacements (dbgeng.h)
description: The RemoveTextReplacements method removes all user-named aliases.
old-location: debugger\removetextreplacements.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::RemoveTextReplacements"]
ms.keywords: IDebugControl2 interface [Windows Debugging],RemoveTextReplacements method, IDebugControl2.RemoveTextReplacements, IDebugControl2::RemoveTextReplacements, IDebugControl3 interface [Windows Debugging],RemoveTextReplacements method, IDebugControl3::RemoveTextReplacements, IDebugControl_ba950bc7-3ed5-4e2e-913d-c743e1190482.xml, RemoveTextReplacements, RemoveTextReplacements method [Windows Debugging], RemoveTextReplacements method [Windows Debugging],IDebugControl2 interface, RemoveTextReplacements method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::RemoveTextReplacements, dbgeng/IDebugControl3::RemoveTextReplacements, debugger.removetextreplacements
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugControl2::RemoveTextReplacements
 - dbgeng/IDebugControl2::RemoveTextReplacements
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugControl2.RemoveTextReplacements
 - IDebugControl3.RemoveTextReplacements
---

# IDebugControl2::RemoveTextReplacements


## -description

The <b>RemoveTextReplacements</b> method removes all user-named aliases.

## -returns

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
 

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

For an overview of aliases used by the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a>, see <a href="/windows-hardware/drivers/debugger/using-aliases">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="/windows-hardware/drivers/debugger/interacting-with-the-engine">Interacting with the Engine</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumbertextreplacements">GetNumberTextReplacements</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-outputtextreplacements">OutputTextReplacements</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-settextreplacement">SetTextReplacement</a>



<a href="/windows-hardware/drivers/debugger/ad--delete-alias-">ad (Delete Alias)</a>
