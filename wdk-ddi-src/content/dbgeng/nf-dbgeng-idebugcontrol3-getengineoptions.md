---
UID: NF:dbgeng.IDebugControl3.GetEngineOptions
title: IDebugControl3::GetEngineOptions (dbgeng.h)
description: The GetEngineOptions method returns the engine's options.
old-location: debugger\getengineoptions.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetEngineOptions"]
ms.keywords: GetEngineOptions, GetEngineOptions method [Windows Debugging], GetEngineOptions method [Windows Debugging],IDebugControl interface, GetEngineOptions method [Windows Debugging],IDebugControl2 interface, GetEngineOptions method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetEngineOptions method, IDebugControl2 interface [Windows Debugging],GetEngineOptions method, IDebugControl2::GetEngineOptions, IDebugControl3 interface [Windows Debugging],GetEngineOptions method, IDebugControl3.GetEngineOptions, IDebugControl3::GetEngineOptions, IDebugControl::GetEngineOptions, IDebugControl_75edd4f2-c81d-408d-a61a-3c2fcf5932e6.xml, dbgeng/IDebugControl2::GetEngineOptions, dbgeng/IDebugControl3::GetEngineOptions, dbgeng/IDebugControl::GetEngineOptions, debugger.getengineoptions
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
 - IDebugControl3::GetEngineOptions
 - dbgeng/IDebugControl3::GetEngineOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl3::GetEngineOptions
---

# IDebugControl3::GetEngineOptions


## -description

The <b>GetEngineOptions</b> method returns the engine's options.

## -parameters

### -param Options 

[out]
Receives a bit-set that contains the engine's options. For a description of the engine options, see <a href="/previous-versions/ff541475(v=vs.85)">DEBUG_ENGOPT_XXX</a>.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addengineoptions">AddEngineOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removeengineoptions">RemoveEngineOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setengineoptions">SetEngineOptions</a>

