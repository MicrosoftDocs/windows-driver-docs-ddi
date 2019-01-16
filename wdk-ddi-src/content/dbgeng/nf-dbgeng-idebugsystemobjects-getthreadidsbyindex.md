---
UID: NF:dbgeng.IDebugSystemObjects.GetThreadIdsByIndex
title: IDebugSystemObjects::GetThreadIdsByIndex
description: The GetThreadIdsByIndex method returns the engine and system thread IDs for the specified threads in the current process.
old-location: debugger\getthreadidsbyindex.htm
tech.root: debugger
ms.assetid: d671ea6e-19cb-4a90-b345-ea544c9561cd
ms.date: 05/03/2018
ms.keywords: GetThreadIdsByIndex, GetThreadIdsByIndex method [Windows Debugging], GetThreadIdsByIndex method [Windows Debugging],IDebugSystemObjects interface, GetThreadIdsByIndex method [Windows Debugging],IDebugSystemObjects2 interface, GetThreadIdsByIndex method [Windows Debugging],IDebugSystemObjects3 interface, GetThreadIdsByIndex method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetThreadIdsByIndex method, IDebugSystemObjects.GetThreadIdsByIndex, IDebugSystemObjects2 interface [Windows Debugging],GetThreadIdsByIndex method, IDebugSystemObjects2::GetThreadIdsByIndex, IDebugSystemObjects3 interface [Windows Debugging],GetThreadIdsByIndex method, IDebugSystemObjects3::GetThreadIdsByIndex, IDebugSystemObjects4 interface [Windows Debugging],GetThreadIdsByIndex method, IDebugSystemObjects4::GetThreadIdsByIndex, IDebugSystemObjects::GetThreadIdsByIndex, IDebugSystemObjects_fa12ac17-9a66-45c0-9c91-11236a4a3eab.xml, dbgeng/IDebugSystemObjects2::GetThreadIdsByIndex, dbgeng/IDebugSystemObjects3::GetThreadIdsByIndex, dbgeng/IDebugSystemObjects4::GetThreadIdsByIndex, dbgeng/IDebugSystemObjects::GetThreadIdsByIndex, debugger.getthreadidsbyindex
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
-	IDebugSystemObjects.GetThreadIdsByIndex
-	IDebugSystemObjects2.GetThreadIdsByIndex
-	IDebugSystemObjects3.GetThreadIdsByIndex
-	IDebugSystemObjects4.GetThreadIdsByIndex
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects::GetThreadIdsByIndex


## -description


The <b>GetThreadIdsByIndex</b> method returns the engine and system thread IDs for the specified <a href="https://msdn.microsoft.com/6182ca34-ee5e-47e9-82fe-29266397e3a8">threads</a> in the current process.


## -parameters




### -param Start [in]

Specifies the index of the first thread whose IDs are requested.


### -param Count [in]

Specifies the number of threads whose IDs are requested.


### -param Ids [out, optional]

Receives the engine thread IDs.  If <i>Ids</i> is <b>NULL</b>, this information is not returned; otherwise, <i>Ids</i> is treated as an array of <i>Count</i> ULONG valuess.


### -param SysIds [out, optional]

Receives the system thread IDs.  If <i>SysIds</i> is <b>NULL</b>, this information is not returned; otherwise, <i>SysIds</i> is treated as an array of <i>Count</i> ULONG values.


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



The index of the first thread is zero.  The index of the last thread is the number of threads returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547992">GetNumberThreads</a> minus one.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



