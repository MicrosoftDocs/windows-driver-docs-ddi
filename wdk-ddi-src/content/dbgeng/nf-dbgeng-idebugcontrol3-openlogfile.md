---
UID: NF:dbgeng.IDebugControl3.OpenLogFile
title: IDebugControl3::OpenLogFile
author: windows-driver-content
description: The OpenLogFile method opens a log file that will receive output from the client objects.
old-location: debugger\openlogfile.htm
tech.root: debugger
ms.assetid: aba8839e-4c44-4c10-8b6f-9f5832c12166
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],OpenLogFile method, IDebugControl2 interface [Windows Debugging],OpenLogFile method, IDebugControl2::OpenLogFile, IDebugControl3 interface [Windows Debugging],OpenLogFile method, IDebugControl3.OpenLogFile, IDebugControl3::OpenLogFile, IDebugControl::OpenLogFile, IDebugControl_984f684e-c1c0-4819-b8ac-02718581c6ad.xml, OpenLogFile, OpenLogFile method [Windows Debugging], OpenLogFile method [Windows Debugging],IDebugControl interface, OpenLogFile method [Windows Debugging],IDebugControl2 interface, OpenLogFile method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::OpenLogFile, dbgeng/IDebugControl3::OpenLogFile, dbgeng/IDebugControl::OpenLogFile, debugger.openlogfile
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
-	IDebugControl.OpenLogFile
-	IDebugControl2.OpenLogFile
-	IDebugControl3.OpenLogFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::OpenLogFile


## -description


The <b>OpenLogFile</b>  method opens a log file that will receive output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">client objects</a>.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556734">SetLogMask</a>
 

 

