---
UID: NF:dbgeng.IDebugControl4.GetManagedStatusWide
title: IDebugControl4::GetManagedStatusWide (dbgeng.h)
description: Provides feedback as a Unicode character string on the engine's use of the runtime debugging APIs provided by the common language runtime (CLR).
old-location: debugger\idebugcontrol4_getmanagedstatuswide.htm
tech.root: debugger
ms.assetid: 5854BB6A-EB5F-493A-96E4-0DF298EC0332
ms.date: 05/03/2018
keywords: ["IDebugControl4::GetManagedStatusWide"]
ms.keywords: GetManagedStatusWide, GetManagedStatusWide method [Windows Debugging], GetManagedStatusWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetManagedStatusWide method, IDebugControl4.GetManagedStatusWide, IDebugControl4::GetManagedStatusWide, dbgeng/IDebugControl4::GetManagedStatusWide, debugger.idebugcontrol4_getmanagedstatuswide
f1_keywords:
 - "dbgeng/IDebugControl4.GetManagedStatusWide"
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
- IDebugControl4.GetManagedStatusWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetManagedStatusWide


## -description


 Provides feedback as a Unicode character string on the engine's
    use of the runtime debugging APIs provided by the common language runtime (CLR).


## -parameters




### -param Flags [out, optional]

A pointer to flags from the debugging APIs.


### -param WhichString [in]

A value that controls which string to use.


### -param String [out]

A pointer to a Unicode character string from the debugging APIs.


### -param StringSize [in]

The size of the string.


### -param StringNeeded [out, optional]

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
 

Managed debugging support relies on debugging functionality provided by the CLR.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>
 

 

