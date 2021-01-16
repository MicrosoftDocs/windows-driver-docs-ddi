---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessExecutableNameWide
title: IDebugSystemObjects4::GetCurrentProcessExecutableNameWide (dbgeng.h)
description: The GetCurrentProcessExecutableNameWide method returns the name of executable file loaded in the current process.
old-location: debugger\getcurrentprocessexecutablenamewide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects4::GetCurrentProcessExecutableNameWide"]
ms.keywords: GetCurrentProcessExecutableNameWide, GetCurrentProcessExecutableNameWide method [Windows Debugging], GetCurrentProcessExecutableNameWide method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentProcessExecutableNameWide method, IDebugSystemObjects4.GetCurrentProcessExecutableNameWide, IDebugSystemObjects4::GetCurrentProcessExecutableNameWide, dbgeng/IDebugSystemObjects4::GetCurrentProcessExecutableNameWide, debugger.getcurrentprocessexecutablenamewide
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
 - IDebugSystemObjects4::GetCurrentProcessExecutableNameWide
 - dbgeng/IDebugSystemObjects4::GetCurrentProcessExecutableNameWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects4::GetCurrentProcessExecutableNameWide
---

# IDebugSystemObjects4::GetCurrentProcessExecutableNameWide


## -description

The <b>GetCurrentProcessExecutableNameWide</b>  method returns the name of executable file loaded in the current process.

## -parameters

### -param Buffer 

[out, optional]
Receives the name of the executable file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size in characters of the buffer <i>Buffer</i>.

### -param ExeSize 

[out, optional]
Receives the size in characters of the name of the executable file.  If <i>ExeSize</i> is <b>NULL</b>, this information is not returned.

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
The method was successful. However, the buffer was not large enough to hold the name of the executable file and it was truncated.

</td>
</tr>
</table>

## -remarks

These methods are only available in user-mode debugging.

If the engine cannot determine the name of the executable file, it writes the string "?NoImage?" to the buffer.

For more information about processes, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.

