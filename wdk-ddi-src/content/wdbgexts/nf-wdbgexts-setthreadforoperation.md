---
UID: NF:wdbgexts.SetThreadForOperation
title: SetThreadForOperation function (wdbgexts.h)
description: The SetThreadForOperation function sets the thread to use for the next StackTrace call.
old-location: debugger\setthreadforoperation.htm
tech.root: debugger
ms.assetid: b5bae644-6c8d-4346-87bd-211efcf27748
ms.date: 05/03/2018
keywords: ["SetThreadForOperation function"]
ms.keywords: SetThreadForOperation, SetThreadForOperation function [Windows Debugging], WdbgExts_Ref_62cb59e2-5a16-4bee-936c-6eeaa5126fbc.xml, debugger.setthreadforoperation, wdbgexts/SetThreadForOperation
f1_keywords:
 - "wdbgexts/SetThreadForOperation"
 - "SetThreadForOperation"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdbgexts.h
api_name:
- SetThreadForOperation
targetos: Windows
req.typenames: 
---

# SetThreadForOperation function


## -description


The <b>SetThreadForOperation</b> function sets the thread to use for the next <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_stacktrace_routine">StackTrace</a> call.


## -parameters




### -param Thread

Points to a thread object to be used for the next stack trace.


## -remarks



If you are writing 64-bit code, you should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-setthreadforoperation64">SetThreadForOperation64</a> instead. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/32-bit-pointers-and-64-bit-pointers">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include Wdbgexts.h. For a DbgEng extension, include Wdbgexts.h before Dbgeng.h. See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details.



