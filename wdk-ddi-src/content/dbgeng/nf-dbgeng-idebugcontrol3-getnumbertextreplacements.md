---
UID: NF:dbgeng.IDebugControl3.GetNumberTextReplacements
title: IDebugControl3::GetNumberTextReplacements (dbgeng.h)
description: The GetNumberTextReplacements method returns the number of currently defined user-named and automatic aliases.
old-location: debugger\getnumbertextreplacements.htm
tech.root: debugger
ms.assetid: d15400a8-3d8d-48dd-86f0-4e53f8b04add
ms.date: 05/03/2018
ms.keywords: GetNumberTextReplacements, GetNumberTextReplacements method [Windows Debugging], GetNumberTextReplacements method [Windows Debugging],IDebugControl2 interface, GetNumberTextReplacements method [Windows Debugging],IDebugControl3 interface, IDebugControl2 interface [Windows Debugging],GetNumberTextReplacements method, IDebugControl2::GetNumberTextReplacements, IDebugControl3 interface [Windows Debugging],GetNumberTextReplacements method, IDebugControl3.GetNumberTextReplacements, IDebugControl3::GetNumberTextReplacements, IDebugControl_34139b78-b8a1-4096-a54c-7fdfac7024ce.xml, dbgeng/IDebugControl2::GetNumberTextReplacements, dbgeng/IDebugControl3::GetNumberTextReplacements, debugger.getnumbertextreplacements
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl2.GetNumberTextReplacements"
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
- IDebugControl2.GetNumberTextReplacements
- IDebugControl3.GetNumberTextReplacements
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetNumberTextReplacements


## -description


The <b>GetNumberTextReplacements</b> method returns the number of currently defined user-named and automatic aliases.  


## -parameters




### -param NumRepl [out]

Receives the total number of user-named and automatic aliases.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-gettextreplacement">GetTextReplacement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputtextreplacements">OutputTextReplacements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-removetextreplacements">RemoveTextReplacements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-settextreplacement">SetTextReplacement</a>
 

 

