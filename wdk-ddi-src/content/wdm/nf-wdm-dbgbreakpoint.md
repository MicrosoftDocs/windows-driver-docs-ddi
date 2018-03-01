---
UID: NF:wdm.DbgBreakPoint
title: DbgBreakPoint function
author: windows-driver-content
description: The DbgBreakPoint routine breaks into the kernel debugger.
old-location: devtest\dbgbreakpoint.htm
old-project: devtest
ms.assetid: deeac910-2cc3-4a54-bf3b-aeb56d0004dc
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DbgBreakPoint, DbgBreakPoint routine [Driver Development Tools], DebugFns_f53df634-d9a5-4b98-ad10-560e6e4e5a66.xml, devtest.dbgbreakpoint, ntddk/DbgBreakPoint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
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
req.lib: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtDll.dll
-	NtosKrnl.exe
api_name:
-	DbgBreakPoint
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# DbgBreakPoint function


## -description


The <b>DbgBreakPoint</b> routine breaks into the kernel debugger.


## -syntax


````
VOID DbgBreakPoint(void);
````


## -parameters






## -returns



None




## -remarks



The <b>DbgBreakPoint</b> routine is the kernel-mode equivalent of <b>DebugBreak</b>.

This routine raises an exception that is handled by the kernel debugger if one is installed; otherwise, it is handled by the debug system. If a debugger is not connected to the system, the exception can be handled in the standard way.

In kernel mode, a break exception that is not handled will cause a bug check. You can, however, connect a kernel-mode debugger to a target computer that has stopped responding and has kernel debugging enabled. For more information, see <a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548063">KdBreakPoint</a>



<a href="..\wdm\nf-wdm-kdbreakpointwithstatus.md">KdBreakPointWithStatus</a>



<a href="..\wdm\nf-wdm-dbgbreakpointwithstatus.md">DbgBreakPointWithStatus</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20DbgBreakPoint routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

