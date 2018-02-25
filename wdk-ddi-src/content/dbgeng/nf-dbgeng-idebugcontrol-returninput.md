---
UID: NF:dbgeng.IDebugControl.ReturnInput
title: IDebugControl::ReturnInput method
author: windows-driver-content
description: The ReturnInput method is used by IDebugInputCallbacks objects to send an input string to the engine following a request for input.
old-location: debugger\returninput.htm
old-project: debugger
ms.assetid: 1f4c63da-8583-4382-a208-8279b4fe0906
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, D, I, IDebugControl, IDebugControl interface [Windows Debugging], ReturnInput method, IDebugControl2 interface [Windows Debugging], ReturnInput method, IDebugControl2::ReturnInput, IDebugControl3 interface [Windows Debugging], ReturnInput method, IDebugControl3::ReturnInput, IDebugControl::ReturnInput, IDebugControl_e060c1a6-43cd-46a1-ba4c-e9aa69bcf205.xml, R, ReturnInput method [Windows Debugging], ReturnInput method [Windows Debugging], IDebugControl interface, ReturnInput method [Windows Debugging], IDebugControl2 interface, ReturnInput method [Windows Debugging], IDebugControl3 interface, ReturnInput,IDebugControl.ReturnInput, b, dbgeng/IDebugControl2::ReturnInput, dbgeng/IDebugControl3::ReturnInput, dbgeng/IDebugControl::ReturnInput, debugger.returninput, e, g, l, n, o, p, r, t, u"
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
-	IDebugControl.ReturnInput
-	IDebugControl2.ReturnInput
-	IDebugControl3.ReturnInput
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl::ReturnInput method


## -description


The <b>ReturnInput</b>  method is used by <b>IDebugInputCallbacks</b> objects to send an input string to the engine following a request for input.


## -syntax


````
HRESULT ReturnInput(
  [in] PCSTR Buffer
);
````


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



