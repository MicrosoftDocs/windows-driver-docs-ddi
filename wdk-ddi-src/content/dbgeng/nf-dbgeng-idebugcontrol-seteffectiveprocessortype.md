---
UID: NF:dbgeng.IDebugControl.SetEffectiveProcessorType
title: IDebugControl::SetEffectiveProcessorType (dbgeng.h)
description: The SetEffectiveProcessorType method sets the effective processor type of the processor of the computer that is running the target.
old-location: debugger\seteffectiveprocessortype.htm
tech.root: debugger
ms.assetid: 7c524181-c438-47ae-9180-1b0c623f24dc
ms.date: 05/03/2018
keywords: ["IDebugControl::SetEffectiveProcessorType"]
ms.keywords: IDebugControl interface [Windows Debugging],SetEffectiveProcessorType method, IDebugControl.SetEffectiveProcessorType, IDebugControl2 interface [Windows Debugging],SetEffectiveProcessorType method, IDebugControl2::SetEffectiveProcessorType, IDebugControl3 interface [Windows Debugging],SetEffectiveProcessorType method, IDebugControl3::SetEffectiveProcessorType, IDebugControl::SetEffectiveProcessorType, IDebugControl_284f54f4-897e-4329-b588-5eae0c638179.xml, SetEffectiveProcessorType, SetEffectiveProcessorType method [Windows Debugging], SetEffectiveProcessorType method [Windows Debugging],IDebugControl interface, SetEffectiveProcessorType method [Windows Debugging],IDebugControl2 interface, SetEffectiveProcessorType method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetEffectiveProcessorType, dbgeng/IDebugControl3::SetEffectiveProcessorType, dbgeng/IDebugControl::SetEffectiveProcessorType, debugger.seteffectiveprocessortype
f1_keywords:
 - "dbgeng/IDebugControl.SetEffectiveProcessorType"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl.SetEffectiveProcessorType
- IDebugControl2.SetEffectiveProcessorType
- IDebugControl3.SetEffectiveProcessorType
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::SetEffectiveProcessorType


## -description


The <b>SetEffectiveProcessorType</b> method sets the effective processor type of the processor of the computer that is running the target.


## -parameters




### -param Type [in]

Specifies the type of the processor.  For possible values, see the <i>Type</i> parameter in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getactualprocessortype">GetActualProcessorType</a>.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/target-information">Target Information</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-geteffectiveprocessortype">GetEffectiveProcessorType</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
 

 

