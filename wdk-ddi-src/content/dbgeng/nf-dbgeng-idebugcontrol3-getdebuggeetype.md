---
UID: NF:dbgeng.IDebugControl3.GetDebuggeeType
title: IDebugControl3::GetDebuggeeType method
author: windows-driver-content
description: The GetDebuggeeType method describes the nature of the current target.
old-location: debugger\getdebuggeetype.htm
old-project: debugger
ms.assetid: 86f236fa-73f8-4071-b6da-6de2d276cbff
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl_4179686c-b047-41f5-98cc-28f2c6bd852d.xml, GetDebuggeeType method [Windows Debugging], IDebugControl3 interface, IDebugControl3, GetDebuggeeType method [Windows Debugging], IDebugControl2 interface, debugger.getdebuggeetype, GetDebuggeeType method [Windows Debugging], IDebugControl interface, GetDebuggeeType method [Windows Debugging], IDebugControl interface [Windows Debugging], GetDebuggeeType method, dbgeng/IDebugControl2::GetDebuggeeType, IDebugControl3::GetDebuggeeType, dbgeng/IDebugControl::GetDebuggeeType, IDebugControl3 interface [Windows Debugging], GetDebuggeeType method, dbgeng/IDebugControl3::GetDebuggeeType, IDebugControl2 interface [Windows Debugging], GetDebuggeeType method, IDebugControl2, IDebugControl, GetDebuggeeType, IDebugControl::GetDebuggeeType, IDebugControl2::GetDebuggeeType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	IDebugControl.GetDebuggeeType
-	IDebugControl2.GetDebuggeeType
-	IDebugControl3.GetDebuggeeType
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl3::GetDebuggeeType method


## -description


The <b>GetDebuggeeType</b> method describes the nature of the current target.


## -syntax


````
HRESULT GetDebuggeeType(
  [out] PULONG Class,
  [out] PULONG Qualifier
);
````


## -parameters




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



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 



