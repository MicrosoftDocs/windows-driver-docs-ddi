---
UID: NF:dbgeng.IDebugSymbols3.GetScope
title: IDebugSymbols3::GetScope method
author: windows-driver-content
description: The GetScope method returns information about the current scope.
old-location: debugger\getscope.htm
old-project: debugger
ms.assetid: 59eb490e-66d5-4108-8d00-5503fa56665d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetScope method [Windows Debugging], GetScope method [Windows Debugging], IDebugSymbols interface, GetScope method [Windows Debugging], IDebugSymbols2 interface, GetScope method [Windows Debugging], IDebugSymbols3 interface, GetScope,IDebugSymbols3.GetScope, IDebugSymbols interface [Windows Debugging], GetScope method, IDebugSymbols2 interface [Windows Debugging], GetScope method, IDebugSymbols2::GetScope, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetScope method, IDebugSymbols3::GetScope, IDebugSymbols::GetScope, IDebugSymbols_500f523a-22d9-468e-8d7c-36f49bda089c.xml, dbgeng/IDebugSymbols2::GetScope, dbgeng/IDebugSymbols3::GetScope, dbgeng/IDebugSymbols::GetScope, debugger.getscope
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Ntddk.h
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
-	IDebugSymbols.GetScope
-	IDebugSymbols2.GetScope
-	IDebugSymbols3.GetScope
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetScope method


## -description


The <b>GetScope</b> method returns information about the current scope.


## -parameters




### -param InstructionOffset [out, optional]

Receives the location in the process's virtual address space of the current scope's current instruction.


### -param ScopeFrame [out, optional]

Receives the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541643">DEBUG_STACK_FRAME</a> structure representing the current scope's stack frame.


### -param ScopeContext [out, optional]

Receives the current scope's <a href="https://msdn.microsoft.com/f14b6361-9962-4fa3-bb1a-dfde066754b9">thread context</a>.  The type of the thread context is the CONTEXT structure for the target's effective processor.  The buffer <i>ScopeContext</i> must be large enough to hold this structure.


### -param ScopeContextSize [in]

Specifies the size of the buffer <i>ScopeContext</i>.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer <i>ScopeContext</i> was not large enough to hold the scope's context.

</td>
</tr>
</table>
 




## -remarks



For more information about scopes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.




## -see-also




<a href="https://msdn.microsoft.com/66a5aa3d-fe35-4c30-951f-f25de75dacb0">IDebugControl::GetEffectiveProcessorType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554577">ResetScope</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556773">SetScope</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetScope method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

