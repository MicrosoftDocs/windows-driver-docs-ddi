---
UID: NF:dbgeng.IDebugControl3.CloseLogFile
title: IDebugControl3::CloseLogFile
author: windows-driver-content
description: The CloseLogFile method closes the currently-open log file.
old-location: debugger\closelogfile.htm
old-project: debugger
ms.assetid: 86ae188b-379c-474e-9f21-60286af19656
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: CloseLogFile, CloseLogFile method [Windows Debugging], CloseLogFile method [Windows Debugging],IDebugControl interface, CloseLogFile method [Windows Debugging],IDebugControl2 interface, CloseLogFile method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],CloseLogFile method, IDebugControl2 interface [Windows Debugging],CloseLogFile method, IDebugControl2::CloseLogFile, IDebugControl3 interface [Windows Debugging],CloseLogFile method, IDebugControl3.CloseLogFile, IDebugControl3::CloseLogFile, IDebugControl::CloseLogFile, IDebugControl_988fe3ac-a51d-4757-995d-40fe9d66aa02.xml, dbgeng/IDebugControl2::CloseLogFile, dbgeng/IDebugControl3::CloseLogFile, dbgeng/IDebugControl::CloseLogFile, debugger.closelogfile
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
-	Dbgeng.h
api_name:
-	IDebugControl.CloseLogFile
-	IDebugControl2.CloseLogFile
-	IDebugControl3.CloseLogFile
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::CloseLogFile


## -description


The <b>CloseLogFile</b> method closes the currently-open log file.


## -parameters






## -returns



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
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



If no log file is open, this method has no effect.

For more about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.




## -see-also




<a href="https://msdn.microsoft.com/730cfab3-5529-4054-ba62-8a780572603d">.logclose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547016">GetLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547025">GetLogFile2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553154">OpenLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>
 

 

