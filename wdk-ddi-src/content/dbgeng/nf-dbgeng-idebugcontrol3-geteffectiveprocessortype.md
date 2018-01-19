---
UID: NF:dbgeng.IDebugControl3.GetEffectiveProcessorType
title: IDebugControl3::GetEffectiveProcessorType method
author: windows-driver-content
description: The GetEffectiveProcessorType method returns the effective processor type of the processor of the computer that is running the target.
old-location: debugger\geteffectiveprocessortype.htm
old-project: debugger
ms.assetid: 66a5aa3d-fe35-4c30-951f-f25de75dacb0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetEffectiveProcessorType, GetEffectiveProcessorType
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
req.alt-api: IDebugControl.GetEffectiveProcessorType,IDebugControl2.GetEffectiveProcessorType,IDebugControl3.GetEffectiveProcessorType
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556657">SetEffectiveProcessorType</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546670">GetExecutingProcessorType</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetEffectiveProcessorType method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

