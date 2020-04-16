---
UID: NF:dbgeng.IDebugClient.GetOutputWidth
title: IDebugClient::GetOutputWidth (dbgeng.h)
description: Gets the width of an output line for commands that produce formatted output.
old-location: debugger\idebugclient_getoutputwidth.htm
tech.root: debugger
ms.assetid: FE76DA51-400E-4F64-B8D9-8738D2F5031A
ms.date: 05/03/2018
keywords: ["IDebugClient::GetOutputWidth"]
ms.keywords: GetOutputWidth, GetOutputWidth method [Windows Debugging], GetOutputWidth method [Windows Debugging],IDebugClient interface, IDebugClient interface [Windows Debugging],GetOutputWidth method, IDebugClient.GetOutputWidth, IDebugClient::GetOutputWidth, dbgeng/IDebugClient::GetOutputWidth, debugger.idebugclient_getoutputwidth
f1_keywords:
 - "dbgeng/IDebugClient.GetOutputWidth"
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
- IDebugClient.GetOutputWidth
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient::GetOutputWidth


## -description


Gets the width of an output line for
    commands that produce formatted output. 


## -parameters




### -param Columns [out]

The number of columns in the output.


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



This setting is a suggestion that can be overridden by other settings.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>
 

 

