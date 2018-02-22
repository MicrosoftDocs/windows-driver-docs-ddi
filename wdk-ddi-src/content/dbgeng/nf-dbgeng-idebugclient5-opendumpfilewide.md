---
UID: NF:dbgeng.IDebugClient5.OpenDumpFileWide
title: IDebugClient5::OpenDumpFileWide method
author: windows-driver-content
description: The OpenDumpFileWide method opens a dump file as a debugger target.
old-location: debugger\opendumpfilewide.htm
old-project: Debugger
ms.assetid: 56efc94f-ef1e-41f9-ab99-57f0be34a770
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: OpenDumpFileWide method [Windows Debugging], IDebugClient4, OpenDumpFileWide, dbgeng/IDebugClient5::OpenDumpFileWide, IDebugClient5, IDebugClient4 interface [Windows Debugging], OpenDumpFileWide method, IDebugClient5 interface [Windows Debugging], OpenDumpFileWide method, OpenDumpFileWide method [Windows Debugging], IDebugClient4 interface, dbgeng/IDebugClient4::OpenDumpFileWide, IDebugClient5::OpenDumpFileWide, debugger.opendumpfilewide, IDebugClient4::OpenDumpFileWide, IDebugClient_e3280682-6272-4324-bba5-120a95f27b15.xml, OpenDumpFileWide method [Windows Debugging], IDebugClient5 interface
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
-	IDebugClient4.OpenDumpFileWide
-	IDebugClient5.OpenDumpFileWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::OpenDumpFileWide method


## -description


The <b>OpenDumpFileWide</b> method opens a dump file as a debugger target.


## -syntax


````
HRESULT OpenDumpFileWide(
  [in, optional] PCWSTR  FileName,
  [in]           ULONG64 FileHandle
);
````


## -parameters




### -param FileName [in, optional]

Specifies the name of the dump file to open -- unless <i>FileHandle</i> is not zero, in which case <i>FileName</i> is used only when the engine is queried for the name of the dump file.  <i>FileName</i> must include the file name extension.  <i>FileName</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.  <i>FileName</i> can also be in the form of a file URL, starting with "file://".  If <i>FileName</i> specifies a cabinet (.cab) file, the cabinet file is searched for the first file with extension .kdmp, then .hdmp, then .mdmp, and finally .dmp.


### -param FileHandle [in]

Specifies the file handle of the dump file to open.  If <i>FileHandle</i> is zero, <i>FileName</i> is used to open the dump file.  Otherwise, if <i>FileName</i> is not <b>NULL</b>, the engine returns it when queried for the name of the dump file.  If <i>FileHandle</i> is not zero and <i>FileName</i> is <b>NULL</b>, the engine will return <b>&lt;HandleOnly&gt;</b> for the file name.


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



The ASCII version of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a>.

<div class="alert"><b>Note</b>    The engine doesn't completely attach to the dump file until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> method has been called.  When a dump file is created from a process or kernel, information about the last event is stored in the dump file.  After the dump file is opened, the next time execution is attempted, the engine will generate this event for the event callbacks.  Only then does the dump file become available in the debugging session.</div>
<div> </div>
For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537874">AddDumpInformationFileWide</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564611">.opendump (Open Dump File)</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient4::OpenDumpFileWide method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

