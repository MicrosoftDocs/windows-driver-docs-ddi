---
UID: NC:wdbgexts.PWINDBG_SET_THREAD_CONTEXT_ROUTINE
title: PWINDBG_SET_THREAD_CONTEXT_ROUTINE (wdbgexts.h)
description: The PWINDBG_SET_THREAD_CONTEXT_ROUTINE (SetContext) function is similar to the Win32 SetThreadContext routine. It sets the context of the process being debugged.
old-location: debugger\setcontext.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["PWINDBG_SET_THREAD_CONTEXT_ROUTINE callback function"]
ms.keywords: PWINDBG_SET_THREAD_CONTEXT_ROUTINE, PWINDBG_SET_THREAD_CONTEXT_ROUTINE callback, SetContext, SetContext callback function [Windows Debugging], WdbgExts_Ref_1a94f80d-7df9-45d1-9bca-19a18a2efb22.xml, debugger.setcontext, wdbgexts/SetContext
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PWINDBG_SET_THREAD_CONTEXT_ROUTINE
 - wdbgexts/PWINDBG_SET_THREAD_CONTEXT_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wdbgexts.h
api_name:
 - PWINDBG_SET_THREAD_CONTEXT_ROUTINE
---

# PWINDBG_SET_THREAD_CONTEXT_ROUTINE callback function


## -description

The <b>PWINDBG_SET_THREAD_CONTEXT_ROUTINE</b> (<b>SetContext</b>) function is similar to the Win32 <b>SetThreadContext</b> routine. It sets the context of the process being debugged.

## -parameters

### -param Processor

### -param lpContext 

[out]
Points to the address of a context structure that contains the context to be set for the process being debugged. The context structure is highly machine-specific.

### -param cbSizeOfContext 

[in]
Specifies the size of the context structure.


#### - Target [in]

<b>User mode:</b>  Specifies the thread ID of the thread being debugged.

<b>Kernel Mode:</b>  Specifies the processor number of the processor being debugged.

## -returns

If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

