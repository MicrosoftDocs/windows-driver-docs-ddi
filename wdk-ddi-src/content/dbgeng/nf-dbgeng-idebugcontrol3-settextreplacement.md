---
UID: NF:dbgeng.IDebugControl3.SetTextReplacement
title: IDebugControl3::SetTextReplacement (dbgeng.h)
description: The SetTextReplacement method sets the value of a user-named alias.
old-location: debugger\settextreplacement.htm
tech.root: debugger
ms.assetid: 00c82e73-5649-403b-9f07-81bdd2f6c756
ms.date: 05/03/2018
keywords: ["IDebugControl3::SetTextReplacement"]
ms.keywords: IDebugControl2 interface [Windows Debugging],SetTextReplacement method, IDebugControl2::SetTextReplacement, IDebugControl3 interface [Windows Debugging],SetTextReplacement method, IDebugControl3.SetTextReplacement, IDebugControl3::SetTextReplacement, IDebugControl_b53cd6ec-4cc4-45b2-96a0-b830bc7f8ca9.xml, SetTextReplacement, SetTextReplacement method [Windows Debugging], SetTextReplacement method [Windows Debugging],IDebugControl2 interface, SetTextReplacement method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetTextReplacement, dbgeng/IDebugControl3::SetTextReplacement, debugger.settextreplacement
f1_keywords:
 - "dbgeng/IDebugControl2.SetTextReplacement"
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
- IDebugControl2.SetTextReplacement
- IDebugControl3.SetTextReplacement
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::SetTextReplacement


## -description


The <b>SetTextReplacement</b>  method sets the value of a user-named alias.  


## -parameters




### -param SrcText [in]

Specifies the name of the user-named alias.  The <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> makes a copy of this string.  If <i>SrcText</i> is the same as the name of an automatic alias, the automatic alias is hidden by the new user-named alias.


### -param DstText [in, optional]

Specifies the value of the user-named alias.  The debugger engine makes a copy of this string.  If <i>DstText</i> is <b>NULL</b>, the user-named alias is removed.


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



Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>SrcText</i> with the value of the alias (specified by <i>DstText</i>).

If <i>SrcText</i> is an asterisk (<b>*</b>) and <i>DstText</i> is <b>NULL</b>, all user-named aliases are removed.  This is the same behavior as the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removetextreplacements">RemoveTextReplacements</a> method.

When an alias is changed by this method, the event callbacks are notified by passing the DEBUG_CES_TEXT_REPLACEMENTS flag to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> callback method.

For an overview of aliases used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-aliases">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/interacting-with-the-engine">Interacting with the Engine</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-gettextreplacement">GetTextReplacement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-outputtextreplacements">OutputTextReplacements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removetextreplacements">RemoveTextReplacements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-settextmacro">SetTextMacro</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/ad--delete-alias-">ad (Delete Alias)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/as--as--set-alias-">as, aS (Set Alias)</a>
 

 

