---
UID: NF:wdbgexts.SetThreadForOperation64
title: SetThreadForOperation64 function
author: windows-driver-content
description: The SetThreadForOperation64 function sets the thread to use for the next StackTrace call.
old-location: debugger\setthreadforoperation64.htm
old-project: debugger
ms.assetid: 0c8f7113-0866-454a-9596-8733dd78b282
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: SetThreadForOperation64, SetThreadForOperation64 function [Windows Debugging], WdbgExts_Ref_8c7ef2e9-4096-4284-9878-63d90f49e227.xml, debugger.setthreadforoperation64, wdbgexts/SetThreadForOperation64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	SetThreadForOperation64
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# SetThreadForOperation64 function


## -description


The <b>SetThreadForOperation64</b> function sets the thread to use for the next <a href="..\wdbgexts\nc-wdbgexts-pwindbg_stacktrace_routine.md">StackTrace</a> call.


## -syntax


````
__inline VOID SetThreadForOperation64(
   PULONG64 Thread
);
````


## -parameters




### -param Thread

Points to the thread object to be used for the next stack trace.


## -returns



None




## -remarks



If you are writing 32-bit code, you should use <a href="..\wdbgexts\nf-wdbgexts-setthreadforoperation.md">SetThreadForOperation</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include Wdbgexts.h. For a DbgEng extension, include Wdbgexts.h before Dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.



