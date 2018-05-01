---
UID: NF:dbgeng.IDebugControl4.GetLogFile2
title: IDebugControl4::GetLogFile2
author: windows-driver-content
description: The GetLogFile2 method returns the name of the currently open log file.
old-location: debugger\getlogfile2.htm
old-project: debugger
ms.assetid: 77ab08ce-96c5-4330-aab2-1bf4ab23cfc4
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetLogFile2, GetLogFile2 method [Windows Debugging], GetLogFile2 method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetLogFile2 method, IDebugControl4.GetLogFile2, IDebugControl4::GetLogFile2, IDebugControl_9822bd84-b8ee-4d36-a66f-e38567d23646.xml, dbgeng/IDebugControl4::GetLogFile2, debugger.getlogfile2
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
-	IDebugControl4.GetLogFile2
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetLogFile2


## -description


The <b>GetLogFile2</b>  method returns the name of the currently open log file.


## -parameters




### -param Buffer [out, optional]

Receives the name of the currently open log file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param FileSize [out, optional]

Receives the size, in characters, of the name of the log file.  If <i>FileSize</i> is <b>NULL</b>, this information is not returned.


### -param Flags [out]

Receives the bit-flags that were used when opening the log file.  See the <i>Flags</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a> for a description of these flags.


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



For more information about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539148">CloseLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547016">GetLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547066">GetLogMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>
 

 

