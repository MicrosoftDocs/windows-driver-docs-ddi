---
UID: NF:dbgeng.IDebugSystemObjects.GetThreadIdsByIndex
title: IDebugSystemObjects::GetThreadIdsByIndex (dbgeng.h)
description: The GetThreadIdsByIndex method returns the engine and system thread IDs for the specified threads in the current process.
old-location: debugger\getthreadidsbyindex.htm
tech.root: debugger
ms.assetid: d671ea6e-19cb-4a90-b345-ea544c9561cd
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects::GetThreadIdsByIndex"]
ms.keywords: GetThreadIdsByIndex, GetThreadIdsByIndex method [Windows Debugging], GetThreadIdsByIndex method [Windows Debugging],IDebugSystemObjects interface, GetThreadIdsByIndex method [Windows Debugging],IDebugSystemObjects2 interface, GetThreadIdsByIndex method [Windows Debugging],IDebugSystemObjects3 interface, GetThreadIdsByIndex method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetThreadIdsByIndex method, IDebugSystemObjects.GetThreadIdsByIndex, IDebugSystemObjects2 interface [Windows Debugging],GetThreadIdsByIndex method, IDebugSystemObjects2::GetThreadIdsByIndex, IDebugSystemObjects3 interface [Windows Debugging],GetThreadIdsByIndex method, IDebugSystemObjects3::GetThreadIdsByIndex, IDebugSystemObjects4 interface [Windows Debugging],GetThreadIdsByIndex method, IDebugSystemObjects4::GetThreadIdsByIndex, IDebugSystemObjects::GetThreadIdsByIndex, IDebugSystemObjects_fa12ac17-9a66-45c0-9c91-11236a4a3eab.xml, dbgeng/IDebugSystemObjects2::GetThreadIdsByIndex, dbgeng/IDebugSystemObjects3::GetThreadIdsByIndex, dbgeng/IDebugSystemObjects4::GetThreadIdsByIndex, dbgeng/IDebugSystemObjects::GetThreadIdsByIndex, debugger.getthreadidsbyindex
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugSystemObjects::GetThreadIdsByIndex
 - dbgeng/IDebugSystemObjects::GetThreadIdsByIndex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetThreadIdsByIndex
 - IDebugSystemObjects2.GetThreadIdsByIndex
 - IDebugSystemObjects3.GetThreadIdsByIndex
 - IDebugSystemObjects4.GetThreadIdsByIndex
---

# IDebugSystemObjects::GetThreadIdsByIndex


## -description

The <b>GetThreadIdsByIndex</b> method returns the engine and system thread IDs for the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-threads-and-processes">threads</a> in the current process.

## -parameters

### -param Start 

[in]
Specifies the index of the first thread whose IDs are requested.

### -param Count 

[in]
Specifies the number of threads whose IDs are requested.

### -param Ids 

[out, optional]
Receives the engine thread IDs.  If <i>Ids</i> is <b>NULL</b>, this information is not returned; otherwise, <i>Ids</i> is treated as an array of <i>Count</i> ULONG valuess.

### -param SysIds 

[out, optional]
Receives the system thread IDs.  If <i>SysIds</i> is <b>NULL</b>, this information is not returned; otherwise, <i>SysIds</i> is treated as an array of <i>Count</i> ULONG values.

## -returns

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

The index of the first thread is zero.  The index of the last thread is the number of threads returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getnumberthreads">GetNumberThreads</a> minus one.

For more information about threads, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.

