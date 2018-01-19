---
UID: NF:dbgeng.IDebugControl3.OutputVersionInformation
title: IDebugControl3::OutputVersionInformation method
author: windows-driver-content
description: The OutputVersionInformation method prints version information about the debugger engine to the debugger console.
old-location: debugger\outputversioninformation.htm
old-project: debugger
ms.assetid: cbf688b4-a174-4ab0-af98-2c0db1b2ab3a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::OutputVersionInformation, OutputVersionInformation
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
req.alt-api: IDebugControl.OutputVersionInformation,IDebugControl2.OutputVersionInformation,IDebugControl3.OutputVersionInformation
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

# IDebugControl3::OutputVersionInformation method



## -description
The <b>OutputVersionInformation</b> method prints version information about the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a> to the debugger console.



## -syntax

````
HRESULT OutputVersionInformation(
  [in] ULONG OutputControl
);
````


## -parameters

### -param OutputControl [in]

Specifies where to send the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


## -returns
This method may also return other error values, including error values caused by the engine being busy.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
The information that is sent to the output can include the mode of the debugger, the path and version of the debugger DLLs, the extension DLL search path, the extension DLL chain, and the version of the operating system that is running on the host computer.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.</p>