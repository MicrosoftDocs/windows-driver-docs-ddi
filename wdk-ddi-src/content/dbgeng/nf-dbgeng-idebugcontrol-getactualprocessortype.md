---
UID: NF:dbgeng.IDebugControl.GetActualProcessorType
title: IDebugControl::GetActualProcessorType (dbgeng.h)
description: The GetActualProcessorType method returns the processor type of the physical processor of the computer that is running the target.
old-location: debugger\getactualprocessortype.htm
tech.root: debugger
ms.assetid: c02be0a4-f82a-4895-bbae-21f6ffdc5466
ms.date: 05/03/2018
keywords: ["IDebugControl::GetActualProcessorType"]
ms.keywords: GetActualProcessorType, GetActualProcessorType method [Windows Debugging], GetActualProcessorType method [Windows Debugging],IDebugControl interface, GetActualProcessorType method [Windows Debugging],IDebugControl2 interface, GetActualProcessorType method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetActualProcessorType method, IDebugControl.GetActualProcessorType, IDebugControl2 interface [Windows Debugging],GetActualProcessorType method, IDebugControl2::GetActualProcessorType, IDebugControl3 interface [Windows Debugging],GetActualProcessorType method, IDebugControl3::GetActualProcessorType, IDebugControl::GetActualProcessorType, IDebugControl_5511971f-2155-4ba3-b0f3-9bcd91b29555.xml, dbgeng/IDebugControl2::GetActualProcessorType, dbgeng/IDebugControl3::GetActualProcessorType, dbgeng/IDebugControl::GetActualProcessorType, debugger.getactualprocessortype
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
 - IDebugControl::GetActualProcessorType
 - dbgeng/IDebugControl::GetActualProcessorType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetActualProcessorType
 - IDebugControl2.GetActualProcessorType
 - IDebugControl3.GetActualProcessorType
---

# IDebugControl::GetActualProcessorType


## -description

The <b>GetActualProcessorType</b> method returns the processor type of the physical processor of the computer that is running the target.

## -parameters

### -param Type 

[out]
Receives the type of the processor.  The processor types are listed in the following table.     

<table>
<tr>
<th>Value</th>
<th>Processor</th>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_I386

</td>
<td>
x86 architecture

</td>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_ARM

</td>
<td>
ARM architecture

</td>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_IA64

</td>
<td>
Intel Itanium architecture

</td>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_AMD64

</td>
<td>
x64 architecture

</td>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_EBC

</td>
<td>
EFI byte code architecture

</td>
</tr>
</table>

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

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-geteffectiveprocessortype">GetEffectiveProcessorType</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexecutingprocessortype">GetExecutingProcessorType</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>