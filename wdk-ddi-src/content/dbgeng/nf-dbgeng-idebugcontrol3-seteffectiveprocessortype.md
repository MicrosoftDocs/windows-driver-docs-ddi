---
UID: NF:dbgeng.IDebugControl3.SetEffectiveProcessorType
title: IDebugControl3::SetEffectiveProcessorType method
author: windows-driver-content
description: The SetEffectiveProcessorType method sets the effective processor type of the processor of the computer that is running the target.
old-location: debugger\seteffectiveprocessortype.htm
old-project: debugger
ms.assetid: 7c524181-c438-47ae-9180-1b0c623f24dc
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl2, IDebugControl2 interface [Windows Debugging], SetEffectiveProcessorType method, dbgeng/IDebugControl2::SetEffectiveProcessorType, dbgeng/IDebugControl::SetEffectiveProcessorType, IDebugControl interface [Windows Debugging], SetEffectiveProcessorType method, SetEffectiveProcessorType method [Windows Debugging], SetEffectiveProcessorType, SetEffectiveProcessorType method [Windows Debugging], IDebugControl interface, IDebugControl3::SetEffectiveProcessorType, IDebugControl3, IDebugControl2::SetEffectiveProcessorType, IDebugControl, IDebugControl::SetEffectiveProcessorType, dbgeng/IDebugControl3::SetEffectiveProcessorType, IDebugControl_284f54f4-897e-4329-b588-5eae0c638179.xml, SetEffectiveProcessorType method [Windows Debugging], IDebugControl2 interface, SetEffectiveProcessorType method [Windows Debugging], IDebugControl3 interface, IDebugControl3 interface [Windows Debugging], SetEffectiveProcessorType method, debugger.seteffectiveprocessortype
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
-	IDebugControl.SetEffectiveProcessorType
-	IDebugControl2.SetEffectiveProcessorType
-	IDebugControl3.SetEffectiveProcessorType
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl3::SetEffectiveProcessorType method


## -description


The <b>SetEffectiveProcessorType</b> method sets the effective processor type of the processor of the computer that is running the target.


## -syntax


````
HRESULT SetEffectiveProcessorType(
  [in] ULONG Type
);
````


## -parameters




### -param Type [in]

Specifies the type of the processor.  For possible values, see the <i>Type</i> parameter in <a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>.


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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546595">GetEffectiveProcessorType</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetEffectiveProcessorType method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

