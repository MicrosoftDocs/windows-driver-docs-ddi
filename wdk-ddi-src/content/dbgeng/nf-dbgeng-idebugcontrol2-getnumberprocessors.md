---
UID: NF:dbgeng.IDebugControl2.GetNumberProcessors
title: IDebugControl2::GetNumberProcessors method
author: windows-driver-content
description: The GetNumberProcessors method returns the number of processors on the computer running the current target.
old-location: debugger\getnumberprocessors.htm
old-project: debugger
ms.assetid: b3f4af4e-dbba-4f14-8935-f894865cbe7d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetNumberProcessors method [Windows Debugging], GetNumberProcessors method [Windows Debugging], IDebugControl interface, GetNumberProcessors method [Windows Debugging], IDebugControl2 interface, GetNumberProcessors method [Windows Debugging], IDebugControl3 interface, GetNumberProcessors,IDebugControl2.GetNumberProcessors, IDebugControl interface [Windows Debugging], GetNumberProcessors method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetNumberProcessors method, IDebugControl2::GetNumberProcessors, IDebugControl3 interface [Windows Debugging], GetNumberProcessors method, IDebugControl3::GetNumberProcessors, IDebugControl::GetNumberProcessors, IDebugControl_0ddf74be-971f-4bd8-bdfd-4ceedfbbdc0f.xml, dbgeng/IDebugControl2::GetNumberProcessors, dbgeng/IDebugControl3::GetNumberProcessors, dbgeng/IDebugControl::GetNumberProcessors, debugger.getnumberprocessors
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.GetNumberProcessors
-	IDebugControl2.GetNumberProcessors
-	IDebugControl3.GetNumberProcessors
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetNumberProcessors method


## -description


The <b>GetNumberProcessors</b> method returns the number of processors on the computer running the current target.


## -parameters




### -param Number [out]

Receives the number of processors.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.



