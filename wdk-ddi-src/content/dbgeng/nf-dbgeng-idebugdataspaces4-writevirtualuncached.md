---
UID: NF:dbgeng.IDebugDataSpaces4.WriteVirtualUncached
title: IDebugDataSpaces4::WriteVirtualUncached method
author: windows-driver-content
description: The WriteVirtualUncached method writes data to the target's virtual address space.
old-location: debugger\writevirtualuncached.htm
old-project: debugger
ms.assetid: 01b729cb-d7d0-4c8d-a438-51319ef8e1c8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::WriteVirtualUncached, WriteVirtualUncached
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
req.alt-api: IDebugDataSpaces.WriteVirtualUncached,IDebugDataSpaces2.WriteVirtualUncached,IDebugDataSpaces3.WriteVirtualUncached,IDebugDataSpaces4.WriteVirtualUncached
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

# IDebugDataSpaces4::WriteVirtualUncached method



## -description
The <b>WriteVirtualUncached</b> method writes data to the target's virtual address space.



## -syntax

````
HRESULT WriteVirtualUncached(
  [in]            ULONG64 Offset,
  [in]            PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesWritten
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's virtual address space to be written.


### -param Buffer [in]

Specifies the buffer to write the memory from.


### -param BufferSize [in]

Specifies the size in bytes of the buffer.  This is also the number of bytes requested to be written.


### -param BytesWritten [out, optional]

Receives the number of bytes that were actually written.  If it is set to <b>NULL</b>, this information is not returned.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was at least partially successful.  <i>BytesWritten</i> indicates the number of bytes successfully written, which may be less than <i>BufferSize</i>.

 


## -remarks
This method writes the buffer to the memory in the target's virtual address space.

This method behaves identically to <a href="https://msdn.microsoft.com/library/windows/hardware/ff561468">WriteVirtual</a>, except that it avoids using the virtual memory cache.  It is therefore useful for reading inherently volatile virtual memory, such as memory-mapped device areas, without contaminating or invalidating the cache.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561468">WriteVirtual</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554361">ReadVirtualUncached</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces::WriteVirtualUncached method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

