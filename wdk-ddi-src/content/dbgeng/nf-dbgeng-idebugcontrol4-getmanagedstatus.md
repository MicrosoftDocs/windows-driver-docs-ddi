---
UID: NF:dbgeng.IDebugControl4.GetManagedStatus
title: IDebugControl4::GetManagedStatus (dbgeng.h)
description: Provides feedback on the engine's use of the runtime debugging APIs provided by the common language runtime (CLR).
old-location: debugger\idebugcontrol4_getmanagedstatus.htm
tech.root: debugger
ms.assetid: C2D32ABB-5ABE-4580-9577-1144569EA8E1
ms.date: 05/03/2018
keywords: ["IDebugControl4::GetManagedStatus"]
ms.keywords: GetManagedStatus, GetManagedStatus method [Windows Debugging], GetManagedStatus method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetManagedStatus method, IDebugControl4.GetManagedStatus, IDebugControl4::GetManagedStatus, dbgeng/IDebugControl4::GetManagedStatus, debugger.idebugcontrol4_getmanagedstatus
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
 - IDebugControl4::GetManagedStatus
 - dbgeng/IDebugControl4::GetManagedStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4.GetManagedStatus
---

# IDebugControl4::GetManagedStatus


## -description

 Provides feedback on the engine's
    use of the runtime debugging APIs provided by the common language runtime (CLR).

## -parameters

### -param Flags 

[out, optional]
A pointer to flags from the debugging APIs.

### -param WhichString 

[in]
A value that controls which string to use.

### -param String 

[out]
A pointer to a string from the debugging APIs.

### -param StringSize 

[in]
The size of the string.

### -param StringNeeded 

[out, optional]
A pointer to an output string.

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
 

    Managed debugging support relies on debugging
    functionality provided by the CLR.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>

