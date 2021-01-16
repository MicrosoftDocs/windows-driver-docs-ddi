---
UID: NF:dbgeng.IDebugClient5.AddDumpInformationFileWide
title: IDebugClient5::AddDumpInformationFileWide (dbgeng.h)
description: The AddDumpInformationFileWide method registers additional files containing supporting information that will be used when opening a dump file. The ASCII version of this method is AddDumpInformationFile.
old-location: debugger\adddumpinformationfilewide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::AddDumpInformationFileWide"]
ms.keywords: AddDumpInformationFileWide, AddDumpInformationFileWide method [Windows Debugging], AddDumpInformationFileWide method [Windows Debugging],IDebugClient4 interface, AddDumpInformationFileWide method [Windows Debugging],IDebugClient5 interface, IDebugClient4 interface [Windows Debugging],AddDumpInformationFileWide method, IDebugClient4::AddDumpInformationFileWide, IDebugClient5 interface [Windows Debugging],AddDumpInformationFileWide method, IDebugClient5.AddDumpInformationFileWide, IDebugClient5::AddDumpInformationFileWide, IDebugClient_515044fe-647d-447a-bb74-5738d4d08d6d.xml, dbgeng/IDebugClient4::AddDumpInformationFileWide, dbgeng/IDebugClient5::AddDumpInformationFileWide, debugger.adddumpinformationfilewide
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugClient5::AddDumpInformationFileWide
 - dbgeng/IDebugClient5::AddDumpInformationFileWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5::AddDumpInformationFileWide
---

# IDebugClient5::AddDumpInformationFileWide


## -description

The <b>AddDumpInformationFileWide</b> method registers additional files containing supporting information that will be used when opening a <a href="/windows-hardware/drivers/debugger/d">dump file</a>.  The ASCII version of this method is <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfile">AddDumpInformationFile</a>.

## -parameters

### -param FileName 

[in, optional]
Specifies the name of the file containing the supporting information.  If <i>FileHandle</i> is not zero, <i>FileName</i> is used only for informational purposes.

### -param FileHandle 

[in]
Specifies the handle of the file containing the supporting information.  If <i>FileHandle</i> is zero, the file named in <i>FileName</i> is used.

### -param Type 

[in]
Specifies the type of the file in <i>FileName</i> or <i>FileHandle</i>.  Currently, only files containing paging file information are supported, and <i>Type</i> must be set to DEBUG_DUMP_FILE_PAGE_FILE_DUMP.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

If supporting information is to be used when opening a dump file, this method or <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfile">AddDumpInformationFile</a> must be called before <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-opendumpfile">OpenDumpFile</a> is called. If a session has already started, this method cannot be used.

For more information about crash dump files, see <a href="/windows-hardware/drivers/debugger/dump-file-targets">Dump-File Targets</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfile">AddDumpInformationFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getdumpfile">GetDumpFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getnumberdumpfiles">GetNumberDumpFiles</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-opendumpfile">OpenDumpFile</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-opendumpfilewide">OpenDumpFileWide</a>

