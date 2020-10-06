---
UID: NF:dbgeng.IDebugControl7.GetDebuggeeType2
title: IDebugControl7::GetDebuggeeType2 (dbgeng.h)
description: The GetDebuggeeType2 method describes the nature of the current target.
old-location: debugger\idebugcontrol7_getdebuggeetype2.htm
tech.root: debugger
ms.assetid: DA1F45F5-5B15-4DAD-A746-E467FE1BAE42
ms.date: 05/03/2018
keywords: ["IDebugControl7::GetDebuggeeType2"]
ms.keywords: GetDebuggeeType2, GetDebuggeeType2 method [Windows Debugging], GetDebuggeeType2 method [Windows Debugging],IDebugControl7 interface, IDebugControl7 interface [Windows Debugging],GetDebuggeeType2 method, IDebugControl7.GetDebuggeeType2, IDebugControl7::GetDebuggeeType2, dbgeng/IDebugControl7::GetDebuggeeType2, debugger.idebugcontrol7_getdebuggeetype2
req.header: dbgeng.h
req.include-header: 
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
 - IDebugControl7::GetDebuggeeType2
 - dbgeng/IDebugControl7::GetDebuggeeType2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl7.GetDebuggeeType2
---

# IDebugControl7::GetDebuggeeType2


## -description

The GetDebuggeeType2 method describes the nature of the current target.

## -parameters

### -param Flags 

[in]
Takes a single flag, DEBUG_EXEC_FLAGS_NONBLOCK, that indicates whether the function GetDebuggeeType2 should own the engine critical section object (g_EngineLock) before finding the debuggee type.



If the Flag is present, then the function  will try to own the critical section. If that fails, it  will continue without blocking the caller thread.


If the flag is not passed in, then the function will wait for the engine critical section to become available before continuing.

### -param Class 

[out]
Receives the class of the current target.  It will be set to one of the values in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_CLASS_UNINITIALIZED

</td>
<td>
There is no current target.

</td>
</tr>
<tr>
<td>
DEBUG_CLASS_KERNEL

</td>
<td>
The current target is a kernel-mode target.

</td>
</tr>
<tr>
<td>
DEBUG_CLASS_USER_WINDOWS

</td>
<td>
The current target is a user-mode target.

</td>
</tr>
</table>

### -param Qualifier 

[out]
Provides more details about the type of the target.  Its interpretation depends on the value of <i>Class</i>.  When class is DEBUG_CLASS_UNINITIALIZED, <i>Qualifier</i> returns zero.  The following values are applicable for kernel-mode targets.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_KERNEL_CONNECTION

</td>
<td>
The current target is a live kernel being debugged in the standard way (using a COM port, 1394 bus, or named pipe).

</td>
</tr>
<tr>
<td>
DEBUG_KERNEL_LOCAL

</td>
<td>
The current target is the local kernel.

</td>
</tr>
<tr>
<td>
DEBUG_KERNEL_EXDI_DRIVER

</td>
<td>
The current target is a live kernel connected using eXDI drivers.

</td>
</tr>
<tr>
<td>
DEBUG_KERNEL_SMALL_DUMP

</td>
<td>
The current target is a kernel-mode Small Memory Dump file.

</td>
</tr>
<tr>
<td>
DEBUG_KERNEL_DUMP

</td>
<td>
The current target is a kernel-mode Kernel Memory Dump file.

</td>
</tr>
<tr>
<td>
DEBUG_KERNEL_FULL_DUMP

</td>
<td>
The current target is a kernel-mode Complete Memory Dump file.

</td>
</tr>
</table>
 

The following values are applicable for user-mode targets.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_USER_WINDOWS_PROCESS

</td>
<td>
The current target is a user-mode process on the same computer as the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a>.

</td>
</tr>
<tr>
<td>
DEBUG_USER_WINDOWS_PROCESS_SERVER

</td>
<td>
The current target is a user-mode process connected using a process server.

</td>
</tr>
<tr>
<td>
DEBUG_USER_WINDOWS_SMALL_DUMP

</td>
<td>
The current target is a user-mode Minidump file.

</td>
</tr>
<tr>
<td>
DEBUG_USER_WINDOWS_DUMP

</td>
<td>
The current target is a Full User-Mode Dump file.

</td>
</tr>
</table>

## -returns

This method does not return a value.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol7">IDebugControl7</a>