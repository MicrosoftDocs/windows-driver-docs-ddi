---
UID: NF:dbgeng.IDebugControl.GetNumberSupportedProcessorTypes
title: IDebugControl::GetNumberSupportedProcessorTypes (dbgeng.h)
description: The GetNumberSupportedProcessorTypes method returns the number of processor types supported by the engine.
old-location: debugger\getnumbersupportedprocessortypes.htm
tech.root: debugger
ms.assetid: 6057fd27-75be-403b-a939-7865de45e031
ms.date: 05/03/2018
keywords: ["IDebugControl::GetNumberSupportedProcessorTypes"]
ms.keywords: GetNumberSupportedProcessorTypes, GetNumberSupportedProcessorTypes method [Windows Debugging], GetNumberSupportedProcessorTypes method [Windows Debugging],IDebugControl interface, GetNumberSupportedProcessorTypes method [Windows Debugging],IDebugControl2 interface, GetNumberSupportedProcessorTypes method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetNumberSupportedProcessorTypes method, IDebugControl.GetNumberSupportedProcessorTypes, IDebugControl2 interface [Windows Debugging],GetNumberSupportedProcessorTypes method, IDebugControl2::GetNumberSupportedProcessorTypes, IDebugControl3 interface [Windows Debugging],GetNumberSupportedProcessorTypes method, IDebugControl3::GetNumberSupportedProcessorTypes, IDebugControl::GetNumberSupportedProcessorTypes, IDebugControl_5b3a8335-0e6f-4f83-9549-fa53ce9eb1d5.xml, dbgeng/IDebugControl2::GetNumberSupportedProcessorTypes, dbgeng/IDebugControl3::GetNumberSupportedProcessorTypes, dbgeng/IDebugControl::GetNumberSupportedProcessorTypes, debugger.getnumbersupportedprocessortypes
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
 - IDebugControl::GetNumberSupportedProcessorTypes
 - dbgeng/IDebugControl::GetNumberSupportedProcessorTypes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetNumberSupportedProcessorTypes
 - IDebugControl2.GetNumberSupportedProcessorTypes
 - IDebugControl3.GetNumberSupportedProcessorTypes
---

# IDebugControl::GetNumberSupportedProcessorTypes


## -description

The GetNumberSupportedProcessorTypes method returns the number of processor types supported by the engine.

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

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getsupportedprocessortypes">GetSupportedProcessorTypes</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>