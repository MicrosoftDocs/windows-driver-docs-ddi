---
UID: NF:dbgeng.IDebugControl4.ResetManagedStatus
title: IDebugControl4::ResetManagedStatus (dbgeng.h)
description: Clears and reinitializes the engine's managed code debugging support of the runtime debugging APIs provided by the common language runtime (CLR).
old-location: debugger\idebugcontrol4_resetmanagedstatus.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl4::ResetManagedStatus"]
ms.keywords: IDebugControl4 interface [Windows Debugging],ResetManagedStatus method, IDebugControl4.ResetManagedStatus, IDebugControl4::ResetManagedStatus, ResetManagedStatus, ResetManagedStatus method [Windows Debugging], ResetManagedStatus method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::ResetManagedStatus, debugger.idebugcontrol4_resetmanagedstatus
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
 - IDebugControl4::ResetManagedStatus
 - dbgeng/IDebugControl4::ResetManagedStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4::ResetManagedStatus
---

# IDebugControl4::ResetManagedStatus


## -description

Clears and reinitializes the engine's managed code debugging support of the runtime debugging APIs provided by the common language runtime (CLR).

## -parameters

### -param Flags [in]


Flags for the debugging API.

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
 
Managed debugging support relies on debugging functionality provided by the CLR.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>

