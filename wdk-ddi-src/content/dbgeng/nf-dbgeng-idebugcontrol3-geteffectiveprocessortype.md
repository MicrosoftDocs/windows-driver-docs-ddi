---
UID: NF:dbgeng.IDebugControl3.GetEffectiveProcessorType
title: IDebugControl3::GetEffectiveProcessorType method
author: windows-driver-content
description: The GetEffectiveProcessorType method returns the effective processor type of the processor of the computer that is running the target.
old-location: debugger\geteffectiveprocessortype.htm
old-project: debugger
ms.assetid: 66a5aa3d-fe35-4c30-951f-f25de75dacb0
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugControl3::GetEffectiveProcessorType, IDebugControl_9e0db836-17eb-4df1-a298-f8d54282d188.xml, IDebugControl3, GetEffectiveProcessorType, GetEffectiveProcessorType method [Windows Debugging], GetEffectiveProcessorType method [Windows Debugging], IDebugControl interface, IDebugControl::GetEffectiveProcessorType, GetEffectiveProcessorType method [Windows Debugging], IDebugControl2 interface, dbgeng/IDebugControl::GetEffectiveProcessorType, IDebugControl3::GetEffectiveProcessorType, IDebugControl2::GetEffectiveProcessorType, dbgeng/IDebugControl2::GetEffectiveProcessorType, IDebugControl interface [Windows Debugging], GetEffectiveProcessorType method, debugger.geteffectiveprocessortype, IDebugControl2 interface [Windows Debugging], GetEffectiveProcessorType method, GetEffectiveProcessorType method [Windows Debugging], IDebugControl3 interface, IDebugControl3 interface [Windows Debugging], GetEffectiveProcessorType method
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.GetEffectiveProcessorType
-	IDebugControl2.GetEffectiveProcessorType
-	IDebugControl3.GetEffectiveProcessorType
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetEffectiveProcessorType method


## -description


The <b>GetEffectiveProcessorType</b> method returns the effective processor type of the processor of the computer that is running the target.


## -syntax


````
HRESULT GetEffectiveProcessorType(
  [out] PULONG Type
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546670">GetExecutingProcessorType</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556657">SetEffectiveProcessorType</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetEffectiveProcessorType method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

