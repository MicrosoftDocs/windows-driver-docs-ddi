---
UID: NF:dbgeng.IDebugClient2.WriteDumpFile2
title: IDebugClient2::WriteDumpFile2
author: windows-driver-content
description: The WriteDumpFile2 method creates a user-mode or kernel-modecrash dump file.
old-location: debugger\writedumpfile2.htm
old-project: debugger
ms.assetid: a6cdefc2-8670-485d-979a-8a270dad1c0b
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugClient2 interface [Windows Debugging],WriteDumpFile2 method, IDebugClient2.WriteDumpFile2, IDebugClient2::WriteDumpFile2, IDebugClient3 interface [Windows Debugging],WriteDumpFile2 method, IDebugClient3::WriteDumpFile2, IDebugClient4 interface [Windows Debugging],WriteDumpFile2 method, IDebugClient4::WriteDumpFile2, IDebugClient5 interface [Windows Debugging],WriteDumpFile2 method, IDebugClient5::WriteDumpFile2, IDebugClient_6ce4aeba-f7a6-4872-9ff2-baf3b3165471.xml, WriteDumpFile2, WriteDumpFile2 method [Windows Debugging], WriteDumpFile2 method [Windows Debugging],IDebugClient2 interface, WriteDumpFile2 method [Windows Debugging],IDebugClient3 interface, WriteDumpFile2 method [Windows Debugging],IDebugClient4 interface, WriteDumpFile2 method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::WriteDumpFile2, dbgeng/IDebugClient3::WriteDumpFile2, dbgeng/IDebugClient4::WriteDumpFile2, dbgeng/IDebugClient5::WriteDumpFile2, debugger.writedumpfile2
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient2.WriteDumpFile2
-	IDebugClient3.WriteDumpFile2
-	IDebugClient4.WriteDumpFile2
-	IDebugClient5.WriteDumpFile2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient2::WriteDumpFile2


## -description


The <b>WriteDumpFile2</b> method creates a user-mode or kernel-modecrash dump file.


## -parameters




### -param DumpFile [in]

Specifies the name of the dump file to create.  <i>DumpFile</i> must include the file name extension.  <i>DumpFile</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.


### -param Qualifier [in]

Specifies the type of dump file to create.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541472">DEBUG_DUMP_XXX</a>.


### -param FormatFlags [in]

Specifies flags that determine the format of the dump file and--for user-mode minidumps--what information to include in the file.  For details, see Remarks.


### -param Comment [in, optional]

Specifies a comment string to be included in the crash dump file.  This string is displayed in the debugger console when the dump file is loaded.  Some dump file formats do not support the storing of comment strings.


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
 




## -remarks



The DEBUG_FORMAT_<i>XXX</i> bit-flags are used by <b>WriteDumpFile2</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561389">WriteDumpFileWide</a> to determine the format of a crash dump file and, for user-mode Minidumps, what information to include in the file.

The following bit-flags apply to all crash dump files.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_FORMAT_WRITE_CAB

</td>
<td>
Package the crash dump file in a CAB file.  The supplied file name or file handle is used for the CAB file; the crash dump is first created in a temporary file before being moved into the CAB file.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_CAB_SECONDARY_FILES

</td>
<td>

<dl>
<dt>Include the current symbols and mapped images in the CAB file.</dt>
<dt>If DEBUG_FORMAT_WRITE_CAB is not set, this flag is ignored.</dt>
</dl>


</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_NO_OVERWRITE

</td>
<td>
Do not overwrite existing files.

</td>
</tr>
</table>
 

The following bit-flags can also be included for user-mode Minidumps.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_FULL_MEMORY

</td>
<td>
Add full memory data.  All accessible committed pages owned by the target application will be included.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_HANDLE_DATA

</td>
<td>
Add data about the handles that are associated with the target application.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_UNLOADED_MODULES

</td>
<td>
Add unloaded module information.  This information is available only in Windows Server 2003 and later versions of Windows.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_INDIRECT_MEMORY

</td>
<td>
Add indirect memory.  A small region of memory that surrounds any address that is referenced by a pointer on the stack or backing store is included.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_DATA_SEGMENTS

</td>
<td>
Add all data segments within the executable images.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_FILTER_MEMORY

</td>
<td>
Set to zero all of the memory on the stack and in the backing store that is not useful for recreating the stack trace.  This can make compression of the Minidump more efficient and increase privacy by removing unnecessary information.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_FILTER_PATHS

</td>
<td>
Remove the module paths, leaving only the module names.  This is useful for protecting privacy by hiding the directory structure (which may contain the user's name).

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_PROCESS_THREAD_DATA

</td>
<td>
Add the process environment block (PEB) and thread environment block (TEB).  This flag can be used to provide Windows system information for threads and processes.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_PRIVATE_READ_WRITE_MEMORY

</td>
<td>
Add all committed private read-write memory pages.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_NO_OPTIONAL_DATA

</td>
<td>

<dl>
<dt>Prevent privacy-sensitive data from being included in the Minidump.  Currently, this flag excludes from the Minidump data that would have been added due to the following flags being set:</dt>
<dt>DEBUG_FORMAT_USER_SMALL_PROCESS_THREAD_DATA,</dt>
<dt>DEBUG_FORMAT_USER_SMALL_FULL_MEMORY,</dt>
<dt>DEBUG_FORMAT_USER_SMALL_INDIRECT_MEMORY,</dt>
<dt>DEBUG_FORMAT_USER_SMALL_PRIVATE_READ_WRITE_MEMORY.</dt>
</dl>


</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_FULL_MEMORY_INFO

</td>
<td>
Add all basic memory information.  This is the information returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553502">QueryVirtual</a> method.  The information for all memory is included, not just valid memory, which allows the debugger to reconstruct the complete virtual memory layout from the Minidump.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_THREAD_INFO

</td>
<td>
Add additional thread information, which includes execution time, start time, exit time, start address, and exit status.

</td>
</tr>
<tr>
<td>
DEBUG_FORMAT_USER_SMALL_CODE_SEGMENTS

</td>
<td>
Add all code segments with the executable images.

</td>
</tr>
</table>
 

For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562428">.dump (Create Dump File)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561389">WriteDumpFileWide</a>
 

 

