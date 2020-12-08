---
UID: NF:dbgeng.IDebugControl.RemoveEngineOptions
title: IDebugControl::RemoveEngineOptions (dbgeng.h)
description: The RemoveEngineOptions method turns off some of the engine's options.
old-location: debugger\removeengineoptions.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl::RemoveEngineOptions"]
ms.keywords: IDebugControl interface [Windows Debugging],RemoveEngineOptions method, IDebugControl.RemoveEngineOptions, IDebugControl2 interface [Windows Debugging],RemoveEngineOptions method, IDebugControl2::RemoveEngineOptions, IDebugControl3 interface [Windows Debugging],RemoveEngineOptions method, IDebugControl3::RemoveEngineOptions, IDebugControl::RemoveEngineOptions, IDebugControl_b1af0528-4fc2-4ea3-90e8-c7d92b0632f4.xml, RemoveEngineOptions, RemoveEngineOptions method [Windows Debugging], RemoveEngineOptions method [Windows Debugging],IDebugControl interface, RemoveEngineOptions method [Windows Debugging],IDebugControl2 interface, RemoveEngineOptions method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::RemoveEngineOptions, dbgeng/IDebugControl3::RemoveEngineOptions, dbgeng/IDebugControl::RemoveEngineOptions, debugger.removeengineoptions
req.header: dbgeng.h
req.include-header: Dbgeng.h, Dbgeng.h, Dbgeng.h
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
 - IDebugControl::RemoveEngineOptions
 - dbgeng/IDebugControl::RemoveEngineOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.RemoveEngineOptions
 - IDebugControl2.RemoveEngineOptions
 - IDebugControl3.RemoveEngineOptions
---

# IDebugControl::RemoveEngineOptions


## -description

The <b>RemoveEngineOptions</b> method turns off some of the engine's options.

## -parameters

### -param Options 

[in]
Specifies the engine options to turn off.  <i>Options</i> is a bit-set; the new value of the engine's options will equal the bitwise-NOT of <i>Options</i> combined with old value using the bitwise-AND operator (<code>new_value := old_value AND NOT Options</code>).  For a description of the engine options, see <a href="/previous-versions/ff541475(v=vs.85)">DEBUG_ENGOPT_XXX</a>.

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

After the engine options have been changed, the engine sends out notification to each client's event callback object by passing the DEBUG_CES_ENGINE_OPTIONS flag to the <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> method.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addengineoptions">AddEngineOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getengineoptions">GetEngineOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setengineoptions">SetEngineOptions</a>
