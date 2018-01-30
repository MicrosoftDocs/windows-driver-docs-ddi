---
UID: NF:dbgeng.IDebugClient5.WriteDumpFileWide
title: IDebugClient5::WriteDumpFileWide method
author: windows-driver-content
description: The WriteDumpFileWide method creates a user-mode or kernel-modecrash dump file.
old-location: debugger\writedumpfilewide.htm
old-project: debugger
ms.assetid: b089499f-4f15-400e-bf88-53d0507200b9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: WriteDumpFileWide method [Windows Debugging], WriteDumpFileWide method [Windows Debugging], IDebugClient4 interface, IDebugClient5::WriteDumpFileWide, IDebugClient4 interface [Windows Debugging], WriteDumpFileWide method, IDebugClient4::WriteDumpFileWide, IDebugClient_cbae8215-df5f-484c-9b0a-8a5dc1564a00.xml, WriteDumpFileWide, IDebugClient5 interface [Windows Debugging], WriteDumpFileWide method, IDebugClient5, debugger.writedumpfilewide, dbgeng/IDebugClient5::WriteDumpFileWide, WriteDumpFileWide method [Windows Debugging], IDebugClient5 interface, dbgeng/IDebugClient4::WriteDumpFileWide
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
-	IDebugClient4.WriteDumpFileWide
-	IDebugClient5.WriteDumpFileWide
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugClient5::WriteDumpFileWide method


## -description


The <b>WriteDumpFileWide</b> method creates a user-mode or kernel-modecrash dump file.


## -syntax


````
HRESULT WriteDumpFileWide(
  [in, optional] PCWSTR  FileName,
  [in]           ULONG64 FileHandle,
  [in]           ULONG   Qualifier,
  [in]           ULONG   FormatFlags,
  [in, optional] PCWSTR  Comment
);
````


## -parameters




### -param FileName [in, optional]

Specifies the name of the dump file to create.  <i>FileName</i> must include the file name extension. <i>FileName</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.  If <i>FileHandle</i> is not <b>NULL</b>, <i>FileName</i> is ignored (except when writing status messages to the debugger console).


### -param FileHandle [in]

Specifies the file handle of the file to write the crash dump to.  If <i>FileHandle</i> is <b>NULL</b>, the file specified in <i>FileName</i> is used instead.


### -param Qualifier [in]

Specifies the type of dump to create.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541472">DEBUG_DUMP_XXX</a>.


### -param FormatFlags [in]

Specifies flags that determine the format of the dump file and--for user-mode minidumps--what information to include in the file.  For details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541497">DEBUG_FORMAT_XXX</a>.


### -param Comment [in, optional]

Specifies a comment string to be included in the crash dump file.  This string is displayed in the debugger console when the dump file is loaded.


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


For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562428">.dump (Create Dump File)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561382">WriteDumpFile2</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient4::WriteDumpFileWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

