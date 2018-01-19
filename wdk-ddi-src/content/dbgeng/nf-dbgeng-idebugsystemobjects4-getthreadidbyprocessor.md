---
UID: NF:dbgeng.IDebugSystemObjects4.GetThreadIdByProcessor
title: IDebugSystemObjects4::GetThreadIdByProcessor method
author: windows-driver-content
description: The GetThreadIdByProcessor method returns the engine thread ID for the kernel-modevirtual thread corresponding to the specified processor.
old-location: debugger\getthreadidbyprocessor.htm
old-project: debugger
ms.assetid: c771a581-53ac-44a7-b307-b8a22ac97496
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::GetThreadIdByProcessor, GetThreadIdByProcessor
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
req.alt-api: IDebugSystemObjects.GetThreadIdByProcessor,IDebugSystemObjects2.GetThreadIdByProcessor,IDebugSystemObjects3.GetThreadIdByProcessor,IDebugSystemObjects4.GetThreadIdByProcessor
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

# IDebugSystemObjects4::GetThreadIdByProcessor method



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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
This method is only available in kernel-mode debugging.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>