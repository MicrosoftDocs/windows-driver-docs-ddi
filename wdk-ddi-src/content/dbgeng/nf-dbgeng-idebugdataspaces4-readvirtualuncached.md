---
UID: NF:dbgeng.IDebugDataSpaces4.ReadVirtualUncached
title: IDebugDataSpaces4::ReadVirtualUncached method
author: windows-driver-content
description: The ReadVirtualUncached method reads memory from the target's virtual address space.
old-location: debugger\readvirtualuncached.htm
old-project: debugger
ms.assetid: 91674220-3160-40d2-9d68-56d854244711
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::ReadVirtualUncached, ReadVirtualUncached
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
req.alt-api: IDebugDataSpaces.ReadVirtualUncached,IDebugDataSpaces2.ReadVirtualUncached,IDebugDataSpaces3.ReadVirtualUncached,IDebugDataSpaces4.ReadVirtualUncached
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

# IDebugDataSpaces4::ReadVirtualUncached method



## -description
The <b>ReadVirtualUncached</b> method reads memory from the target's virtual address space.



## -syntax

````
HRESULT ReadVirtualUncached(
  [in]            ULONG64 Offset,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's virtual address space to be read.


### -param Buffer [out]

Specifies the buffer to read the memory into.


### -param BufferSize [in]

Specifies the size in bytes of the buffer.  This is also the number of bytes being requested.


### -param BytesRead [out, optional]

Receives the number of bytes that were read.  If it is set to <b>NULL</b>, this information is not returned.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.  It is possible that <i>BytesRead</i> is less than <i>BufferSize</i>, but at least one byte of data is being returned.

 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
This method fills the buffer with the contents of the memory in the target's virtual address space.

This method behaves identically to <a href="https://msdn.microsoft.com/library/windows/hardware/ff554359">ReadVirtual</a>, except that it avoids using the virtual memory cache.  It is therefore useful for reading inherently volatile virtual memory, such as memory-mapped device areas, without contaminating or invalidating the cache.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554359">ReadVirtual</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561473">WriteVirtualUncached</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces::ReadVirtualUncached method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

