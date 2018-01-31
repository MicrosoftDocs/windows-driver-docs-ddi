---
UID: NS:dbgeng._DEBUG_THREAD_BASIC_INFORMATION
title: "_DEBUG_THREAD_BASIC_INFORMATION"
author: windows-driver-content
description: The DEBUG_THREAD_BASIC_INFORMATION structure describes an operating system thread.
old-location: debugger\debug_thread_basic_information.htm
old-project: debugger
ms.assetid: e964ed63-6c00-4308-955c-f8a99490a248
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/DEBUG_THREAD_BASIC_INFORMATION, dbgeng/PDEBUG_THREAD_BASIC_INFORMATION, Structures_e48c9daa-ce4f-4131-9ca6-cb1a7a129fcc.xml, DEBUG_THREAD_BASIC_INFORMATION structure [Windows Debugging], debugger.debug_thread_basic_information, PDEBUG_THREAD_BASIC_INFORMATION structure pointer [Windows Debugging], _DEBUG_THREAD_BASIC_INFORMATION, PDEBUG_THREAD_BASIC_INFORMATION, *PDEBUG_THREAD_BASIC_INFORMATION, DEBUG_THREAD_BASIC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	DbgEng.h
apiname:
-	DEBUG_THREAD_BASIC_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PDEBUG_THREAD_BASIC_INFORMATION, DEBUG_THREAD_BASIC_INFORMATION"
---

# _DEBUG_THREAD_BASIC_INFORMATION structure


## -description


The DEBUG_THREAD_BASIC_INFORMATION structure describes an operating system thread.


## -syntax


````
typedef struct _DEBUG_THREAD_BASIC_INFORMATION {
  ULONG   Valid;
  ULONG   ExitStatus;
  ULONG   PriorityClass;
  ULONG   Priority;
  ULONG64 CreateTime;
  ULONG64 ExitTime;
  ULONG64 KernelTime;
  ULONG64 UserTime;
  ULONG64 StartOffset;
  ULONG64 Affinity;
}  DEBUG_THREAD_BASIC_INFORMATION, *PDEBUG_THREAD_BASIC_INFORMATION;
````


## -struct-fields




#### - Valid

A bitset that specifies which other members of the structure contain valid information. A member of the structure is valid if the corresponding bit flag is set in <b>Valid</b>.
<table>
<tr>
<th>Flag</th>
<th>Members</th>
</tr>
<tr>
<td>
DEBUG_TBINFO_EXIT_STATUS

</td>
<td>
<b>ExitStatus</b>

</td>
</tr>
<tr>
<td>
DEBUG_TBINFO_PRIORITY_CLASS

</td>
<td>
<b>PriorityClass</b>

</td>
</tr>
<tr>
<td>
DEBUG_TBINFO_PRIORITY

</td>
<td>
<b>Priority</b>

</td>
</tr>
<tr>
<td>
DEBUG_TBINFO_TIMES

</td>
<td>
<b>CreateTime</b>, <b>ExitTime</b>, <b>KernelTime</b>, <b> UserTime</b>

</td>
</tr>
<tr>
<td>
DEBUG_TBINFO_START_OFFSET

</td>
<td>
<b>StartOffset</b>

</td>
</tr>
<tr>
<td>
DEBUG_TBINFO_AFFINITY

</td>
<td>
<b>Affinity</b>

</td>
</tr>
</table> 


#### - ExitStatus

The exit code of the thread. If the thread is still running, <b>ExitStatus</b> is set to STILL_ACTIVE.

<b>ExitStatus</b> is only valid if the  DEBUG_TBINFO_EXIT_STATUS bit flag is set in <b>Valid</b>.


#### - PriorityClass

The priority class of the thread. The priority classes are defined by the <i>XXX</i>_PRIORITY_CLASS constants in WinBase.h. For more information about thread priority classes, see the Platform SDK.

<b>PriorityClass</b> is only valid if the DEBUG_TBINFO_PRIORITY_CLASS bit flag is set in <b>Valid</b>.


#### - Priority

The priority of the thread relative to the priority class. Some thread priorities are defined by the THREAD_PRIORITY_<i>XXX</i> constants in WinBase.h.  For more information about thread priorities,  see the Platform SDK.

<b>Priority</b> is only valid if the DEBUG_TBINFO_PRIORITY bit flag is set in <b>Valid</b>.


#### - CreateTime

The creation time of the thread.

<b>CreateTime</b> is only valid if the DEBUG_TBINFO_TIMES bit flag is set in <b>Valid</b>.


#### - ExitTime

The exit time of the thread.

<b>ExitTime</b> is only valid if the DEBUG_TBINFO_TIMES bit flag is set in <b>Valid</b>.


#### - KernelTime

The amount of time the thread has executed in kernel mode.

<b>KernelTime</b> is only valid if the DEBUG_TBINFO_TIMES bit flag is set in <b>Valid</b>.


#### - UserTime

The amount of time the thread has executed in user-mode.

<b>UserTime</b> is only valid if the DEBUG_TBINFO_TIMES bit flag is set in <b>Valid</b>.


#### - StartOffset

The starting address of the thread.

<b>StartOffset</b> is only valid if the DEBUG_TBINFO_START_OFFSET bit flag is set in <b>Valid</b>.


#### - Affinity

The thread affinity mask for the thread in a Symmetric Multiple Processor (SMP) computer. For more information about the thread affinity mask, see the Platform SDK.

<b>Affinity</b> is only valid if the DEBUG_TBINFO_AFFINITY bit flag is set in <b>Valid</b>.

