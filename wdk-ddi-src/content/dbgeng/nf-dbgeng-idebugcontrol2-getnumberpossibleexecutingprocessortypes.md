---
UID: NF:dbgeng.IDebugControl2.GetNumberPossibleExecutingProcessorTypes
title: IDebugControl2::GetNumberPossibleExecutingProcessorTypes (dbgeng.h)
description: The GetNumberPossibleExecutingProcessorTypes method returns the number of processor types that are supported by the computer running the current target.
old-location: debugger\getnumberpossibleexecutingprocessortypes.htm
tech.root: debugger
ms.assetid: 9e4ca8a6-f33f-4403-a52f-f242ce40aac8
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetNumberPossibleExecutingProcessorTypes"]
ms.keywords: GetNumberPossibleExecutingProcessorTypes, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging], GetNumberPossibleExecutingProcessorTypes method [Windows Debugging],IDebugControl interface, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging],IDebugControl2 interface, GetNumberPossibleExecutingProcessorTypes method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetNumberPossibleExecutingProcessorTypes method, IDebugControl2 interface [Windows Debugging],GetNumberPossibleExecutingProcessorTypes method, IDebugControl2.GetNumberPossibleExecutingProcessorTypes, IDebugControl2::GetNumberPossibleExecutingProcessorTypes, IDebugControl3 interface [Windows Debugging],GetNumberPossibleExecutingProcessorTypes method, IDebugControl3::GetNumberPossibleExecutingProcessorTypes, IDebugControl::GetNumberPossibleExecutingProcessorTypes, IDebugControl_62f066c6-6ffb-4323-ad82-786a8a763783.xml, dbgeng/IDebugControl2::GetNumberPossibleExecutingProcessorTypes, dbgeng/IDebugControl3::GetNumberPossibleExecutingProcessorTypes, dbgeng/IDebugControl::GetNumberPossibleExecutingProcessorTypes, debugger.getnumberpossibleexecutingprocessortypes
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
 - IDebugControl2::GetNumberPossibleExecutingProcessorTypes
 - dbgeng/IDebugControl2::GetNumberPossibleExecutingProcessorTypes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetNumberPossibleExecutingProcessorTypes
 - IDebugControl2.GetNumberPossibleExecutingProcessorTypes
 - IDebugControl3.GetNumberPossibleExecutingProcessorTypes
---

# IDebugControl2::GetNumberPossibleExecutingProcessorTypes


## -description

The <b>GetNumberPossibleExecutingProcessorTypes</b> method returns the number of processor types that are supported by the computer running the current target.

## -parameters

### -param Number 

[out]
Receives the number of processor types.

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

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getpossibleexecutingprocessortypes">GetPossibleExecutingProcessorTypes</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>