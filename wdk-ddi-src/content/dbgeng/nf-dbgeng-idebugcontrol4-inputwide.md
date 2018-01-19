---
UID: NF:dbgeng.IDebugControl4.InputWide
title: IDebugControl4::InputWide method
author: windows-driver-content
description: The InputWide method requests an input string from the debugger engine.
old-location: debugger\inputwide.htm
old-project: debugger
ms.assetid: 79997d8c-4641-4953-a1a2-e5bde88cbc3f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl4, IDebugControl4::InputWide, InputWide
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
req.alt-api: IDebugControl4.InputWide
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl4::InputWide method



## -description
The <b>InputWide</b>  method requests an input string from the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>.



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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful. However, the buffer was not big enough to hold the whole input string and it was truncated.

 


## -remarks
For an overview of input in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.</p>