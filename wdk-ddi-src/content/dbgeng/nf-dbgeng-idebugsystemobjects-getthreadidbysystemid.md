---
UID: NF:dbgeng.IDebugSystemObjects.GetThreadIdBySystemId
title: IDebugSystemObjects::GetThreadIdBySystemId (dbgeng.h)
description: The GetThreadIdBySystemId method returns the engine thread ID for the specified thread. The thread is specified by its system thread ID.
old-location: debugger\getthreadidbysystemid.htm
tech.root: debugger
ms.assetid: 2dcb7703-df66-4795-bf59-d0851c4ccf0f
ms.date: 05/03/2018
ms.keywords: GetThreadIdBySystemId, GetThreadIdBySystemId method [Windows Debugging], GetThreadIdBySystemId method [Windows Debugging],IDebugSystemObjects interface, GetThreadIdBySystemId method [Windows Debugging],IDebugSystemObjects2 interface, GetThreadIdBySystemId method [Windows Debugging],IDebugSystemObjects3 interface, GetThreadIdBySystemId method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetThreadIdBySystemId method, IDebugSystemObjects.GetThreadIdBySystemId, IDebugSystemObjects2 interface [Windows Debugging],GetThreadIdBySystemId method, IDebugSystemObjects2::GetThreadIdBySystemId, IDebugSystemObjects3 interface [Windows Debugging],GetThreadIdBySystemId method, IDebugSystemObjects3::GetThreadIdBySystemId, IDebugSystemObjects4 interface [Windows Debugging],GetThreadIdBySystemId method, IDebugSystemObjects4::GetThreadIdBySystemId, IDebugSystemObjects::GetThreadIdBySystemId, IDebugSystemObjects_d9c3c65f-9078-4be8-b301-dddc789cd8b0.xml, dbgeng/IDebugSystemObjects2::GetThreadIdBySystemId, dbgeng/IDebugSystemObjects3::GetThreadIdBySystemId, dbgeng/IDebugSystemObjects4::GetThreadIdBySystemId, dbgeng/IDebugSystemObjects::GetThreadIdBySystemId, debugger.getthreadidbysystemid
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
- IDebugSystemObjects.GetThreadIdBySystemId
- IDebugSystemObjects2.GetThreadIdBySystemId
- IDebugSystemObjects3.GetThreadIdBySystemId
- IDebugSystemObjects4.GetThreadIdBySystemId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects::GetThreadIdBySystemId


## -description


The <b>GetThreadIdBySystemId</b> method returns the engine thread ID for the specified thread.  The thread is specified by its system thread ID.


## -parameters




### -param SysId [in]

Specifies the system thread ID.


### -param Id [out]

Receives the engine thread ID.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The target is a kernel-mode target.

</td>
</tr>
</table>
 




## -remarks



This method is only available in user-mode debugging.

For more information about threads, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.



