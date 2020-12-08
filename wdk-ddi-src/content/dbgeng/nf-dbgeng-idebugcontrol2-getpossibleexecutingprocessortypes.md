---
UID: NF:dbgeng.IDebugControl2.GetPossibleExecutingProcessorTypes
title: IDebugControl2::GetPossibleExecutingProcessorTypes (dbgeng.h)
description: The GetPossibleExecutingProcessorTypes method returns the processor types that are supported by the computer running the current target.
old-location: debugger\getpossibleexecutingprocessortypes.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetPossibleExecutingProcessorTypes"]
ms.keywords: GetPossibleExecutingProcessorTypes, GetPossibleExecutingProcessorTypes method [Windows Debugging], GetPossibleExecutingProcessorTypes method [Windows Debugging],IDebugControl interface, GetPossibleExecutingProcessorTypes method [Windows Debugging],IDebugControl2 interface, GetPossibleExecutingProcessorTypes method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetPossibleExecutingProcessorTypes method, IDebugControl2 interface [Windows Debugging],GetPossibleExecutingProcessorTypes method, IDebugControl2.GetPossibleExecutingProcessorTypes, IDebugControl2::GetPossibleExecutingProcessorTypes, IDebugControl3 interface [Windows Debugging],GetPossibleExecutingProcessorTypes method, IDebugControl3::GetPossibleExecutingProcessorTypes, IDebugControl::GetPossibleExecutingProcessorTypes, IDebugControl_582811e7-4eb0-4b94-a5d0-8c903ea8c2fe.xml, dbgeng/IDebugControl2::GetPossibleExecutingProcessorTypes, dbgeng/IDebugControl3::GetPossibleExecutingProcessorTypes, dbgeng/IDebugControl::GetPossibleExecutingProcessorTypes, debugger.getpossibleexecutingprocessortypes
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
 - IDebugControl2::GetPossibleExecutingProcessorTypes
 - dbgeng/IDebugControl2::GetPossibleExecutingProcessorTypes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetPossibleExecutingProcessorTypes
 - IDebugControl2.GetPossibleExecutingProcessorTypes
 - IDebugControl3.GetPossibleExecutingProcessorTypes
---

# IDebugControl2::GetPossibleExecutingProcessorTypes


## -description

The <b>GetPossibleExecutingProcessorTypes</b> method returns the processor types that are supported by the computer running the current target.

## -parameters

### -param Start 

[in]
Specifies the index of the first processor type to return.  The processor types are indexed by numbers zero through to the number of processor types supported by the current target minus one.  The number of processor types supported by the current target can be found using <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumberpossibleexecutingprocessortypes">GetNumberPossibleExecutingProcessorTypes</a>.

### -param Count 

[in]
Specifies how many processor types to return.

### -param Types 

[out]
Receives the list of processor types.  The number of elements this array holds is <i>Count</i>.  For a description of the processor types see <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getactualprocessortype">GetActualProcessorType</a>.

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



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumberpossibleexecutingprocessortypes">GetNumberPossibleExecutingProcessorTypes</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
