---
UID: NF:dbgeng.IDebugClient3.SetOutputMask
title: IDebugClient3::SetOutputMask (dbgeng.h)
description: The SetOutputMask method sets the output mask for the client.
old-location: debugger\setoutputmask.htm
tech.root: debugger
ms.assetid: 8fef4def-9735-4623-841b-a18995d4d403
ms.date: 05/03/2018
ms.keywords: IDebugClient interface [Windows Debugging],SetOutputMask method, IDebugClient2 interface [Windows Debugging],SetOutputMask method, IDebugClient2::SetOutputMask, IDebugClient3 interface [Windows Debugging],SetOutputMask method, IDebugClient3.SetOutputMask, IDebugClient3::SetOutputMask, IDebugClient4 interface [Windows Debugging],SetOutputMask method, IDebugClient4::SetOutputMask, IDebugClient5 interface [Windows Debugging],SetOutputMask method, IDebugClient5::SetOutputMask, IDebugClient::SetOutputMask, IDebugClient_85242101-702d-4c9a-b71a-5eddd76a4fa6.xml, SetOutputMask, SetOutputMask method [Windows Debugging], SetOutputMask method [Windows Debugging],IDebugClient interface, SetOutputMask method [Windows Debugging],IDebugClient2 interface, SetOutputMask method [Windows Debugging],IDebugClient3 interface, SetOutputMask method [Windows Debugging],IDebugClient4 interface, SetOutputMask method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::SetOutputMask, dbgeng/IDebugClient3::SetOutputMask, dbgeng/IDebugClient4::SetOutputMask, dbgeng/IDebugClient5::SetOutputMask, dbgeng/IDebugClient::SetOutputMask, debugger.setoutputmask
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
- IDebugClient.SetOutputMask
- IDebugClient2.SetOutputMask
- IDebugClient3.SetOutputMask
- IDebugClient4.SetOutputMask
- IDebugClient5.SetOutputMask
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient3::SetOutputMask


## -description


The <b>SetOutputMask</b> method sets the output mask for the client.


## -parameters




### -param Mask [in]

Specifies the new output mask for the client.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-output-xxx">DEBUG_OUTPUT_XXX</a> for a description of the possible values for <i>Mask</i>.


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



For an overview of output in the debugger engine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/input-and-output">Input and Output</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-getoutputmask">GetOutputMask</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-setotheroutputmask">SetOtherOutputMask</a>
 

 

