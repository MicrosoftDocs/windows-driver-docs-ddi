---
UID: NF:dbgeng.IDebugSymbols3.ReadTypedDataPhysical
title: IDebugSymbols3::ReadTypedDataPhysical method
author: windows-driver-content
description: The ReadTypedDataPhysical method reads the value of a variable from the target computer's physical memory.
old-location: debugger\readtypeddataphysical.htm
old-project: debugger
ms.assetid: 72562325-27f9-4e80-b03f-8926adad99c1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::ReadTypedDataPhysical, ReadTypedDataPhysical
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
req.alt-api: IDebugSymbols.ReadTypedDataPhysical,IDebugSymbols2.ReadTypedDataPhysical,IDebugSymbols3.ReadTypedDataPhysical
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

# IDebugSymbols3::ReadTypedDataPhysical method



## -description
The <b>ReadTypedDataPhysical</b> method reads the value of a variable from the target computer's physical memory.



## -syntax

````
HRESULT ReadTypedDataPhysical(
  [in]            ULONG64 Offset,
  [in]            ULONG64 Module,
  [in]            ULONG   TypeId,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````


## -parameters

### -param Offset [in]

Specifies the physical address in the target computer's memory of the variable to be read.


### -param Module [in]

Specifies the base address of the module containing the type of the variable.


### -param TypeId [in]

Specifies the type ID of the type of the variable.


### -param Buffer [out]

Receives the data that was read.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.


### -param BytesRead [out, optional]

Receives the number of bytes that were read.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful.  However, the buffer <i>Buffer</i> was not large enough to hold all the data and it was truncated.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
This method is only available in kernel mode debugging.

The number of bytes this method attempts to read is the smaller of the size of the buffer and the size of the variable.

This is a convenience method.  The same result can be obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a> and <a href="..\dbgeng\nf-dbgeng-idebugdataspaces-readphysical.md">ReadPhysical</a>.

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.</p>