---
UID: NF:dbgeng.IDebugControl4.InputWide
title: IDebugControl4::InputWide method
author: windows-driver-content
description: The InputWide method requests an input string from the debugger engine.
old-location: debugger\inputwide.htm
old-project: debugger
ms.assetid: 79997d8c-4641-4953-a1a2-e5bde88cbc3f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl4::InputWide, dbgeng/IDebugControl4::InputWide, IDebugControl4 interface [Windows Debugging], InputWide method, InputWide method [Windows Debugging], InputWide, IDebugControl4, InputWide method [Windows Debugging], IDebugControl4 interface, debugger.inputwide
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
-	IDebugControl4.InputWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl4::InputWide method


## -description


The <b>InputWide</b>  method requests an input string from the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.


## -syntax


````
HRESULT InputWide(
  [out]           PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG InputSize
);
````


## -parameters




### -param Buffer [out]

Receives the input string from the engine.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param InputSize [out, optional]

Receives the number of characters returned in <i>Buffer</i>.  If <i>InputSize</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not big enough to hold the whole input string and it was truncated.

</td>
</tr>
</table>
 




## -remarks



For an overview of input in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.



