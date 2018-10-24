---
UID: NS:dbgeng._DEBUG_THREAD_BASIC_INFORMATION
title: "_DEBUG_THREAD_BASIC_INFORMATION"
author: windows-driver-content
description: The DEBUG_THREAD_BASIC_INFORMATION structure describes an operating system thread.
old-location: debugger\debug_thread_basic_information.htm
tech.root: debugger
ms.assetid: e964ed63-6c00-4308-955c-f8a99490a248
ms.date: 05/03/2018
ms.keywords: "*PDEBUG_THREAD_BASIC_INFORMATION, DEBUG_THREAD_BASIC_INFORMATION, DEBUG_THREAD_BASIC_INFORMATION structure [Windows Debugging], PDEBUG_THREAD_BASIC_INFORMATION, PDEBUG_THREAD_BASIC_INFORMATION structure pointer [Windows Debugging], Structures_e48c9daa-ce4f-4131-9ca6-cb1a7a129fcc.xml, _DEBUG_THREAD_BASIC_INFORMATION, dbgeng/DEBUG_THREAD_BASIC_INFORMATION, dbgeng/PDEBUG_THREAD_BASIC_INFORMATION, debugger.debug_thread_basic_information"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	DbgEng.h
api_name:
-	DEBUG_THREAD_BASIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: DEBUG_THREAD_BASIC_INFORMATION, *PDEBUG_THREAD_BASIC_INFORMATION
---

# _DEBUG_THREAD_BASIC_INFORMATION structure


## -description


The DEBUG_THREAD_BASIC_INFORMATION structure describes an operating system thread.


## -struct-fields




### -field Valid

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
 


### -field ExitStatus

The exit code of the thread. If the thread is still running, <b>ExitStatus</b> is set to STILL_ACTIVE.

<b>ExitStatus</b> is only valid if the  DEBUG_TBINFO_EXIT_STATUS bit flag is set in <b>Valid</b>.


### -field PriorityClass

The priority class of the thread. The priority classes are defined by the <i>XXX</i>_PRIORITY_CLASS constants in WinBase.h. For more information about thread priority classes, see the Platform SDK.

<b>PriorityClass</b> is only valid if the DEBUG_TBINFO_PRIORITY_CLASS bit flag is set in <b>Valid</b>.


### -field Priority

The priority of the thread relative to the priority class. Some thread priorities are defined by the THREAD_PRIORITY_<i>XXX</i> constants in WinBase.h.  For more information about thread priorities,  see the Platform SDK.

<b>Priority</b> is only valid if the DEBUG_TBINFO_PRIORITY bit flag is set in <b>Valid</b>.


### -field CreateTime

The creation time of the thread.

<b>CreateTime</b> is only valid if the DEBUG_TBINFO_TIMES bit flag is set in <b>Valid</b>.


### -field ExitTime

The exit time of the thread.

<b>ExitTime</b> is only valid if the DEBUG_TBINFO_TIMES bit flag is set in <b>Valid</b>.


### -field KernelTime

The amount of time the thread has executed in kernel mode.

<b>KernelTime</b> is only valid if the DEBUG_TBINFO_TIMES bit flag is set in <b>Valid</b>.


### -field UserTime

The amount of time the thread has executed in user-mode.

<b>UserTime</b> is only valid if the DEBUG_TBINFO_TIMES bit flag is set in <b>Valid</b>.


### -field StartOffset

The starting address of the thread.

<b>StartOffset</b> is only valid if the DEBUG_TBINFO_START_OFFSET bit flag is set in <b>Valid</b>.


### -field Affinity

The thread affinity mask for the thread in a Symmetric Multiple Processor (SMP) computer. For more information about the thread affinity mask, see the Platform SDK.

<b>Affinity</b> is only valid if the DEBUG_TBINFO_AFFINITY bit flag is set in <b>Valid</b>.

