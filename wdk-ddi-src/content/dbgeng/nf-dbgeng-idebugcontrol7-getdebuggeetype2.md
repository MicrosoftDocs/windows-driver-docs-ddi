---
UID: NF:dbgeng.IDebugControl7.GetDebuggeeType2
title: IDebugControl7::GetDebuggeeType2 method
author: windows-driver-content
description: The GetDebuggeeType2 method describes the nature of the current target.
old-location: debugger\idebugcontrol7_getdebuggeetype2.htm
old-project: debugger
ms.assetid: DA1F45F5-5B15-4DAD-A746-E467FE1BAE42
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetDebuggeeType2 method [Windows Debugging], IDebugControl7 interface, IDebugControl7 interface [Windows Debugging], GetDebuggeeType2 method, IDebugControl7::GetDebuggeeType2, IDebugControl7, GetDebuggeeType2, GetDebuggeeType2 method [Windows Debugging], debugger.idebugcontrol7_getdebuggeetype2, dbgeng/IDebugControl7::GetDebuggeeType2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	dbgeng.h
apiname: 
-	IDebugControl7.GetDebuggeeType2
product: Windows
targetos: Windows
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl7::GetDebuggeeType2 method


## -description


The GetDebuggeeType2 method describes the nature of the current target. 


## -syntax


````
void GetDebuggeeType2(
  [in]  ULONG  Flags,
  [out] PULONG Class,
  [out] PULONG Qualifier
);
````


## -parameters




### -param Flags [in]

Takes a single flag, DEBUG_EXEC_FLAGS_NONBLOCK, that indicates whether the function GetDebuggeeType2 should own the engine critical section object (g_EngineLock) before finding the debuggee type.



If the Flag is present, then the function  will try to own the critical section. If that fails, it  will continue without blocking the caller thread.


If the flag is not passed in, then the function will wait for the engine critical section to become available before continuing.


### -param Class [out]

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


### -param Qualifier [out]

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
The current target is a user-mode process on the same computer as the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.

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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol7.md">IDebugControl7</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl7::GetDebuggeeType2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

