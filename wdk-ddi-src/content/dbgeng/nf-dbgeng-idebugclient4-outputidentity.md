---
UID: NF:dbgeng.IDebugClient4.OutputIdentity
title: IDebugClient4::OutputIdentity (dbgeng.h)
description: The OutputIdentity method formats and outputs a string describing the computer and user this client represents.
old-location: debugger\outputidentity.htm
tech.root: debugger
ms.assetid: 0e8ced7c-87f3-4366-8137-b0d19dffc340
ms.date: 05/03/2018
keywords: ["IDebugClient4::OutputIdentity"]
ms.keywords: IDebugClient interface [Windows Debugging],OutputIdentity method, IDebugClient2 interface [Windows Debugging],OutputIdentity method, IDebugClient2::OutputIdentity, IDebugClient3 interface [Windows Debugging],OutputIdentity method, IDebugClient3::OutputIdentity, IDebugClient4 interface [Windows Debugging],OutputIdentity method, IDebugClient4.OutputIdentity, IDebugClient4::OutputIdentity, IDebugClient5 interface [Windows Debugging],OutputIdentity method, IDebugClient5::OutputIdentity, IDebugClient::OutputIdentity, IDebugClient_2013e1cd-3c95-4ef7-a53f-004ba30d9ea2.xml, OutputIdentity, OutputIdentity method [Windows Debugging], OutputIdentity method [Windows Debugging],IDebugClient interface, OutputIdentity method [Windows Debugging],IDebugClient2 interface, OutputIdentity method [Windows Debugging],IDebugClient3 interface, OutputIdentity method [Windows Debugging],IDebugClient4 interface, OutputIdentity method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::OutputIdentity, dbgeng/IDebugClient3::OutputIdentity, dbgeng/IDebugClient4::OutputIdentity, dbgeng/IDebugClient5::OutputIdentity, dbgeng/IDebugClient::OutputIdentity, debugger.outputidentity
f1_keywords:
 - "dbgeng/IDebugClient.OutputIdentity"
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
- IDebugClient.OutputIdentity
- IDebugClient2.OutputIdentity
- IDebugClient3.OutputIdentity
- IDebugClient4.OutputIdentity
- IDebugClient5.OutputIdentity
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient4::OutputIdentity


## -description


The <b>OutputIdentity</b> method formats and outputs a string describing the computer and user this client represents.


## -parameters




### -param OutputControl [in]

Specifies where to send the output.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.


### -param Flags [in]

Set to zero.


### -param Format [in]

Specifies a format string similar to the <b>printf</b> format string.  However, this format string must only contain one formatting directive, <b>%s</b>, which will be replaced by a description of the computer and user this client represents.


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



The specific content of the string varies with the operating system.  If the client is remotely connected, some network information may also be present.

For more information about client objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/client-objects">Client Objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getidentity">GetIdentity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

