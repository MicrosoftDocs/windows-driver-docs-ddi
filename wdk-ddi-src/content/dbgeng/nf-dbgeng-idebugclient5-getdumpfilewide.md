---
UID: NF:dbgeng.IDebugClient5.GetDumpFileWide
title: IDebugClient5::GetDumpFileWide method
author: windows-driver-content
description: The GetDumpFileWide method describes the files containing supporting information that were used when opening the current dump target.
old-location: debugger\getdumpfilewide.htm
old-project: debugger
ms.assetid: 42acd24e-5952-46b3-bb0b-1eb43125fccd
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetDumpFileWide method [Windows Debugging], IDebugClient5 interface, IDebugClient4 interface [Windows Debugging], GetDumpFileWide method, debugger.getdumpfilewide, IDebugClient5::GetDumpFileWide, dbgeng/IDebugClient5::GetDumpFileWide, IDebugClient5, GetDumpFileWide, GetDumpFileWide method [Windows Debugging], IDebugClient4 interface, dbgeng/IDebugClient4::GetDumpFileWide, GetDumpFileWide method [Windows Debugging], IDebugClient5 interface [Windows Debugging], GetDumpFileWide method, IDebugClient4::GetDumpFileWide
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
-	IDebugClient4.GetDumpFileWide
-	IDebugClient5.GetDumpFileWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugClient5::GetDumpFileWide method


## -description


The <b>GetDumpFileWide</b> method describes the files containing supporting information that were used when opening the current dump target.


## -syntax


````
HRESULT GetDumpFileWide(
  [in]            ULONG    Index,
  [out, optional] PWSTR    Buffer,
  [in]            ULONG    BufferSize,
  [out, optional] PULONG   NameSize,
  [out, optional] PULONG64 Handle,
  [out]           PULONG   Type
);
````


## -parameters




### -param Index [in]

Specifies which file to describe.  <i>Index</i> can take values between zero and the number of files minus one; the number of files can be found by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff547887">GetNumberDumpFiles</a>.


### -param Buffer [out, optional]

Receives the file name.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size in characters of the buffer <i>Buffer</i>.


### -param NameSize [out, optional]

Receives the size of the file name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


### -param Handle [out, optional]

Receives the file handle of the file.  If <i>Handle</i> is <b>NULL</b>, this information is not returned.


### -param Type [out]

Receives the type of the file.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547887">GetNumberDumpFiles</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537874">AddDumpInformationFileWide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient4::GetDumpFileWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

