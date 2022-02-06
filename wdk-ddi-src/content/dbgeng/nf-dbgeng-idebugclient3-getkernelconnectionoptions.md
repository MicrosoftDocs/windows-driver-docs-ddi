---
UID: NF:dbgeng.IDebugClient3.GetKernelConnectionOptions
title: IDebugClient3::GetKernelConnectionOptions (dbgeng.h)
description: The GetKernelConnectionOptions method returns the connection options for the current kernel target. This method belongs to the IDebugClient3 interface.
old-location: debugger\getkernelconnectionoptions.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["IDebugClient3::GetKernelConnectionOptions"]
ms.keywords: GetKernelConnectionOptions, GetKernelConnectionOptions method [Windows Debugging], GetKernelConnectionOptions method [Windows Debugging],IDebugClient interface, GetKernelConnectionOptions method [Windows Debugging],IDebugClient2 interface, GetKernelConnectionOptions method [Windows Debugging],IDebugClient3 interface, GetKernelConnectionOptions method [Windows Debugging],IDebugClient4 interface, GetKernelConnectionOptions method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetKernelConnectionOptions method, IDebugClient2 interface [Windows Debugging],GetKernelConnectionOptions method, IDebugClient2::GetKernelConnectionOptions, IDebugClient3 interface [Windows Debugging],GetKernelConnectionOptions method, IDebugClient3.GetKernelConnectionOptions, IDebugClient3::GetKernelConnectionOptions, IDebugClient4 interface [Windows Debugging],GetKernelConnectionOptions method, IDebugClient4::GetKernelConnectionOptions, IDebugClient5 interface [Windows Debugging],GetKernelConnectionOptions method, IDebugClient5::GetKernelConnectionOptions, IDebugClient::GetKernelConnectionOptions, IDebugClient_5a7fe06a-42e4-4bdd-935c-8130cdfef568.xml, dbgeng/IDebugClient2::GetKernelConnectionOptions, dbgeng/IDebugClient3::GetKernelConnectionOptions, dbgeng/IDebugClient4::GetKernelConnectionOptions, dbgeng/IDebugClient5::GetKernelConnectionOptions, dbgeng/IDebugClient::GetKernelConnectionOptions, debugger.getkernelconnectionoptions
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
 - IDebugClient3::GetKernelConnectionOptions
 - dbgeng/IDebugClient3::GetKernelConnectionOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient3::GetKernelConnectionOptions
---

# IDebugClient3::GetKernelConnectionOptions


## -description

The <b>GetKernelConnectionOptions</b>  method returns the connection options for the current kernel target.

## -parameters

### -param Buffer [out, optional]


Specifies the buffer to receive the connection options.

### -param BufferSize [in]


Specifies the size in characters of the buffer <i>Buffer</i>. This size includes the space for the '\0' terminating character.

### -param OptionsSize [out, optional]


Receives the size in characters of the connection options. This size includes the space for the '\0' terminating character. If <i>OptionsSize</i> is <b>NULL</b>, this information is not returned.

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
The size of the string was greater than the size of the buffer, so it was truncated to fit into the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
The current target is not a standard live kernel target.

</td>
</tr>
</table>

## -remarks

This method is available only for live kernel targets that are not local and not connected through eXDI.

The connection options returned are the same options used to connect to the kernel.

For more information about connecting to live kernel-mode targets, see <a href="/windows-hardware/drivers/debugger/live-kernel-mode-targets">Live Kernel-Mode Targets</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachkernel">AttachKernel</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>

