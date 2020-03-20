---
UID: NF:dbgeng.IDebugClient5.OpenDumpFile
title: IDebugClient5::OpenDumpFile (dbgeng.h)
description: The OpenDumpFile method opens a dump file as a debugger target.
old-location: debugger\opendumpfile.htm
tech.root: debugger
ms.assetid: c04b79a0-ef20-4ba5-aba9-9335b095cfef
ms.date: 05/03/2018
keywords: ["IDebugClient5::OpenDumpFile"]
ms.keywords: IDebugClient interface [Windows Debugging],OpenDumpFile method, IDebugClient2 interface [Windows Debugging],OpenDumpFile method, IDebugClient2::OpenDumpFile, IDebugClient3 interface [Windows Debugging],OpenDumpFile method, IDebugClient3::OpenDumpFile, IDebugClient4 interface [Windows Debugging],OpenDumpFile method, IDebugClient4::OpenDumpFile, IDebugClient5 interface [Windows Debugging],OpenDumpFile method, IDebugClient5.OpenDumpFile, IDebugClient5::OpenDumpFile, IDebugClient::OpenDumpFile, IDebugClient_4ab673e2-629c-455a-8d40-27465005375f.xml, OpenDumpFile, OpenDumpFile method [Windows Debugging], OpenDumpFile method [Windows Debugging],IDebugClient interface, OpenDumpFile method [Windows Debugging],IDebugClient2 interface, OpenDumpFile method [Windows Debugging],IDebugClient3 interface, OpenDumpFile method [Windows Debugging],IDebugClient4 interface, OpenDumpFile method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::OpenDumpFile, dbgeng/IDebugClient3::OpenDumpFile, dbgeng/IDebugClient4::OpenDumpFile, dbgeng/IDebugClient5::OpenDumpFile, dbgeng/IDebugClient::OpenDumpFile, debugger.opendumpfile
f1_keywords:
 - "dbgeng/IDebugClient.OpenDumpFile"
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
- IDebugClient.OpenDumpFile
- IDebugClient2.OpenDumpFile
- IDebugClient3.OpenDumpFile
- IDebugClient4.OpenDumpFile
- IDebugClient5.OpenDumpFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::OpenDumpFile


## -description


The <b>OpenDumpFile</b> method opens a dump file as a debugger target.


## -parameters




### -param DumpFile [in]

Specifies the name of the dump file to open.  <i>DumpFile</i> must include the file name extension. <i>DumpFile</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.  <i>DumpFile</i> can have the form of a file URL, starting with "file://".  If <i>DumpFile</i> specifies a cabinet (.cab) file, the cabinet file is searched for the first file with extension .kdmp, then .hdmp, then .mdmp, and finally .dmp.


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



The Unicode version of this method is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-opendumpfilewide">OpenDumpFileWide</a>.

<div class="alert"><b>Note</b>    The engine doesn't completely attach to the dump file until the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a> method has been called.  When a dump file is created from a process or kernel, information about the last event is stored in the dump file.  After the dump file is opened, the next time execution is attempted, the engine will generate this event for the event callbacks.  Only then does the dump file become available in the debugging session.</div>
<div> </div>
For more information about crash dump files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/dump-file-targets">Dump-File Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-opendump--open-dump-file-">.opendump (Open Dump File)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfile">AddDumpInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfilewide">AddDumpInformationFileWide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-opendumpfilewide">OpenDumpFileWide</a>
 

 

