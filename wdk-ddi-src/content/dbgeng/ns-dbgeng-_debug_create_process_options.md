---
UID: NS:dbgeng._DEBUG_CREATE_PROCESS_OPTIONS
title: "_DEBUG_CREATE_PROCESS_OPTIONS"
author: windows-driver-content
description: The DEBUG_CREATE_PROCESS_OPTIONS structure specifies the process creation options to use when creating a new process.
old-location: debugger\debug_create_process_options.htm
tech.root: debugger
ms.assetid: b4b279c2-d44a-442d-9f1d-0ac0d2304eb8
ms.date: 5/3/2018
ms.keywords: "*PDEBUG_CREATE_PROCESS_OPTIONS, DEBUG_CREATE_PROCESS_OPTIONS, DEBUG_CREATE_PROCESS_OPTIONS structure [Windows Debugging], PDEBUG_CREATE_PROCESS_OPTIONS, PDEBUG_CREATE_PROCESS_OPTIONS structure pointer [Windows Debugging], Structures_2dc7014a-a1c3-4d31-b754-834f5d06c482.xml, _DEBUG_CREATE_PROCESS_OPTIONS, dbgeng/DEBUG_CREATE_PROCESS_OPTIONS, dbgeng/PDEBUG_CREATE_PROCESS_OPTIONS, debugger.debug_create_process_options"
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
-	DEBUG_CREATE_PROCESS_OPTIONS
product:
- Windows
targetos: Windows
req.typenames: DEBUG_CREATE_PROCESS_OPTIONS, *PDEBUG_CREATE_PROCESS_OPTIONS
---

# _DEBUG_CREATE_PROCESS_OPTIONS structure


## -description


The DEBUG_CREATE_PROCESS_OPTIONS structure specifies the process creation options to use when creating a new process.


## -struct-fields




### -field CreateFlags

The flags to use when creating the process.   In addition to the flags described in the "Process Creation Flags" topic in the Platform SDK documentation, the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> uses the following flags when creating a process.

<table>
<tr>
<th>Values</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_CREATE_PROCESS_NO_DEBUG_HEAP

</td>
<td>
(Microsoft Windows Server 2003 and later)  Prevents the debug heap from being used in the new process.

</td>
</tr>
<tr>
<td>
DEBUG_CREATE_PROCESS_THROUGH_RTL

</td>
<td>
The native NT RTL process creation routines should be used instead of Win32.  This is only meaningful for special processes that run as NT native processes. No Win32 process can be created with this flag.

</td>
</tr>
</table>
 

When creating and attaching to a process through the debugger engine, set one of the Platform SDK's process creation flags: DEBUG_PROCESS or DEBUG_ONLY_THIS_PROCESS.


### -field EngCreateFlags

The engine specific flags used when creating the process.  <b>EngCreateFlags</b> is a combination of the following bit-flags:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_ECREATE_PROCESS_INHERIT_HANDLES

</td>
<td>
The new process will inherit system handles from the debugger or process server.

</td>
</tr>
<tr>
<td>
DEBUG_ECREATE_PROCESS_USE_VERIFIER_FLAGS

</td>
<td>
(Windows Vista and later)  Use Application Verifier flags in the <b>VerifierFlags</b> field.

</td>
</tr>
<tr>
<td>
DEBUG_ECREATE_PROCESS_USE_IMPLICIT_COMMAND_LINE

</td>
<td>
Use the debugger's or process server's implicit command line to start the process instead of a supplied command line.

</td>
</tr>
</table>
 


### -field VerifierFlags

The Application Verifier flags.  Only used if DEBUG_ECREATE_PROCESS_USE_VERIFIER_FLAGS is set in the <b>EngCreateFlags</b> field.  For possible values, see the <a href="https://msdn.microsoft.com/d3040254-aa9b-4aae-b850-966078df7988">Application Verifier</a> documentation. 


### -field Reserved

Set to zero.

