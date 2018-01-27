---
UID: NF:wdbgexts.SetThreadForOperation
title: SetThreadForOperation function
author: windows-driver-content
description: The SetThreadForOperation function sets the thread to use for the next StackTrace call.
old-location: debugger\setthreadforoperation.htm
old-project: debugger
ms.assetid: b5bae644-6c8d-4346-87bd-211efcf27748
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.setthreadforoperation, SetThreadForOperation, SetThreadForOperation function [Windows Debugging], WdbgExts_Ref_62cb59e2-5a16-4bee-936c-6eeaa5126fbc.xml, wdbgexts/SetThreadForOperation
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wdbgexts.h
apiname: 
-	SetThreadForOperation
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# SetThreadForOperation function


## -description


The <b>SetThreadForOperation</b> function sets the thread to use for the next <a href="..\wdbgexts\nc-wdbgexts-pwindbg_stacktrace_routine.md">StackTrace</a> call.


## -syntax


````
__inline VOID SetThreadForOperation(
   ULONG_PTR *Thread
);
````


## -parameters




### -param Thread

Points to a thread object to be used for the next stack trace.


## -returns


None



## -remarks


If you are writing 64-bit code, you should use <a href="..\wdbgexts\nf-wdbgexts-setthreadforoperation64.md">SetThreadForOperation64</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include Wdbgexts.h. For a DbgEng extension, include Wdbgexts.h before Dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.


