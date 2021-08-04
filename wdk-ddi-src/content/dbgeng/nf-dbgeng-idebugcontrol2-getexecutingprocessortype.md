---
UID: NF:dbgeng.IDebugControl2.GetExecutingProcessorType
title: IDebugControl2::GetExecutingProcessorType (dbgeng.h)
description: The GetExecutingProcessorType method returns the executing processor type for the processor for which the last event occurred.
old-location: debugger\getexecutingprocessortype.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetExecutingProcessorType"]
ms.keywords: GetExecutingProcessorType, GetExecutingProcessorType method [Windows Debugging], GetExecutingProcessorType method [Windows Debugging],IDebugControl interface, GetExecutingProcessorType method [Windows Debugging],IDebugControl2 interface, GetExecutingProcessorType method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetExecutingProcessorType method, IDebugControl2 interface [Windows Debugging],GetExecutingProcessorType method, IDebugControl2.GetExecutingProcessorType, IDebugControl2::GetExecutingProcessorType, IDebugControl3 interface [Windows Debugging],GetExecutingProcessorType method, IDebugControl3::GetExecutingProcessorType, IDebugControl::GetExecutingProcessorType, IDebugControl_b2aad495-5a68-4888-bedb-da76edbfbe7a.xml, dbgeng/IDebugControl2::GetExecutingProcessorType, dbgeng/IDebugControl3::GetExecutingProcessorType, dbgeng/IDebugControl::GetExecutingProcessorType, debugger.getexecutingprocessortype
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
 - IDebugControl2::GetExecutingProcessorType
 - dbgeng/IDebugControl2::GetExecutingProcessorType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl2::GetExecutingProcessorType
---

# IDebugControl2::GetExecutingProcessorType


## -description

The <b>GetExecutingProcessorType</b> method returns the executing processor type for the processor for which the last event occurred.

## -parameters

### -param Type 

[out]
Receives the processor type.  See <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getactualprocessortype">GetActualProcessorType</a> for a list of possible values this parameter can receive.

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



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>

