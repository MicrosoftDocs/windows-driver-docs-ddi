---
UID: NF:dbgeng.IDebugClient.GetRunningProcessSystemIdByExecutableName
title: IDebugClient::GetRunningProcessSystemIdByExecutableName (dbgeng.h)
description: The GetRunningProcessSystemIdByExecutableName method searches for a process with a given executable file name and return its process ID.
old-location: debugger\getrunningprocesssystemidbyexecutablename.htm
tech.root: debugger
ms.assetid: 67e231b4-c693-4824-b895-b7f3085e6f4e
ms.date: 05/03/2018
keywords: ["IDebugClient::GetRunningProcessSystemIdByExecutableName"]
ms.keywords: GetRunningProcessSystemIdByExecutableName, GetRunningProcessSystemIdByExecutableName method [Windows Debugging], GetRunningProcessSystemIdByExecutableName method [Windows Debugging],IDebugClient interface, GetRunningProcessSystemIdByExecutableName method [Windows Debugging],IDebugClient2 interface, GetRunningProcessSystemIdByExecutableName method [Windows Debugging],IDebugClient3 interface, GetRunningProcessSystemIdByExecutableName method [Windows Debugging],IDebugClient4 interface, GetRunningProcessSystemIdByExecutableName method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetRunningProcessSystemIdByExecutableName method, IDebugClient.GetRunningProcessSystemIdByExecutableName, IDebugClient2 interface [Windows Debugging],GetRunningProcessSystemIdByExecutableName method, IDebugClient2::GetRunningProcessSystemIdByExecutableName, IDebugClient3 interface [Windows Debugging],GetRunningProcessSystemIdByExecutableName method, IDebugClient3::GetRunningProcessSystemIdByExecutableName, IDebugClient4 interface [Windows Debugging],GetRunningProcessSystemIdByExecutableName method, IDebugClient4::GetRunningProcessSystemIdByExecutableName, IDebugClient5 interface [Windows Debugging],GetRunningProcessSystemIdByExecutableName method, IDebugClient5::GetRunningProcessSystemIdByExecutableName, IDebugClient::GetRunningProcessSystemIdByExecutableName, IDebugClient_c7e63b9d-45fe-4125-9fbf-984de939b089.xml, dbgeng/IDebugClient2::GetRunningProcessSystemIdByExecutableName, dbgeng/IDebugClient3::GetRunningProcessSystemIdByExecutableName, dbgeng/IDebugClient4::GetRunningProcessSystemIdByExecutableName, dbgeng/IDebugClient5::GetRunningProcessSystemIdByExecutableName, dbgeng/IDebugClient::GetRunningProcessSystemIdByExecutableName, debugger.getrunningprocesssystemidbyexecutablename
f1_keywords:
 - "dbgeng/IDebugClient.GetRunningProcessSystemIdByExecutableName"
 - "IDebugClient.GetRunningProcessSystemIdByExecutableName"
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
- IDebugClient.GetRunningProcessSystemIdByExecutableName
- IDebugClient2.GetRunningProcessSystemIdByExecutableName
- IDebugClient3.GetRunningProcessSystemIdByExecutableName
- IDebugClient4.GetRunningProcessSystemIdByExecutableName
- IDebugClient5.GetRunningProcessSystemIdByExecutableName
targetos: Windows
req.typenames: 
---

# IDebugClient::GetRunningProcessSystemIdByExecutableName


## -description


The <b>GetRunningProcessSystemIdByExecutableName</b>  method searches for a process with a given executable file name and return its process ID.


## -parameters




### -param Server 
[in]
Specifies the process server to search for the executable name.  If <i>Server</i> is zero, the engine will search for the executable name among the processes running on the local computer.


### -param ExeName 
[in]
Specifies the executable file name for which to search.


### -param Flags 
[in]
Specifies a bit-set that controls how the executable name is matched.  The following flags may be present:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_GET_PROC_FULL_MATCH

</td>
<td>
<i>ExeName</i> specifies the full path name of the executable file name.

If this flag is not set, this method will not use path names when searching for the process.

</td>
</tr>
<tr>
<td>
DEBUG_GET_PROC_ONLY_MATCH

</td>
<td>
Require that only one process match the executable file name <i>ExeName</i>.

</td>
</tr>
</table>
 


### -param Id 
[out]
Receives the process ID of the first process to match <i>ExeName</i>.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
More than one process matched the executable file name in <i>ExeName</i>, and DEBUG_GET_PROC_ONLY_MATCH was set in <i>Flags</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No process matched the executable file name in <i>ExeName</i>.

</td>
</tr>
</table>
 




## -remarks



This method is available only for live user-mode debugging.

For more information about creating and attaching to live user-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocessdescription">GetRunningProcessDescription</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocesssystemids">GetRunningProcessSystemIds</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

