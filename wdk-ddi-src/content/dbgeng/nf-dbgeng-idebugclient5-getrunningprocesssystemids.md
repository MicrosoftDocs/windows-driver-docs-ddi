---
UID: NF:dbgeng.IDebugClient5.GetRunningProcessSystemIds
title: IDebugClient5::GetRunningProcessSystemIds (dbgeng.h)
description: The GetRunningProcessSystemIds method returns the process IDs for each running process.
old-location: debugger\getrunningprocesssystemids.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetRunningProcessSystemIds"]
ms.keywords: GetRunningProcessSystemIds, GetRunningProcessSystemIds method [Windows Debugging], GetRunningProcessSystemIds method [Windows Debugging],IDebugClient interface, GetRunningProcessSystemIds method [Windows Debugging],IDebugClient2 interface, GetRunningProcessSystemIds method [Windows Debugging],IDebugClient3 interface, GetRunningProcessSystemIds method [Windows Debugging],IDebugClient4 interface, GetRunningProcessSystemIds method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetRunningProcessSystemIds method, IDebugClient2 interface [Windows Debugging],GetRunningProcessSystemIds method, IDebugClient2::GetRunningProcessSystemIds, IDebugClient3 interface [Windows Debugging],GetRunningProcessSystemIds method, IDebugClient3::GetRunningProcessSystemIds, IDebugClient4 interface [Windows Debugging],GetRunningProcessSystemIds method, IDebugClient4::GetRunningProcessSystemIds, IDebugClient5 interface [Windows Debugging],GetRunningProcessSystemIds method, IDebugClient5.GetRunningProcessSystemIds, IDebugClient5::GetRunningProcessSystemIds, IDebugClient::GetRunningProcessSystemIds, IDebugClient_f1eed41f-b746-4eb6-b6db-8eef7ac89d6a.xml, dbgeng/IDebugClient2::GetRunningProcessSystemIds, dbgeng/IDebugClient3::GetRunningProcessSystemIds, dbgeng/IDebugClient4::GetRunningProcessSystemIds, dbgeng/IDebugClient5::GetRunningProcessSystemIds, dbgeng/IDebugClient::GetRunningProcessSystemIds, debugger.getrunningprocesssystemids
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
 - IDebugClient5::GetRunningProcessSystemIds
 - dbgeng/IDebugClient5::GetRunningProcessSystemIds
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient.GetRunningProcessSystemIds
 - IDebugClient2.GetRunningProcessSystemIds
 - IDebugClient3.GetRunningProcessSystemIds
 - IDebugClient4.GetRunningProcessSystemIds
 - IDebugClient5.GetRunningProcessSystemIds
---

# IDebugClient5::GetRunningProcessSystemIds


## -description

The <b>GetRunningProcessSystemIds</b> method returns the process IDs for each running process.

## -parameters

### -param Server 

[in]
Specifies the process server to query for process IDs.  If <i>Server</i> is zero, the engine will return the process IDs of the processes running on the local computer.

### -param Ids 

[out, optional]
Receives the process IDs.  The size of this array is <i>Count</i>.  If <i>Ids</i> is <b>NULL</b>, this information is not returned.

### -param Count 

[in]
Specifies the number of process IDs the array <i>Ids</i> can hold.

### -param ActualCount 

[out, optional]
Receives the actual number of process IDs returned in <i>Ids</i>.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

This method is available only for live user-mode debugging.

For more information about creating and attaching to live user-mode targets, see <a href="/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocessdescription">GetRunningProcessDescription</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocesssystemidbyexecutablename">GetRunningProcessSystemIdByExecutableName</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
