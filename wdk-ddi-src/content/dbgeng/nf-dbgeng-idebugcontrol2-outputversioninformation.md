---
UID: NF:dbgeng.IDebugControl2.OutputVersionInformation
title: IDebugControl2::OutputVersionInformation method
author: windows-driver-content
description: The OutputVersionInformation method prints version information about the debugger engine to the debugger console.
old-location: debugger\outputversioninformation.htm
old-project: debugger
ms.assetid: cbf688b4-a174-4ab0-af98-2c0db1b2ab3a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugControl interface [Windows Debugging], OutputVersionInformation method, IDebugControl2, IDebugControl2 interface [Windows Debugging], OutputVersionInformation method, IDebugControl2::OutputVersionInformation, IDebugControl3 interface [Windows Debugging], OutputVersionInformation method, IDebugControl3::OutputVersionInformation, IDebugControl::OutputVersionInformation, IDebugControl_ea568b24-944d-4ed8-abd6-24b7c7771a1e.xml, OutputVersionInformation method [Windows Debugging], OutputVersionInformation method [Windows Debugging], IDebugControl interface, OutputVersionInformation method [Windows Debugging], IDebugControl2 interface, OutputVersionInformation method [Windows Debugging], IDebugControl3 interface, OutputVersionInformation,IDebugControl2.OutputVersionInformation, dbgeng/IDebugControl2::OutputVersionInformation, dbgeng/IDebugControl3::OutputVersionInformation, dbgeng/IDebugControl::OutputVersionInformation, debugger.outputversioninformation
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
-	IDebugControl.OutputVersionInformation
-	IDebugControl2.OutputVersionInformation
-	IDebugControl3.OutputVersionInformation
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::OutputVersionInformation method


## -description


The <b>OutputVersionInformation</b> method prints version information about the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> to the debugger console.


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



The information that is sent to the output can include the mode of the debugger, the path and version of the debugger DLLs, the extension DLL search path, the extension DLL chain, and the version of the operating system that is running on the host computer.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.



