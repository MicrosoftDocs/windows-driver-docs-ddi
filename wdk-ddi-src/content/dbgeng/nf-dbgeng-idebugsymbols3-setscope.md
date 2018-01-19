---
UID: NF:dbgeng.IDebugSymbols3.SetScope
title: IDebugSymbols3::SetScope method
author: windows-driver-content
description: The SetScope method sets the current scope.
old-location: debugger\setscope.htm
old-project: debugger
ms.assetid: 78a32ba6-5546-486a-aede-9a597b27f9fb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::SetScope, SetScope
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
req.alt-api: IDebugSymbols.SetScope,IDebugSymbols2.SetScope,IDebugSymbols3.SetScope
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

# IDebugSymbols3::SetScope method



## -description
The <b>SetScope</b> method sets the current scope.



## -syntax

````
HRESULT SetScope(
  [in]           ULONG64            InstructionOffset,
  [in, optional] PDEBUG_STACK_FRAME ScopeFrame,
  [in, optional] PVOID              ScopeContext,
  [in]           ULONG              ScopeContextSize
);
````


## -parameters

### -param InstructionOffset [in]

Specifies the location in the process's virtual address space for the scope's current instruction.  This is only used if both <i>ScopeFrame</i> and <i>ScopeContext</i> are <b>NULL</b>; otherwise, it is ignored.


### -param ScopeFrame [in, optional]

Specifies the scope's stack frame.  For information about this structure, see <a href="..\dbgeng\ns-dbgeng-_debug_stack_frame.md">DEBUG_STACK_FRAME</a>.


### -param ScopeContext [in, optional]

Specifies the scope's <a href="debugger.scopes_and_symbol_groups#thread_context#thread_context">thread context</a>.  The type of the thread context is the CONTEXT structure for the target's effective processor.  The buffer <i>ScopeContext</i> must be large enough to hold this structure.  If <i>ScopeContext</i> is <b>NULL</b>, the current <a href="debugger.changing_contexts#register_context#register_context">register context</a> is used instead.


### -param ScopeContextSize [in]

Specifies the size of the buffer <i>ScopeContext</i>.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The scope identified by <i>InstructionOffset</i>, <i>ScopeFrame</i>, and <i>ScopeContext</i> is the same as the old scope.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The scope has changed.

 


## -remarks
If only <i>InstructionOffset</i> is provided, the scope can be used to look up symbol names; however, the values of these symbols will not be available.

To set the scope to a previous state, <i>ScopeContext</i> must be provided.  This is not always necessary (for example, if you only wish to access the symbols and not the <a href="debugger.x86_architecture#registers#registers">registers</a>).  To set the scope to a frame on the current stack, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556774">SetScopeFrameByIndex</a> can be used.

For more information about scopes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548270">GetScope</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554577">ResetScope</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556774">SetScopeFrameByIndex</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::SetScope method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

