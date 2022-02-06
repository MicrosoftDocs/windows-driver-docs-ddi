---
UID: NF:dbgeng.IDebugClient.GetRunningProcessDescription
title: IDebugClient::GetRunningProcessDescription (dbgeng.h)
description: The IDebugClient::GetRunningProcessDescription method returns a description of the process that includes several elements.
old-location: debugger\getrunningprocessdescription.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugClient::GetRunningProcessDescription"]
ms.keywords: GetRunningProcessDescription, GetRunningProcessDescription method [Windows Debugging], GetRunningProcessDescription method [Windows Debugging],IDebugClient interface, GetRunningProcessDescription method [Windows Debugging],IDebugClient2 interface, GetRunningProcessDescription method [Windows Debugging],IDebugClient3 interface, GetRunningProcessDescription method [Windows Debugging],IDebugClient4 interface, GetRunningProcessDescription method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetRunningProcessDescription method, IDebugClient.GetRunningProcessDescription, IDebugClient2 interface [Windows Debugging],GetRunningProcessDescription method, IDebugClient2::GetRunningProcessDescription, IDebugClient3 interface [Windows Debugging],GetRunningProcessDescription method, IDebugClient3::GetRunningProcessDescription, IDebugClient4 interface [Windows Debugging],GetRunningProcessDescription method, IDebugClient4::GetRunningProcessDescription, IDebugClient5 interface [Windows Debugging],GetRunningProcessDescription method, IDebugClient5::GetRunningProcessDescription, IDebugClient::GetRunningProcessDescription, IDebugClient_e5736881-635f-4998-809b-d210bf447a36.xml, dbgeng/IDebugClient2::GetRunningProcessDescription, dbgeng/IDebugClient3::GetRunningProcessDescription, dbgeng/IDebugClient4::GetRunningProcessDescription, dbgeng/IDebugClient5::GetRunningProcessDescription, dbgeng/IDebugClient::GetRunningProcessDescription, debugger.getrunningprocessdescription
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
 - IDebugClient::GetRunningProcessDescription
 - dbgeng/IDebugClient::GetRunningProcessDescription
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient::GetRunningProcessDescription
---

# IDebugClient::GetRunningProcessDescription


## -description

The <b>GetRunningProcessDescription</b>  method returns a description of the process that includes the executable image name, the service names, the MTS package names, and the command line.

## -parameters

### -param Server [in]


Specifies the process server to query for the process description.  If <i>Server</i> is zero, the engine will query information about the local process directly.

### -param SystemId [in]


Specifies the process ID of the process whose description is desired.

### -param Flags [in]


Specifies a bit-set containing options that affect the behavior of this method.  <i>Flags</i> can contain the following bit flags:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_PROC_DESC_NO_PATHS

</td>
<td>
Return only file names without path names.

</td>
</tr>
<tr>
<td>
DEBUG_PROC_DESC_NO_SERVICES

</td>
<td>
Do not look up service names.

</td>
</tr>
<tr>
<td>
DEBUG_PROC_DESC_NO_MTS_PACKAGES

</td>
<td>
Do not look up MTS package names.

</td>
</tr>
<tr>
<td>
DEBUG_PROC_DESC_NO_COMMAND_LINE

</td>
<td>
Do not retrieve the command line.

</td>
</tr>
</table>

### -param ExeName [out, optional]


Receives the name of the executable file used to start the process.  If <i>ExeName</i> is <b>NULL</b>, this information is not returned.

### -param ExeNameSize [in]


Specifies the size in characters of the buffer <i>ExeNameSize</i>. This size includes the space for the '\0' terminating character.

### -param ActualExeNameSize [out, optional]


Receives the size in characters of the executable file name. This size includes the space for the '\0' terminating character. If <i>ExeNameSize</i> is <b>NULL</b>, this information is not returned.

### -param Description [out, optional]


Receives extra information about the process, including service names, MTS package names, and the command line.  If <i>Description</i> is <b>NULL</b>, this information is not returned.

### -param DescriptionSize [in]


Specifies the size in characters of the buffer <i>Description</i>. This size includes the space for the '\0' terminating character.

### -param ActualDescriptionSize [out, optional]


Receives the size in characters of the extra information. This size includes the space for the '\0' terminating character. If <i>ActualDescriptionSize</i> is <b>NULL</b>, this information is not returned.

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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, either <i>ExeNameSize</i> or <i>DescriptionSize</i> were smaller than the size of the respective string and the string was truncated to fit inside the buffer.

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



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocesssystemidbyexecutablename">GetRunningProcessSystemIdByExecutableName</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocesssystemids">GetRunningProcessSystemIds</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>

