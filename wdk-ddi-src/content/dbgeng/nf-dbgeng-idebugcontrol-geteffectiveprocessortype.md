---
UID: NF:dbgeng.IDebugControl.GetEffectiveProcessorType
title: IDebugControl::GetEffectiveProcessorType (dbgeng.h)
description: The GetEffectiveProcessorType method returns the effective processor type of the processor of the computer that is running the target.
old-location: debugger\geteffectiveprocessortype.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl::GetEffectiveProcessorType"]
ms.keywords: GetEffectiveProcessorType, GetEffectiveProcessorType method [Windows Debugging], GetEffectiveProcessorType method [Windows Debugging],IDebugControl interface, GetEffectiveProcessorType method [Windows Debugging],IDebugControl2 interface, GetEffectiveProcessorType method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetEffectiveProcessorType method, IDebugControl.GetEffectiveProcessorType, IDebugControl2 interface [Windows Debugging],GetEffectiveProcessorType method, IDebugControl2::GetEffectiveProcessorType, IDebugControl3 interface [Windows Debugging],GetEffectiveProcessorType method, IDebugControl3::GetEffectiveProcessorType, IDebugControl::GetEffectiveProcessorType, IDebugControl_9e0db836-17eb-4df1-a298-f8d54282d188.xml, dbgeng/IDebugControl2::GetEffectiveProcessorType, dbgeng/IDebugControl3::GetEffectiveProcessorType, dbgeng/IDebugControl::GetEffectiveProcessorType, debugger.geteffectiveprocessortype
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
 - IDebugControl::GetEffectiveProcessorType
 - dbgeng/IDebugControl::GetEffectiveProcessorType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetEffectiveProcessorType
 - IDebugControl2.GetEffectiveProcessorType
 - IDebugControl3.GetEffectiveProcessorType
---

# IDebugControl::GetEffectiveProcessorType


## -description

The <b>GetEffectiveProcessorType</b> method returns the effective processor type of the processor of the computer that is running the target.

## -parameters

### -param Type 

[out]
Receives the type of the processor.  For possible values, see the <i>Type</i> parameter in <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getactualprocessortype">GetActualProcessorType</a>.

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

## -remarks

For more information, see <a href="/windows-hardware/drivers/debugger/target-information">Target Information</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getactualprocessortype">GetActualProcessorType</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexecutingprocessortype">GetExecutingProcessorType</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-seteffectiveprocessortype">SetEffectiveProcessorType</a>
