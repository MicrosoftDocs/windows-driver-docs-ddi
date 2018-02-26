---
UID: NC:wdbgexts.PWINDBG_SET_THREAD_CONTEXT_ROUTINE
title: PWINDBG_SET_THREAD_CONTEXT_ROUTINE
author: windows-driver-content
description: The PWINDBG_SET_THREAD_CONTEXT_ROUTINE (SetContext) function is similar to the Win32 SetThreadContext routine. It sets the context of the process being debugged.
old-location: debugger\setcontext.htm
old-project: debugger
ms.assetid: ca40f869-2b6e-4317-b568-09c5962b629a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PWINDBG_SET_THREAD_CONTEXT_ROUTINE, SetContext, SetContext callback function [Windows Debugging], WdbgExts_Ref_1a94f80d-7df9-45d1-9bca-19a18a2efb22.xml, debugger.setcontext, wdbgexts/SetContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdbgexts.h
apiname:
-	SetContext
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---

# PWINDBG_SET_THREAD_CONTEXT_ROUTINE callback


## -description


The <b>PWINDBG_SET_THREAD_CONTEXT_ROUTINE</b> (<b>SetContext</b>) function is similar to the Win32 <b>SetThreadContext</b> routine. It sets the context of the process being debugged.


## -prototype


````
ULONG  SetContext(
  _In_  ULONG    Target,
  _Out_ PCONTEXT lpContext,
  _In_  ULONG    cbSizeOfContext
);
````


## -parameters




### -param Processor


### -param lpContext [out]

Points to the address of a context structure that contains the context to be set for the process being debugged. The context structure is highly machine-specific. 


### -param cbSizeOfContext [in]

Specifies the size of the context structure.


#### - Target [in]

<b>User mode:</b>  Specifies the thread ID of the thread being debugged.

<b>Kernel Mode:</b>  Specifies the processor number of the processor being debugged.


## -returns



If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.



