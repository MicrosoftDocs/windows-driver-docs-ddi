---
UID: NF:dbgeng.IDebugClient5.SetProcessOptions
title: IDebugClient5::SetProcessOptions
author: windows-driver-content
description: The SetProcessOptions method sets the process options affecting the current process.
old-location: debugger\setprocessoptions.htm
old-project: debugger
ms.assetid: c077e2cc-b234-4393-ab8c-d0b8199515e3
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugClient interface [Windows Debugging],SetProcessOptions method, IDebugClient2 interface [Windows Debugging],SetProcessOptions method, IDebugClient2::SetProcessOptions, IDebugClient3 interface [Windows Debugging],SetProcessOptions method, IDebugClient3::SetProcessOptions, IDebugClient4 interface [Windows Debugging],SetProcessOptions method, IDebugClient4::SetProcessOptions, IDebugClient5 interface [Windows Debugging],SetProcessOptions method, IDebugClient5.SetProcessOptions, IDebugClient5::SetProcessOptions, IDebugClient::SetProcessOptions, IDebugClient_d9936a28-08c3-4c4c-ba2b-accc9443b825.xml, SetProcessOptions, SetProcessOptions method [Windows Debugging], SetProcessOptions method [Windows Debugging],IDebugClient interface, SetProcessOptions method [Windows Debugging],IDebugClient2 interface, SetProcessOptions method [Windows Debugging],IDebugClient3 interface, SetProcessOptions method [Windows Debugging],IDebugClient4 interface, SetProcessOptions method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::SetProcessOptions, dbgeng/IDebugClient3::SetProcessOptions, dbgeng/IDebugClient4::SetProcessOptions, dbgeng/IDebugClient5::SetProcessOptions, dbgeng/IDebugClient::SetProcessOptions, debugger.setprocessoptions
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
-	IDebugClient.SetProcessOptions
-	IDebugClient2.SetProcessOptions
-	IDebugClient3.SetProcessOptions
-	IDebugClient4.SetProcessOptions
-	IDebugClient5.SetProcessOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::SetProcessOptions


## -description


The <b>SetProcessOptions</b> method sets the process options affecting the current process.


## -parameters




### -param Options [in]

Specifies a set of flags that will become the new process options for the current process.  For details on these options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>.


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



This method is available only in live user-mode debugging.

Some of the process options are global options, others are specific to the current process.

If any process options are modified, the engine will notify the event callbacks by calling their <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> method with the DEBUG_CES_PROCESS_OPTIONS flag set.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537917">AddProcessOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548163">GetProcessOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554505">RemoveProcessOptions</a>
 

 

