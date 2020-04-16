---
UID: NF:dbgeng.IDebugControl.OutputVersionInformation
title: IDebugControl::OutputVersionInformation (dbgeng.h)
description: The OutputVersionInformation method prints version information about the debugger engine to the debugger console.
old-location: debugger\outputversioninformation.htm
tech.root: debugger
ms.assetid: cbf688b4-a174-4ab0-af98-2c0db1b2ab3a
ms.date: 05/03/2018
keywords: ["IDebugControl::OutputVersionInformation"]
ms.keywords: IDebugControl interface [Windows Debugging],OutputVersionInformation method, IDebugControl.OutputVersionInformation, IDebugControl2 interface [Windows Debugging],OutputVersionInformation method, IDebugControl2::OutputVersionInformation, IDebugControl3 interface [Windows Debugging],OutputVersionInformation method, IDebugControl3::OutputVersionInformation, IDebugControl::OutputVersionInformation, IDebugControl_ea568b24-944d-4ed8-abd6-24b7c7771a1e.xml, OutputVersionInformation, OutputVersionInformation method [Windows Debugging], OutputVersionInformation method [Windows Debugging],IDebugControl interface, OutputVersionInformation method [Windows Debugging],IDebugControl2 interface, OutputVersionInformation method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::OutputVersionInformation, dbgeng/IDebugControl3::OutputVersionInformation, dbgeng/IDebugControl::OutputVersionInformation, debugger.outputversioninformation
f1_keywords:
 - "dbgeng/IDebugControl.OutputVersionInformation"
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
- IDebugControl.OutputVersionInformation
- IDebugControl2.OutputVersionInformation
- IDebugControl3.OutputVersionInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::OutputVersionInformation


## -description


The <b>OutputVersionInformation</b> method prints version information about the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> to the debugger console.


## -parameters




### -param OutputControl [in]

Specifies where to send the output.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.


## -returns



This method may also return other error values, including error values caused by the engine being busy.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/target-information">Target Information</a>.



