---
UID: NF:wdm.KdBreakPointWithStatus
title: KdBreakPointWithStatus macro (wdm.h)
description: The KdBreakPointWithStatus macro breaks into the kernel debugger and sends the value of Status to the debugger.
old-location: devtest\kdbreakpointwithstatus.htm
tech.root: devtest
ms.assetid: 0b7f2f55-f7b8-415b-b683-3b6b96f84eb3
ms.date: 02/23/2018
ms.keywords: DebugFns_f34fa39a-d436-44db-97ff-3ccdd50384d8.xml, KdBreakPointWithStatus, KdBreakPointWithStatus function [Driver Development Tools], devtest.kdbreakpointwithstatus, ntddk/KdBreakPointWithStatus
ms.topic: macro
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- KdBreakPointWithStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# KdBreakPointWithStatus macro


## -description


The <b>KdBreakPointWithStatus</b> macro breaks into the kernel debugger and sends the value of <i>Status</i> to the debugger.


## -parameters




### -param s [in]

Specifies a ULONG value to be sent to the debugger (for example, a status code or an address).



## -remarks



<b>KdBreakPointWithStatus</b> is identical to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543629">DbgBreakPointWithStatus</a> routine in code that is compiled for a debug configuration. This routine has no effect if compiled in a release configuration.

On x86 computers, the <i>Status</i> parameter is stored in the <b>eax</b> register. On computers that have register calling conventions, <i>Status</i> is stored in the first argument register.

This routine raises an exception that is handled by the kernel debugger if one is installed; otherwise it is handled by the debug system. If a debugger is not connected to the system, the exception can be handled in the standard way.

In kernel mode, a break exception that is not handled will cause a bug check. You can, however, connect a kernel-mode debugger to a target computer that has stopped responding and has kernel debugging enabled. For more information, see <a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543626">DbgBreakPoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543629">DbgBreakPointWithStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548063">KdBreakPoint</a>



<a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>
 

 

