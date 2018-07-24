---
UID: NF:dbgeng.IDebugControl4.OpenLogFileWide
title: IDebugControl4::OpenLogFileWide
author: windows-driver-content
description: The OpenLogFileWide method opens a log file that will receive output from the client objects.
old-location: debugger\openlogfilewide.htm
tech.root: debugger
ms.assetid: 1e69812e-077e-476f-a253-f0c39575eb32
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IDebugControl4 interface [Windows Debugging],OpenLogFileWide method, IDebugControl4.OpenLogFileWide, IDebugControl4::OpenLogFileWide, OpenLogFileWide, OpenLogFileWide method [Windows Debugging], OpenLogFileWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::OpenLogFileWide, debugger.openlogfilewide
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
-	IDebugControl4.OpenLogFileWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::OpenLogFileWide


## -description


The <b>OpenLogFileWide</b>  method opens a log file that will receive output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">client objects</a>.


## -parameters




### -param File [in]

Specifies the name of the log file.  <i>File</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger  was started.  If the file does not exist, it will be created.


### -param Append [in]

Specifies whether or not to append log messages to an existing log file.  If <b>TRUE</b>, log messages will be appended to the file; if <b>FALSE</b>, the contents of any existing file matching <i>File</i> are discarded.


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



<b>OpenLogFile</b> and <b>OpenLogFileWide</b> behave the same way as <a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a> and <b>OpenLogFile2Wide</b> with <i>Flags</i> set to DEBUG_LOG_APPEND if <i>Append</i> is <b>TRUE</b> and DEBUG_LOG_DEFAULT otherwise.

Only one log file can be open at a time.  If there is already a log file open, it will be closed.

For more information about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563986">.logappend (Append Log File)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564018">.logopen (Open Log File)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539148">CloseLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547016">GetLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547066">GetLogMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556734">SetLogMask</a>
 

 

