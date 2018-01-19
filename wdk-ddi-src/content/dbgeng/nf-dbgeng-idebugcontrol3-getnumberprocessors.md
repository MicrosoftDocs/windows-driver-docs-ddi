---
UID: NF:dbgeng.IDebugControl3.GetNumberProcessors
title: IDebugControl3::GetNumberProcessors method
author: windows-driver-content
description: The GetNumberProcessors method returns the number of processors on the computer running the current target.
old-location: debugger\getnumberprocessors.htm
old-project: debugger
ms.assetid: b3f4af4e-dbba-4f14-8935-f894865cbe7d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetNumberProcessors, GetNumberProcessors
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
req.alt-api: IDebugControl.GetNumberProcessors,IDebugControl2.GetNumberProcessors,IDebugControl3.GetNumberProcessors
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

# IDebugControl3::GetNumberProcessors method



## -description
The <b>GetNumberProcessors</b> method returns the number of processors on the computer running the current target.



## -syntax

````
HRESULT GetNumberProcessors(
  [out] PULONG Number
);
````


## -parameters

### -param Number [out]

Receives the number of processors.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.</p>