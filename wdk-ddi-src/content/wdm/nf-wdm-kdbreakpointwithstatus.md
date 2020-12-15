---
UID: NF:wdm.KdBreakPointWithStatus
title: KdBreakPointWithStatus macro (wdm.h)
description: The KdBreakPointWithStatus macro breaks into the kernel debugger and sends the value of Status to the debugger.
old-location: devtest\kdbreakpointwithstatus.htm
tech.root: devtest
ms.date: 02/23/2018
keywords: ["KdBreakPointWithStatus macro"]
ms.keywords: DebugFns_f34fa39a-d436-44db-97ff-3ccdd50384d8.xml, KdBreakPointWithStatus, KdBreakPointWithStatus function [Driver Development Tools], devtest.kdbreakpointwithstatus, ntddk/KdBreakPointWithStatus
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
 - KdBreakPointWithStatus
 - wdm/KdBreakPointWithStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - KdBreakPointWithStatus
---

# KdBreakPointWithStatus macro


## -description

The <b>KdBreakPointWithStatus</b> macro breaks into the kernel debugger and sends the value of <i>Status</i> to the debugger.

## -parameters

### -param s 

[in]
Specifies a ULONG value to be sent to the debugger (for example, a status code or an address).

## -remarks

<b>KdBreakPointWithStatus</b> is identical to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgbreakpointwithstatus">DbgBreakPointWithStatus</a> routine in code that is compiled for a debug configuration. This routine has no effect if compiled in a release configuration.

On x86 computers, the <i>Status</i> parameter is stored in the <b>eax</b> register. On computers that have register calling conventions, <i>Status</i> is stored in the first argument register.

This routine raises an exception that is handled by the kernel debugger if one is installed; otherwise it is handled by the debug system. If a debugger is not connected to the system, the exception can be handled in the standard way.

In kernel mode, a break exception that is not handled will cause a bug check. You can, however, connect a kernel-mode debugger to a target computer that has stopped responding and has kernel debugging enabled. For more information, see <a href="/windows-hardware/drivers/debugger/index">Windows Debugging</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgbreakpoint">DbgBreakPoint</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgbreakpointwithstatus">DbgBreakPointWithStatus</a>



<a href="/previous-versions/windows/hardware/previsioning-framework/ff548063(v=vs.85)">KdBreakPoint</a>



<a href="/windows-hardware/drivers/debugger/index">Windows Debugging</a>
