---
UID: NF:dbgeng.IDebugControl4.GetLogFileWide
title: IDebugControl4::GetLogFileWide
author: windows-driver-content
description: The GetLogFileWide method returns the name of the currently open log file.
old-location: debugger\getlogfilewide.htm
old-project: debugger
ms.assetid: 2dd20552-747c-4eb8-aacd-7ee241d490d1
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetLogFileWide, GetLogFileWide method [Windows Debugging], GetLogFileWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetLogFileWide method, IDebugControl4.GetLogFileWide, IDebugControl4::GetLogFileWide, dbgeng/IDebugControl4::GetLogFileWide, debugger.getlogfilewide
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
-	IDebugControl4.GetLogFileWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetLogFileWide


## -description


The <b>GetLogFileWide</b>  method returns the name of the currently open log file.


## -parameters




### -param Buffer [out, optional]

Receives the name of the currently open log file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param FileSize [out, optional]

Receives the size, in characters, of the name of the log file.  If <i>FileSize</i> is <b>NULL</b>, this information is not returned.


### -param Append [out]

Receives <b>TRUE</b> if log messages are appended to the log file, or <b>FALSE</b> if the contents of the log file were discarded when the file was opened.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the name of the log file was too long to fit in the <i>Buffer</i> buffer so the name was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
There is no currently open log file.

</td>
</tr>
</table>
 




## -remarks



<b>GetLogFile</b> and <b>GetLogFileWide</b> behave the same way as <a href="https://msdn.microsoft.com/library/windows/hardware/ff547025">GetLogFile2</a> and <b>GetLogFile2Wide</b> with <i>Append</i> receiving only the information about the DEBUG_LOG_APPEND flag.

For more information about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539148">CloseLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547025">GetLogFile2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547066">GetLogMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553154">OpenLogFile</a>
 

 

