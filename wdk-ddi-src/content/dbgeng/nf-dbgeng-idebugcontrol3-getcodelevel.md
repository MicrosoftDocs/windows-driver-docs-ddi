---
UID: NF:dbgeng.IDebugControl3.GetCodeLevel
title: IDebugControl3::GetCodeLevel (dbgeng.h)
description: The GetCodeLevel method returns the current code level and is mainly used when stepping through code.
old-location: debugger\getcodelevel.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetCodeLevel"]
ms.keywords: GetCodeLevel, GetCodeLevel method [Windows Debugging], GetCodeLevel method [Windows Debugging],IDebugControl interface, GetCodeLevel method [Windows Debugging],IDebugControl2 interface, GetCodeLevel method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetCodeLevel method, IDebugControl2 interface [Windows Debugging],GetCodeLevel method, IDebugControl2::GetCodeLevel, IDebugControl3 interface [Windows Debugging],GetCodeLevel method, IDebugControl3.GetCodeLevel, IDebugControl3::GetCodeLevel, IDebugControl::GetCodeLevel, IDebugControl_8533dd3f-f004-4d89-9f02-b7835fc6169e.xml, dbgeng/IDebugControl2::GetCodeLevel, dbgeng/IDebugControl3::GetCodeLevel, dbgeng/IDebugControl::GetCodeLevel, debugger.getcodelevel
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
 - IDebugControl3::GetCodeLevel
 - dbgeng/IDebugControl3::GetCodeLevel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl3::GetCodeLevel
---

# IDebugControl3::GetCodeLevel


## -description

The <b>GetCodeLevel</b> method returns the current code level and is mainly used when stepping through code.

## -parameters

### -param Level 

[out]
Receives the current code level.  <i>Level</i> can take one of the values in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_LEVEL_SOURCE

</td>
<td>
<i>Source mode</i>.  When stepping through code on the target, the size of a single step will be a line of source code.

</td>
</tr>
<tr>
<td>
DEBUG_LEVEL_ASSEMBLY

</td>
<td>
<i>Assembly mode</i>.  When stepping through code on the target, the size of a single step will be a single processor instruction.

</td>
</tr>
</table>

## -returns

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information about the code level, see <a href="/windows-hardware/drivers/debugger/using-source-files">Using Source Files</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setcodelevel">SetCodeLevel</a>

