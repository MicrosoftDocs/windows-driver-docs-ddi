---
UID: NC:wdbgexts.PWINDBG_GET_THREAD_CONTEXT_ROUTINE
title: PWINDBG_GET_THREAD_CONTEXT_ROUTINE
author: windows-driver-content
description: The PWINDBG_GET_THREAD_CONTEXT_ROUTINE (GetContext) function implements the functionality that is similar to the Microsoft Win32 GetThreadContext routine. It returns the context of the process being debugged.
old-location: debugger\getcontext.htm
old-project: debugger
ms.assetid: 706e05ae-9507-4414-b02c-52016e7bbbd9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetContext, GetContext callback function [Windows Debugging], PWINDBG_GET_THREAD_CONTEXT_ROUTINE, WdbgExts_Ref_52639fac-abbf-4abc-a01f-361d14e49fd0.xml, debugger.getcontext, wdbgexts/GetContext
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdbgexts.h
api_name:
-	GetContext
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---

# PWINDBG_GET_THREAD_CONTEXT_ROUTINE callback


## -description


The <b>PWINDBG_GET_THREAD_CONTEXT_ROUTINE</b> (<b>GetContext</b>) function implements the functionality that is similar to the Microsoft Win32 <b>GetThreadContext</b> routine. It returns the context of the process being debugged. 


## -parameters




### -param Processor


### -param lpContext [out]

Points to the address of a context structure that receives the appropriate context of the process being debugged. The context structure is highly machine-specific. 


### -param cbSizeOfContext [in]

Specifies the size of the context structure.


#### - Target [in]

<b>User mode:</b>  Specifies the thread ID of the thread being debugged.

<b>Kernel Mode:</b>  Specifies the processor number of the processor being debugged.


## -returns



If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>. 



