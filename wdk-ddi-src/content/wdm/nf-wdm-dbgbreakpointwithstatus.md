---
UID: NF:wdm.DbgBreakPointWithStatus
title: DbgBreakPointWithStatus function
author: windows-driver-content
description: The DbgBreakPointWithStatus routine breaks into the kernel debugger and sends the value of Status to the debugger.
old-location: devtest\dbgbreakpointwithstatus.htm
tech.root: devtest
ms.assetid: d508c9de-5fae-47c1-88fa-df9048662419
ms.date: 02/23/2018
ms.keywords: DbgBreakPointWithStatus, DbgBreakPointWithStatus routine [Driver Development Tools], DebugFns_d958e007-b135-46b0-a407-1843da2e61c0.xml, devtest.dbgbreakpointwithstatus, ntddk/DbgBreakPointWithStatus
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DebugBreakUsage
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntdll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	DbgBreakPointWithStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# DbgBreakPointWithStatus function


## -description


The <b>DbgBreakPointWithStatus</b> routine breaks into the kernel debugger and sends the value of <i>Status</i> to the debugger.


## -parameters




### -param Status [in]

Specifies a ULONG value that is sent to the debugger (for example, a status code or an address).


## -returns



None




## -remarks



<b>DbgBreakPointWithStatus</b> is identical to <b>DbgBreakPoint</b>, except for the <i>Status</i> message.

On x86 computers, the <i>Status</i> parameter is stored in the <b>eax</b> register. On machines that have register calling conventions, <i>Status</i> is stored in the first argument register.

This routine raises an exception that is handled by the kernel debugger if one is installed; otherwise it is handled by the debug system. If a debugger is not connected to the system, the exception can be handled in the standard way.

In kernel mode, a break exception that is not handled will cause a bug check. You can, however, connect a kernel-mode debugger to a target computer that has stopped responding and has kernel debugging enabled. For more information, see <a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543626">DbgBreakPoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548063">KdBreakPoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548065">KdBreakPointWithStatus</a>
 

 

