---
UID: NF:dbgeng.IDebugClient.GetOutputLinePrefix
title: IDebugClient::GetOutputLinePrefix (dbgeng.h)
description: Gets the prefix used for multiple lines of output.
old-location: debugger\idebugclient_getoutputlineprefix.htm
tech.root: debugger
ms.assetid: FE836B10-1782-4B0E-9D4B-2740FE94B6E1
ms.date: 05/03/2018
ms.keywords: GetOutputLinePrefix, GetOutputLinePrefix method [Windows Debugging], GetOutputLinePrefix method [Windows Debugging],IDebugClient interface, IDebugClient interface [Windows Debugging],GetOutputLinePrefix method, IDebugClient.GetOutputLinePrefix, IDebugClient::GetOutputLinePrefix, dbgeng/IDebugClient::GetOutputLinePrefix, debugger.idebugclient_getoutputlineprefix
f1_keywords:
 - "dbgeng/IDebugClient.GetOutputLinePrefix"
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
- IDebugClient.GetOutputLinePrefix
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient::GetOutputLinePrefix


## -description


    Gets the prefix used for multiple lines of output.


## -parameters




### -param Buffer [out]

A pointer to the buffer to get the prefix.


### -param BufferSize [in]

The size of the buffer.


### -param PrefixSize [out, optional]

A pointer to the size of the buffer.


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



Some of the engine commands produce
    multiple lines of output.  A prefix can be added to each line. 

 The prefix value  is not a general setting for any output
    that contains a newline. Methods which use
    the line prefix are marked in their documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>
 

 

