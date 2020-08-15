---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessExecutableName
title: IDebugSystemObjects4::GetCurrentProcessExecutableName (dbgeng.h)
description: The GetCurrentProcessExecutableName method returns the name of executable file loaded in the current process.
old-location: debugger\getcurrentprocessexecutablename.htm
tech.root: debugger
ms.assetid: ea968316-a53d-4ab1-966a-5c699ffb8f2a
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects4::GetCurrentProcessExecutableName"]
ms.keywords: GetCurrentProcessExecutableName, GetCurrentProcessExecutableName method [Windows Debugging], GetCurrentProcessExecutableName method [Windows Debugging],IDebugSystemObjects interface, GetCurrentProcessExecutableName method [Windows Debugging],IDebugSystemObjects2 interface, GetCurrentProcessExecutableName method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentProcessExecutableName method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetCurrentProcessExecutableName method, IDebugSystemObjects2 interface [Windows Debugging],GetCurrentProcessExecutableName method, IDebugSystemObjects2::GetCurrentProcessExecutableName, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentProcessExecutableName method, IDebugSystemObjects3::GetCurrentProcessExecutableName, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentProcessExecutableName method, IDebugSystemObjects4.GetCurrentProcessExecutableName, IDebugSystemObjects4::GetCurrentProcessExecutableName, IDebugSystemObjects::GetCurrentProcessExecutableName, IDebugSystemObjects_2659a668-4ecb-44de-b287-b4adc830f8c4.xml, dbgeng/IDebugSystemObjects2::GetCurrentProcessExecutableName, dbgeng/IDebugSystemObjects3::GetCurrentProcessExecutableName, dbgeng/IDebugSystemObjects4::GetCurrentProcessExecutableName, dbgeng/IDebugSystemObjects::GetCurrentProcessExecutableName, debugger.getcurrentprocessexecutablename
f1_keywords:
 - "dbgeng/IDebugSystemObjects.GetCurrentProcessExecutableName"
 - "IDebugSystemObjects.GetCurrentProcessExecutableName"
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
- IDebugSystemObjects.GetCurrentProcessExecutableName
- IDebugSystemObjects2.GetCurrentProcessExecutableName
- IDebugSystemObjects3.GetCurrentProcessExecutableName
- IDebugSystemObjects4.GetCurrentProcessExecutableName
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects4::GetCurrentProcessExecutableName


## -description


The <b>GetCurrentProcessExecutableName</b>  method returns the name of executable file loaded in the current process.


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

For more information about processes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.



