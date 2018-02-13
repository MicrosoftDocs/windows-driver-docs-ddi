---
UID: NF:dbgeng.IDebugSystemObjects.GetThreadIdByProcessor
title: IDebugSystemObjects::GetThreadIdByProcessor method
author: windows-driver-content
description: The GetThreadIdByProcessor method returns the engine thread ID for the kernel-modevirtual thread corresponding to the specified processor.
old-location: debugger\getthreadidbyprocessor.htm
old-project: debugger
ms.assetid: c771a581-53ac-44a7-b307-b8a22ac97496
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects3 interface [Windows Debugging], GetThreadIdByProcessor method, IDebugSystemObjects2::GetThreadIdByProcessor, dbgeng/IDebugSystemObjects3::GetThreadIdByProcessor, dbgeng/IDebugSystemObjects::GetThreadIdByProcessor, GetThreadIdByProcessor method [Windows Debugging], IDebugSystemObjects4 interface, GetThreadIdByProcessor method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects interface [Windows Debugging], GetThreadIdByProcessor method, IDebugSystemObjects4::GetThreadIdByProcessor, IDebugSystemObjects_59fff866-93b2-48fb-8f49-bf778e2f0f7f.xml, GetThreadIdByProcessor method [Windows Debugging], IDebugSystemObjects2 interface [Windows Debugging], GetThreadIdByProcessor method, IDebugSystemObjects::GetThreadIdByProcessor, IDebugSystemObjects4 interface [Windows Debugging], GetThreadIdByProcessor method, GetThreadIdByProcessor, debugger.getthreadidbyprocessor, GetThreadIdByProcessor method [Windows Debugging], IDebugSystemObjects interface, dbgeng/IDebugSystemObjects4::GetThreadIdByProcessor, IDebugSystemObjects3::GetThreadIdByProcessor, GetThreadIdByProcessor method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects, dbgeng/IDebugSystemObjects2::GetThreadIdByProcessor
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
-	IDebugSystemObjects.GetThreadIdByProcessor
-	IDebugSystemObjects2.GetThreadIdByProcessor
-	IDebugSystemObjects3.GetThreadIdByProcessor
-	IDebugSystemObjects4.GetThreadIdByProcessor
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSystemObjects::GetThreadIdByProcessor method


## -description


The <b>GetThreadIdByProcessor</b> method returns the engine thread ID for the kernel-modevirtual thread corresponding to the specified processor.


## -syntax


````
HRESULT GetThreadIdByProcessor(
  [in]  ULONG  Processor,
  [out] PULONG Id
);
````


## -parameters




### -param Processor [in]

Specifies the processor corresponding to the desired thread.


### -param Id [out]

Receives the engine thread ID.


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



This method is only available in kernel-mode debugging.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



