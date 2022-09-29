---
UID: NF:wdm.DbgBreakPoint
title: DbgBreakPoint function (wdm.h)
description: The DbgBreakPoint routine breaks into the kernel debugger.
old-location: devtest\dbgbreakpoint.htm
tech.root: devtest
ms.date: 02/23/2018
keywords: ["DbgBreakPoint function"]
ms.keywords: DbgBreakPoint, DbgBreakPoint routine [Driver Development Tools], DebugFns_f53df634-d9a5-4b98-ad10-560e6e4e5a66.xml, devtest.dbgbreakpoint, ntddk/DbgBreakPoint
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DbgBreakPoint
 - wdm/DbgBreakPoint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtDll.dll
 - NtosKrnl.exe
api_name:
 - DbgBreakPoint
---

# DbgBreakPoint function


## -description

The <b>DbgBreakPoint</b> routine breaks into the kernel debugger.

## -returns

None

## -remarks

The <b>DbgBreakPoint</b> routine is the kernel-mode equivalent of <b>DebugBreak</b>.

This routine raises an exception that is handled by the kernel debugger if one is installed; otherwise, it is handled by the debug system. If a debugger is not connected to the system, the exception can be handled in the standard way.

In kernel mode, a break exception that is not handled will cause a bug check. You can, however, connect a kernel-mode debugger to a target computer that has stopped responding and has kernel debugging enabled. For more information, see <a href="/windows-hardware/drivers/debugger/index">Windows Debugging</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgbreakpointwithstatus">DbgBreakPointWithStatus</a>



<a href="/previous-versions/windows/hardware/previsioning-framework/ff548063(v=vs.85)">KdBreakPoint</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kdbreakpointwithstatus">KdBreakPointWithStatus</a>
