---
UID: NF:dbgeng.IDebugControl2.SetCodeLevel
title: IDebugControl2::SetCodeLevel (dbgeng.h)
description: The SetCodeLevel method sets the current code level and is mainly used when stepping through code.
old-location: debugger\setcodelevel.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::SetCodeLevel"]
ms.keywords: IDebugControl interface [Windows Debugging],SetCodeLevel method, IDebugControl2 interface [Windows Debugging],SetCodeLevel method, IDebugControl2.SetCodeLevel, IDebugControl2::SetCodeLevel, IDebugControl3 interface [Windows Debugging],SetCodeLevel method, IDebugControl3::SetCodeLevel, IDebugControl::SetCodeLevel, IDebugControl_40aa5eed-ef3f-4ec4-84eb-0cfec638bc4a.xml, SetCodeLevel, SetCodeLevel method [Windows Debugging], SetCodeLevel method [Windows Debugging],IDebugControl interface, SetCodeLevel method [Windows Debugging],IDebugControl2 interface, SetCodeLevel method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetCodeLevel, dbgeng/IDebugControl3::SetCodeLevel, dbgeng/IDebugControl::SetCodeLevel, debugger.setcodelevel
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
 - IDebugControl2::SetCodeLevel
 - dbgeng/IDebugControl2::SetCodeLevel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.SetCodeLevel
 - IDebugControl2.SetCodeLevel
 - IDebugControl3.SetCodeLevel
---

# IDebugControl2::SetCodeLevel


## -description

The <b>SetCodeLevel</b> method sets the current code level and is mainly used when stepping through code.

## -parameters

### -param Level 

[in]
Specifies the current code level.  <i>Level</i> can take one of the values in the following table.

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

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getcodelevel">GetCodeLevel</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
