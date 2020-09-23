---
UID: NF:wdbgexts.SetThreadForOperation64
title: SetThreadForOperation64 function (wdbgexts.h)
description: The SetThreadForOperation64 function sets the thread to use for the next StackTrace call.
old-location: debugger\setthreadforoperation64.htm
tech.root: debugger
ms.assetid: 0c8f7113-0866-454a-9596-8733dd78b282
ms.date: 05/03/2018
keywords: ["SetThreadForOperation64 function"]
ms.keywords: SetThreadForOperation64, SetThreadForOperation64 function [Windows Debugging], WdbgExts_Ref_8c7ef2e9-4096-4284-9878-63d90f49e227.xml, debugger.setthreadforoperation64, wdbgexts/SetThreadForOperation64
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
 - SetThreadForOperation64
 - wdbgexts/SetThreadForOperation64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - SetThreadForOperation64
---

# SetThreadForOperation64 function


## -description

The <b>SetThreadForOperation64</b> function sets the thread to use for the next <a href="/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_stacktrace_routine">StackTrace</a> call.

## -parameters

### -param Thread

Points to the thread object to be used for the next stack trace.

## -remarks

If you are writing 32-bit code, you should use <a href="/windows-hardware/drivers/ddi/wdbgexts/nf-wdbgexts-setthreadforoperation">SetThreadForOperation</a> instead. See <a href="/windows-hardware/drivers/debugger/32-bit-pointers-and-64-bit-pointers">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include Wdbgexts.h. For a DbgEng extension, include Wdbgexts.h before Dbgeng.h. See <a href="/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details.