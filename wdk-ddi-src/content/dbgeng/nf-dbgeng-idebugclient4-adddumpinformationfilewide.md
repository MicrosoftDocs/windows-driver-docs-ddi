---
UID: NF:dbgeng.IDebugClient4.AddDumpInformationFileWide
title: IDebugClient4::AddDumpInformationFileWide method
author: windows-driver-content
description: The AddDumpInformationFileWide method registers additional files containing supporting information that will be used when opening a dump file. The ASCII version of this method is AddDumpInformationFile.
old-location: debugger\adddumpinformationfilewide.htm
old-project: debugger
ms.assetid: 0b6318de-4f8e-43e8-ad86-c1fc52097662
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 4, :, A, AddDumpInformationFileWide method [Windows Debugging], AddDumpInformationFileWide method [Windows Debugging], IDebugClient4 interface, AddDumpInformationFileWide method [Windows Debugging], IDebugClient5 interface, AddDumpInformationFileWide,IDebugClient4.AddDumpInformationFileWide, C, D, F, I, IDebugClient4, IDebugClient4 interface [Windows Debugging], AddDumpInformationFileWide method, IDebugClient4::AddDumpInformationFileWide, IDebugClient5 interface [Windows Debugging], AddDumpInformationFileWide method, IDebugClient5::AddDumpInformationFileWide, IDebugClient_515044fe-647d-447a-bb74-5738d4d08d6d.xml, W, a, b, d, dbgeng/IDebugClient4::AddDumpInformationFileWide, dbgeng/IDebugClient5::AddDumpInformationFileWide, debugger.adddumpinformationfilewide, e, f, g, i, l, m, n, o, p, r, t, u"
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
-	IDebugClient4.AddDumpInformationFileWide
-	IDebugClient5.AddDumpInformationFileWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient4::AddDumpInformationFileWide method


## -description


The <b>AddDumpInformationFileWide</b> method registers additional files containing supporting information that will be used when opening a <a href="https://msdn.microsoft.com/e4d53375-c82e-493b-9ccb-444c211fbc79">dump file</a>.  The ASCII version of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>.


## -syntax


````
HRESULT AddDumpInformationFileWide(
  [in, optional] PCWSTR  FileName,
  [in]           ULONG64 FileHandle,
  [in]           ULONG   Type
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547887">GetNumberDumpFiles</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546586">GetDumpFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552324">OpenDumpFileWide</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient4::AddDumpInformationFileWide method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

