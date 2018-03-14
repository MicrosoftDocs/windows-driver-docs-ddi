---
UID: NF:dbgeng.IDebugControl2.AddEngineOptions
title: IDebugControl2::AddEngineOptions method
author: windows-driver-content
description: The AddEngineOptions method turns on some of the debugger engine's options.
old-location: debugger\addengineoptions.htm
old-project: debugger
ms.assetid: 088036f5-13cb-47ba-953c-a71c923f028e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: AddEngineOptions method [Windows Debugging], AddEngineOptions method [Windows Debugging], IDebugControl interface, AddEngineOptions method [Windows Debugging], IDebugControl2 interface, AddEngineOptions method [Windows Debugging], IDebugControl3 interface, AddEngineOptions,IDebugControl2.AddEngineOptions, IDebugControl interface [Windows Debugging], AddEngineOptions method, IDebugControl2, IDebugControl2 interface [Windows Debugging], AddEngineOptions method, IDebugControl2::AddEngineOptions, IDebugControl3 interface [Windows Debugging], AddEngineOptions method, IDebugControl3::AddEngineOptions, IDebugControl::AddEngineOptions, IDebugControl_6042b0b9-8175-4790-be19-43f8659716dc.xml, dbgeng/IDebugControl2::AddEngineOptions, dbgeng/IDebugControl3::AddEngineOptions, dbgeng/IDebugControl::AddEngineOptions, debugger.addengineoptions
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
-	Dbgeng.h
api_name:
-	IDebugControl.AddEngineOptions
-	IDebugControl2.AddEngineOptions
-	IDebugControl3.AddEngineOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::AddEngineOptions method


## -description


The <b>AddEngineOptions</b> method turns on some of the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>'s options.


## -syntax


````
HRESULT AddEngineOptions(
  [in] ULONG Options
);
````


## -parameters




### -param Options [in]

Specifies engine options to turn on.  <i>Options</i> is a bit-set that will be combined with the existing engine options using the bitwise-OR operator.  For a description of the engine options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541475">DEBUG_ENGOPT_XXX</a>.


## -returns



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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



After the engine options have been changed, the engine sends out notification to each client's <a href="https://msdn.microsoft.com/1e32bd40-8c77-4c6b-913c-6ec26707ed36">event callback object</a> by passing the DEBUG_CES_ENGINE_OPTIONS flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546598">GetEngineOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554491">RemoveEngineOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556670">SetEngineOptions</a>



 

 


