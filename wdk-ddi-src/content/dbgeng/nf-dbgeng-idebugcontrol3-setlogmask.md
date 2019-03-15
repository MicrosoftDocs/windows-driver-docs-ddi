---
UID: NF:dbgeng.IDebugControl3.SetLogMask
title: IDebugControl3::SetLogMask (dbgeng.h)
description: The SetLogMask method sets the output mask for the currently open log file.
old-location: debugger\setlogmask.htm
tech.root: debugger
ms.assetid: 86c4e5ec-e893-4b1e-b397-6c51351df46c
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetLogMask method, IDebugControl2 interface [Windows Debugging],SetLogMask method, IDebugControl2::SetLogMask, IDebugControl3 interface [Windows Debugging],SetLogMask method, IDebugControl3.SetLogMask, IDebugControl3::SetLogMask, IDebugControl::SetLogMask, IDebugControl_b1c44a2b-d2fd-407b-8994-00f5e53af10d.xml, SetLogMask, SetLogMask method [Windows Debugging], SetLogMask method [Windows Debugging],IDebugControl interface, SetLogMask method [Windows Debugging],IDebugControl2 interface, SetLogMask method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetLogMask, dbgeng/IDebugControl3::SetLogMask, dbgeng/IDebugControl::SetLogMask, debugger.setlogmask
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl.SetLogMask
- IDebugControl2.SetLogMask
- IDebugControl3.SetLogMask
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::SetLogMask


## -description


The <b>SetLogMask</b> method sets the output mask for the currently open log file.


## -parameters




### -param Mask [in]

Specifies the new output mask for the log file.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for details about this value.


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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547066">GetLogMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>
 

 

