---
UID: NF:dbgeng.IDebugDataSpaces4.WriteControl
title: IDebugDataSpaces4::WriteControl method
author: windows-driver-content
description: The WriteControl method writes implementation-specific system data.
old-location: debugger\writecontrol.htm
old-project: debugger
ms.assetid: 0b512c66-7cd8-4605-87d5-13b78d790c8c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::WriteControl, WriteControl
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
req.alt-api: IDebugDataSpaces.WriteControl,IDebugDataSpaces2.WriteControl,IDebugDataSpaces3.WriteControl,IDebugDataSpaces4.WriteControl
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

# IDebugDataSpaces4::WriteControl method



## -description
The <b>WriteControl</b> method writes implementation-specific system data.



## -syntax

````
HRESULT WriteControl(
  [in]            ULONG   Processor,
  [in]            ULONG64 Offset,
  [in]            PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesWritten
);
````


## -parameters

### -param Processor [in]

Specifies the processor whose information is to be written.


### -param Offset [in]

Specifies the offset of the control space of the memory to write.


### -param Buffer [in]

Specifies the data to write to the control-space memory.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be written.


### -param BytesWritten [out, optional]

Receives the number of bytes returned in the buffer <i>Buffer</i>.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
This method is only available in kernel-mode debugging.</p>