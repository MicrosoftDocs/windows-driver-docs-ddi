---
UID: NF:dbgeng.IDebugClient5.AddDumpInformationFileWide
title: IDebugClient5::AddDumpInformationFileWide
author: windows-driver-content
description: The AddDumpInformationFileWide method registers additional files containing supporting information that will be used when opening a dump file. The ASCII version of this method is AddDumpInformationFile.
old-location: debugger\adddumpinformationfilewide.htm
old-project: debugger
ms.assetid: 0b6318de-4f8e-43e8-ad86-c1fc52097662
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: AddDumpInformationFileWide, AddDumpInformationFileWide method [Windows Debugging], AddDumpInformationFileWide method [Windows Debugging],IDebugClient4 interface, AddDumpInformationFileWide method [Windows Debugging],IDebugClient5 interface, IDebugClient4 interface [Windows Debugging],AddDumpInformationFileWide method, IDebugClient4::AddDumpInformationFileWide, IDebugClient5 interface [Windows Debugging],AddDumpInformationFileWide method, IDebugClient5.AddDumpInformationFileWide, IDebugClient5::AddDumpInformationFileWide, IDebugClient_515044fe-647d-447a-bb74-5738d4d08d6d.xml, dbgeng/IDebugClient4::AddDumpInformationFileWide, dbgeng/IDebugClient5::AddDumpInformationFileWide, debugger.adddumpinformationfilewide
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
-	IDebugClient4.AddDumpInformationFileWide
-	IDebugClient5.AddDumpInformationFileWide
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::AddDumpInformationFileWide


## -description


The <b>AddDumpInformationFileWide</b> method registers additional files containing supporting information that will be used when opening a <a href="https://msdn.microsoft.com/e4d53375-c82e-493b-9ccb-444c211fbc79">dump file</a>.  The ASCII version of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>.


## -parameters




### -param FileName [in, optional]

Specifies the name of the file containing the supporting information.  If <i>FileHandle</i> is not zero, <i>FileName</i> is used only for informational purposes.


### -param FileHandle [in]

Specifies the handle of the file containing the supporting information.  If <i>FileHandle</i> is zero, the file named in <i>FileName</i> is used.


### -param Type [in]

Specifies the type of the file in <i>FileName</i> or <i>FileHandle</i>.  Currently, only files containing paging file information are supported, and <i>Type</i> must be set to DEBUG_DUMP_FILE_PAGE_FILE_DUMP.


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



If supporting information is to be used when opening a dump file, this method or <a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a> must be called before <a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a> is called. If a session has already started, this method cannot be used.

For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546586">GetDumpFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547887">GetNumberDumpFiles</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552324">OpenDumpFileWide</a>
 

 

