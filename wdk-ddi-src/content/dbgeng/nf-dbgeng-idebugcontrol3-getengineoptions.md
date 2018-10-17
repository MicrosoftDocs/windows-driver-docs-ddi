---
UID: NF:dbgeng.IDebugControl3.GetEngineOptions
title: IDebugControl3::GetEngineOptions
author: windows-driver-content
description: The GetEngineOptions method returns the engine's options.
old-location: debugger\getengineoptions.htm
tech.root: debugger
ms.assetid: a64645da-e11a-4568-9865-64eb7463892c
ms.date: 5/3/2018
ms.keywords: GetEngineOptions, GetEngineOptions method [Windows Debugging], GetEngineOptions method [Windows Debugging],IDebugControl interface, GetEngineOptions method [Windows Debugging],IDebugControl2 interface, GetEngineOptions method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetEngineOptions method, IDebugControl2 interface [Windows Debugging],GetEngineOptions method, IDebugControl2::GetEngineOptions, IDebugControl3 interface [Windows Debugging],GetEngineOptions method, IDebugControl3.GetEngineOptions, IDebugControl3::GetEngineOptions, IDebugControl::GetEngineOptions, IDebugControl_75edd4f2-c81d-408d-a61a-3c2fcf5932e6.xml, dbgeng/IDebugControl2::GetEngineOptions, dbgeng/IDebugControl3::GetEngineOptions, dbgeng/IDebugControl::GetEngineOptions, debugger.getengineoptions
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
-	IDebugControl.GetEngineOptions
-	IDebugControl2.GetEngineOptions
-	IDebugControl3.GetEngineOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetEngineOptions


## -description


The <b>GetEngineOptions</b> method returns the engine's options.


## -parameters




### -param Options [out]

Receives a bit-set that contains the engine's options. For a description of the engine options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541475">DEBUG_ENGOPT_XXX</a>.


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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537884">AddEngineOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554491">RemoveEngineOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556670">SetEngineOptions</a>
 

 

