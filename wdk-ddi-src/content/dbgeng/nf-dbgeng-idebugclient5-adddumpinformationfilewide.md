---
UID: NF:dbgeng.IDebugClient5.AddDumpInformationFileWide
title: IDebugClient5::AddDumpInformationFileWide method
author: windows-driver-content
description: The AddDumpInformationFileWide method registers additional files containing supporting information that will be used when opening a dump file. The ASCII version of this method is AddDumpInformationFile.
old-location: debugger\adddumpinformationfilewide.htm
old-project: debugger
ms.assetid: 0b6318de-4f8e-43e8-ad86-c1fc52097662
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient5, IDebugClient5::AddDumpInformationFileWide, AddDumpInformationFileWide
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
req.alt-api: IDebugClient4.AddDumpInformationFileWide,IDebugClient5.AddDumpInformationFileWide
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugClient5::AddDumpInformationFileWide method



## -description
The <b>AddDumpInformationFileWide</b> method registers additional files containing supporting information that will be used when opening a <a href="debugger.d#dump_file#dump_file">dump file</a>.  The ASCII version of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>.



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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
If supporting information is to be used when opening a dump file, this method or <a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a> must be called before <a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a> is called. If a session has already started, this method cannot be used.

For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547887">GetNumberDumpFiles</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546586">GetDumpFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552324">OpenDumpFileWide</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient4::AddDumpInformationFileWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

