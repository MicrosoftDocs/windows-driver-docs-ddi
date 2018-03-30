---
UID: NF:dbgeng.IDebugClient4.GetDumpFileWide
title: IDebugClient4::GetDumpFileWide method
author: windows-driver-content
description: The GetDumpFileWide method describes the files containing supporting information that were used when opening the current dump target.
old-location: debugger\getdumpfilewide.htm
old-project: debugger
ms.assetid: 42acd24e-5952-46b3-bb0b-1eb43125fccd
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetDumpFileWide method [Windows Debugging], GetDumpFileWide method [Windows Debugging], IDebugClient4 interface, GetDumpFileWide method [Windows Debugging], IDebugClient5 interface, GetDumpFileWide,IDebugClient4.GetDumpFileWide, IDebugClient4, IDebugClient4 interface [Windows Debugging], GetDumpFileWide method, IDebugClient4::GetDumpFileWide, IDebugClient5 interface [Windows Debugging], GetDumpFileWide method, IDebugClient5::GetDumpFileWide, dbgeng/IDebugClient4::GetDumpFileWide, dbgeng/IDebugClient5::GetDumpFileWide, debugger.getdumpfilewide
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
-	IDebugClient4.GetDumpFileWide
-	IDebugClient5.GetDumpFileWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient4::GetDumpFileWide method


## -description


The <b>GetDumpFileWide</b> method describes the files containing supporting information that were used when opening the current dump target.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537874">AddDumpInformationFileWide</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547887">GetNumberDumpFiles</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

