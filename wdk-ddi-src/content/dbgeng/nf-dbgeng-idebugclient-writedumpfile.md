---
UID: NF:dbgeng.IDebugClient.WriteDumpFile
title: IDebugClient::WriteDumpFile (dbgeng.h)
description: The WriteDumpFile method creates a user-mode or kernel-modecrash dump file.
old-location: debugger\writedumpfile.htm
tech.root: debugger
ms.assetid: 5f410561-b848-471e-8230-f12aa512a897
ms.date: 05/03/2018
ms.keywords: IDebugClient interface [Windows Debugging],WriteDumpFile method, IDebugClient.WriteDumpFile, IDebugClient2 interface [Windows Debugging],WriteDumpFile method, IDebugClient2::WriteDumpFile, IDebugClient3 interface [Windows Debugging],WriteDumpFile method, IDebugClient3::WriteDumpFile, IDebugClient4 interface [Windows Debugging],WriteDumpFile method, IDebugClient4::WriteDumpFile, IDebugClient5 interface [Windows Debugging],WriteDumpFile method, IDebugClient5::WriteDumpFile, IDebugClient::WriteDumpFile, IDebugClient_d9fa8d64-3c92-425b-82fc-dec8553bdb52.xml, WriteDumpFile, WriteDumpFile method [Windows Debugging], WriteDumpFile method [Windows Debugging],IDebugClient interface, WriteDumpFile method [Windows Debugging],IDebugClient2 interface, WriteDumpFile method [Windows Debugging],IDebugClient3 interface, WriteDumpFile method [Windows Debugging],IDebugClient4 interface, WriteDumpFile method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::WriteDumpFile, dbgeng/IDebugClient3::WriteDumpFile, dbgeng/IDebugClient4::WriteDumpFile, dbgeng/IDebugClient5::WriteDumpFile, dbgeng/IDebugClient::WriteDumpFile, debugger.writedumpfile
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugClient.WriteDumpFile"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugClient.WriteDumpFile
- IDebugClient2.WriteDumpFile
- IDebugClient3.WriteDumpFile
- IDebugClient4.WriteDumpFile
- IDebugClient5.WriteDumpFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient::WriteDumpFile


## -description


The <b>WriteDumpFile</b> method creates a user-mode or kernel-modecrash dump file.


## -parameters




### -param DumpFile [in]

Specifies the name of the dump file to create.  <i>DumpFile</i> must include the file name extension.  <i>DumpFile</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.


### -param Qualifier [in]

Specifies the type of dump file to create.  For possible values, see Remarks.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



The DEBUG_DUMP_<i>XXX</i> constants are used by the methods <b>WriteDumpFile</b>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-writedumpfile2">WriteDumpFile2</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-writedumpfilewide">WriteDumpFileWide</a> to specify the type of crash dump file to create.

The possible values include the following.

<table>
<tr>
<th>Constant</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>DEBUG_DUMP_SMALL</b>

</td>
<td>
Creates a Small Memory Dump (kernel-mode) or Minidump (user-mode).

</td>
</tr>
<tr>
<td>
<b>DEBUG_DUMP_DEFAULT</b>

</td>
<td>
Creates a Full User-Mode Dump (user-mode) or Kernel Summary Dump (kernel-mode).

</td>
</tr>
<tr>
<td>
<b>DEBUG_DUMP_FULL</b>

</td>
<td>

         Creates a Complete Memory Dump (kernel-mode only).

</td>
</tr>
</table>
 

To specify the formatting of the file and--for user-mode minidumps--the information to include in the file, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-writedumpfile2">WriteDumpFile2</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-writedumpfilewide">WriteDumpFileWide</a>.

For more information about crash dump files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/dump-file-targets">Dump-File Targets</a>.

Moreover, the following aliases are available for kernel-mode debugging.

<table>
<tr>
<th>Alias</th>
<th>Value</th>
</tr>
<tr>
<td>DEBUG_KERNEL_SMALL_DUMP</td>
<td>
DEBUG_DUMP_SMALL

</td>
</tr>
<tr>
<td>DEBUG_KERNEL_DUMP</td>
<td>
DEBUG_DUMP_DEFAULT

</td>
</tr>
<tr>
<td>DEBUG_KERNEL_FULL_DUMP</td>
<td>
DEBUG_DUMP_FULL

</td>
</tr>
</table>
 

Additionally, the following aliases are available for user-mode debugging.

<table>
<tr>
<th>Alias</th>
<th>Value</th>
</tr>
<tr>
<td>DEBUG_USER_WINDOWS_SMALL_DUMP</td>
<td>
DEBUG_DUMP_SMALL

</td>
</tr>
<tr>
<td>DEBUG_USER_WINDOWS_DUMP</td>
<td>
DEBUG_DUMP_DEFAULT

</td>
</tr>
</table>
 

For a description of kernel-mode dump files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/varieties-of-kernel-mode-dump-files">Varieties of Kernel-Mode Dump Files</a>.  For a description of user-mode dump files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/user-mode-dump-files">Varieties of User-Mode Dump Files</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-dump--create-dump-file-">.dump (Create Dump File)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-writedumpfile2">WriteDumpFile2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-writedumpfilewide">WriteDumpFileWide</a>
 

 

