---
UID: NF:dbgeng.IDebugControl2.GetEffectiveProcessorType
title: IDebugControl2::GetEffectiveProcessorType method
author: windows-driver-content
description: The GetEffectiveProcessorType method returns the effective processor type of the processor of the computer that is running the target.
old-location: debugger\geteffectiveprocessortype.htm
old-project: debugger
ms.assetid: 66a5aa3d-fe35-4c30-951f-f25de75dacb0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetEffectiveProcessorType method [Windows Debugging], GetEffectiveProcessorType method [Windows Debugging], IDebugControl interface, GetEffectiveProcessorType method [Windows Debugging], IDebugControl2 interface, GetEffectiveProcessorType method [Windows Debugging], IDebugControl3 interface, GetEffectiveProcessorType,IDebugControl2.GetEffectiveProcessorType, IDebugControl interface [Windows Debugging], GetEffectiveProcessorType method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetEffectiveProcessorType method, IDebugControl2::GetEffectiveProcessorType, IDebugControl3 interface [Windows Debugging], GetEffectiveProcessorType method, IDebugControl3::GetEffectiveProcessorType, IDebugControl::GetEffectiveProcessorType, IDebugControl_9e0db836-17eb-4df1-a298-f8d54282d188.xml, dbgeng/IDebugControl2::GetEffectiveProcessorType, dbgeng/IDebugControl3::GetEffectiveProcessorType, dbgeng/IDebugControl::GetEffectiveProcessorType, debugger.geteffectiveprocessortype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.GetEffectiveProcessorType
-	IDebugControl2.GetEffectiveProcessorType
-	IDebugControl3.GetEffectiveProcessorType
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetEffectiveProcessorType method


## -description


The <b>GetEffectiveProcessorType</b> method returns the effective processor type of the processor of the computer that is running the target.


## -parameters




### -param Type [out]

Receives the type of the processor.  For possible values, see the <i>Type</i> parameter in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546670">GetExecutingProcessorType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556657">SetEffectiveProcessorType</a>
 

 

