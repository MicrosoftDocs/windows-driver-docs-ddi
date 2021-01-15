---
UID: NF:dbgeng.IDebugClient3.GetOtherOutputMask
title: IDebugClient3::GetOtherOutputMask (dbgeng.h)
description: The GetOtherOutputMask method returns the output mask for another client.
old-location: debugger\getotheroutputmask.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient3::GetOtherOutputMask"]
ms.keywords: GetOtherOutputMask, GetOtherOutputMask method [Windows Debugging], GetOtherOutputMask method [Windows Debugging],IDebugClient interface, GetOtherOutputMask method [Windows Debugging],IDebugClient2 interface, GetOtherOutputMask method [Windows Debugging],IDebugClient3 interface, GetOtherOutputMask method [Windows Debugging],IDebugClient4 interface, GetOtherOutputMask method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetOtherOutputMask method, IDebugClient2 interface [Windows Debugging],GetOtherOutputMask method, IDebugClient2::GetOtherOutputMask, IDebugClient3 interface [Windows Debugging],GetOtherOutputMask method, IDebugClient3.GetOtherOutputMask, IDebugClient3::GetOtherOutputMask, IDebugClient4 interface [Windows Debugging],GetOtherOutputMask method, IDebugClient4::GetOtherOutputMask, IDebugClient5 interface [Windows Debugging],GetOtherOutputMask method, IDebugClient5::GetOtherOutputMask, IDebugClient::GetOtherOutputMask, IDebugClient_780a02ad-2f51-4142-a0d2-74220bf52623.xml, dbgeng/IDebugClient2::GetOtherOutputMask, dbgeng/IDebugClient3::GetOtherOutputMask, dbgeng/IDebugClient4::GetOtherOutputMask, dbgeng/IDebugClient5::GetOtherOutputMask, dbgeng/IDebugClient::GetOtherOutputMask, debugger.getotheroutputmask
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
 - IDebugClient3::GetOtherOutputMask
 - dbgeng/IDebugClient3::GetOtherOutputMask
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient3::GetOtherOutputMask
---

# IDebugClient3::GetOtherOutputMask


## -description

The <b>GetOtherOutputMask</b> method returns the output mask for another client.

## -parameters

### -param Client 

[in]
Specifies the client whose output mask is desired.

### -param Mask 

[out]
Receives the output mask for the client.  See <a href="/windows-hardware/drivers/debugger/debug-output-xxx">DEBUG_OUTPUT_XXX</a> for details on how to interpret this value.

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

For an overview of output in the debugger engine, see <a href="/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getoutputmask">GetOutputMask</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setotheroutputmask">SetOtherOutputMask</a>

