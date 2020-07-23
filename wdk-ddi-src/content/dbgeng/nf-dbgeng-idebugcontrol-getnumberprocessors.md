---
UID: NF:dbgeng.IDebugControl.GetNumberProcessors
title: IDebugControl::GetNumberProcessors (dbgeng.h)
description: The GetNumberProcessors method returns the number of processors on the computer running the current target.
old-location: debugger\getnumberprocessors.htm
tech.root: debugger
ms.assetid: b3f4af4e-dbba-4f14-8935-f894865cbe7d
ms.date: 05/03/2018
keywords: ["IDebugControl::GetNumberProcessors"]
ms.keywords: GetNumberProcessors, GetNumberProcessors method [Windows Debugging], GetNumberProcessors method [Windows Debugging],IDebugControl interface, GetNumberProcessors method [Windows Debugging],IDebugControl2 interface, GetNumberProcessors method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetNumberProcessors method, IDebugControl.GetNumberProcessors, IDebugControl2 interface [Windows Debugging],GetNumberProcessors method, IDebugControl2::GetNumberProcessors, IDebugControl3 interface [Windows Debugging],GetNumberProcessors method, IDebugControl3::GetNumberProcessors, IDebugControl::GetNumberProcessors, IDebugControl_0ddf74be-971f-4bd8-bdfd-4ceedfbbdc0f.xml, dbgeng/IDebugControl2::GetNumberProcessors, dbgeng/IDebugControl3::GetNumberProcessors, dbgeng/IDebugControl::GetNumberProcessors, debugger.getnumberprocessors
f1_keywords:
 - "dbgeng/IDebugControl.GetNumberProcessors"
 - "IDebugControl.GetNumberProcessors"
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
- IDebugControl.GetNumberProcessors
- IDebugControl2.GetNumberProcessors
- IDebugControl3.GetNumberProcessors
targetos: Windows
req.typenames: 
---

# IDebugControl::GetNumberProcessors


## -description


The <b>GetNumberProcessors</b> method returns the number of processors on the computer running the current target.


## -parameters




### -param Number [out]

Receives the number of processors.


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



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/target-information">Target Information</a>.



