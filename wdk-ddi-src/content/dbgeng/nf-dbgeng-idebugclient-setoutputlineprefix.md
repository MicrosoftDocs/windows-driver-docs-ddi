---
UID: NF:dbgeng.IDebugClient.SetOutputLinePrefix
title: IDebugClient::SetOutputLinePrefix (dbgeng.h)
description: Sets a prefix for multiple lines of output.
old-location: debugger\idebugclient_setoutputlineprefix.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient::SetOutputLinePrefix"]
ms.keywords: IDebugClient interface [Windows Debugging],SetOutputLinePrefix method, IDebugClient.SetOutputLinePrefix, IDebugClient::SetOutputLinePrefix, SetOutputLinePrefix, SetOutputLinePrefix method [Windows Debugging], SetOutputLinePrefix method [Windows Debugging],IDebugClient interface, dbgeng/IDebugClient::SetOutputLinePrefix, debugger.idebugclient_setoutputlineprefix
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugClient::SetOutputLinePrefix
 - dbgeng/IDebugClient::SetOutputLinePrefix
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient::SetOutputLinePrefix
---

# IDebugClient::SetOutputLinePrefix


## -description

    Sets a prefix for multiple lines of output.

## -parameters

### -param Prefix 

[in, optional]
A pointer to the prefix value.

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

Some of the engine commands produce
    multiple lines of output.  This function sets a prefix that the engine adds to each line. This function allows the caller to control indentation or identifying marks.

 The prefix value  is not a general setting for any output
    that contains a newline. Methods which use
    the line prefix are marked in their documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>

