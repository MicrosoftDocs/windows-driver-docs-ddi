---
UID: NF:dbgeng.IDebugClient3.AddDumpInformationFile
title: IDebugClient3::AddDumpInformationFile (dbgeng.h)
description: The AddDumpInformationFile method registers additional files containing supporting information that will be used when opening a dump file. The Unicode version of this method is AddDumpInformationFileWide.
old-location: debugger\adddumpinformationfile.htm
tech.root: debugger
ms.assetid: c111eb7e-7c42-4848-89d3-177f240fff7f
ms.date: 05/03/2018
ms.keywords: AddDumpInformationFile, AddDumpInformationFile method [Windows Debugging], AddDumpInformationFile method [Windows Debugging],IDebugClient2 interface, AddDumpInformationFile method [Windows Debugging],IDebugClient3 interface, AddDumpInformationFile method [Windows Debugging],IDebugClient4 interface, AddDumpInformationFile method [Windows Debugging],IDebugClient5 interface, IDebugClient2 interface [Windows Debugging],AddDumpInformationFile method, IDebugClient2::AddDumpInformationFile, IDebugClient3 interface [Windows Debugging],AddDumpInformationFile method, IDebugClient3.AddDumpInformationFile, IDebugClient3::AddDumpInformationFile, IDebugClient4 interface [Windows Debugging],AddDumpInformationFile method, IDebugClient4::AddDumpInformationFile, IDebugClient5 interface [Windows Debugging],AddDumpInformationFile method, IDebugClient5::AddDumpInformationFile, IDebugClient_11398d02-21c4-4ec5-9e1c-8e7e87808c35.xml, dbgeng/IDebugClient2::AddDumpInformationFile, dbgeng/IDebugClient3::AddDumpInformationFile, dbgeng/IDebugClient4::AddDumpInformationFile, dbgeng/IDebugClient5::AddDumpInformationFile, debugger.adddumpinformationfile
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugClient2.AddDumpInformationFile
- IDebugClient3.AddDumpInformationFile
- IDebugClient4.AddDumpInformationFile
- IDebugClient5.AddDumpInformationFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient3::AddDumpInformationFile


## -description


The <b>AddDumpInformationFile</b> method registers additional files containing supporting information that will be used when opening a dump file.  The Unicode version of this method is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfilewide">AddDumpInformationFileWide</a>.


## -parameters




### -param InfoFile [in]

Specifies the name of the file containing the supporting information.


### -param Type [in]

Specifies the type of the file <i>InfoFile</i>.  Currently, only files containing paging file information are supported, and <i>Type</i> must be set to DEBUG_DUMP_FILE_PAGE_FILE_DUMP.


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



If supporting information is to be used when opening a dump file, this method or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfilewide">AddDumpInformationFileWide</a> must be called before <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-opendumpfile">OpenDumpFile</a> is called. If a session has already started, this method cannot be used.

For more information about crash dump files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/dump-file-targets">Dump File Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfilewide">AddDumpInformationFileWide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-getdumpfile">GetDumpFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-getnumberdumpfiles">GetNumberDumpFiles</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-opendumpfile">OpenDumpFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-opendumpfilewide">OpenDumpFileWide</a>
 

 

