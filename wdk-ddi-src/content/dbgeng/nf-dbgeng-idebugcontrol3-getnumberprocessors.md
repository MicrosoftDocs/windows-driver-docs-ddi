---
UID: NF:dbgeng.IDebugControl3.GetNumberProcessors
title: IDebugControl3::GetNumberProcessors method
author: windows-driver-content
description: The GetNumberProcessors method returns the number of processors on the computer running the current target.
old-location: debugger\getnumberprocessors.htm
old-project: debugger
ms.assetid: b3f4af4e-dbba-4f14-8935-f894865cbe7d
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl3::GetNumberProcessors, GetNumberProcessors method [Windows Debugging], IDebugControl2 interface, IDebugControl2 interface [Windows Debugging], GetNumberProcessors method, IDebugControl3, GetNumberProcessors method [Windows Debugging], IDebugControl3 interface, dbgeng/IDebugControl::GetNumberProcessors, debugger.getnumberprocessors, IDebugControl2::GetNumberProcessors, GetNumberProcessors method [Windows Debugging], GetNumberProcessors method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl3::GetNumberProcessors, GetNumberProcessors, dbgeng/IDebugControl2::GetNumberProcessors, IDebugControl interface [Windows Debugging], GetNumberProcessors method, IDebugControl_0ddf74be-971f-4bd8-bdfd-4ceedfbbdc0f.xml, IDebugControl::GetNumberProcessors, IDebugControl3 interface [Windows Debugging], GetNumberProcessors method
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.GetNumberProcessors
-	IDebugControl2.GetNumberProcessors
-	IDebugControl3.GetNumberProcessors
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugControl3::GetNumberProcessors method


## -description


The <b>GetNumberProcessors</b> method returns the number of processors on the computer running the current target.


## -syntax


````
HRESULT GetNumberProcessors(
  [out] PULONG Number
);
````


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


