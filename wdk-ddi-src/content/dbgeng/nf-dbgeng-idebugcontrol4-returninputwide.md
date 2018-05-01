---
UID: NF:dbgeng.IDebugControl4.ReturnInputWide
title: IDebugControl4::ReturnInputWide
author: windows-driver-content
description: The ReturnInputWide method is used by IDebugInputCallbacks objects to send an input string to the engine following a request for input.
old-location: debugger\returninputwide.htm
old-project: debugger
ms.assetid: 6e7f0995-14d0-4dd3-b598-2f988a2ec4fd
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugControl4 interface [Windows Debugging],ReturnInputWide method, IDebugControl4.ReturnInputWide, IDebugControl4::ReturnInputWide, ReturnInputWide, ReturnInputWide method [Windows Debugging], ReturnInputWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::ReturnInputWide, debugger.returninputwide
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
-	IDebugControl4.ReturnInputWide
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::ReturnInputWide


## -description


The <b>ReturnInputWide</b>  method is used by <b>IDebugInputCallbacks</b> objects to send an input string to the engine following a request for input.


## -parameters




### -param Buffer [in]

Specifies the input string being sent to the engine.


## -returns



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
The engine had already received the input it requested. The input string in <i>Buffer</i> was not received by the engine.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



For an overview of input in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.



