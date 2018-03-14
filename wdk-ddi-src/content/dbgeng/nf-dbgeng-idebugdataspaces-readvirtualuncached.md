---
UID: NF:dbgeng.IDebugDataSpaces.ReadVirtualUncached
title: IDebugDataSpaces::ReadVirtualUncached method
author: windows-driver-content
description: The ReadVirtualUncached method reads memory from the target's virtual address space.
old-location: debugger\readvirtualuncached.htm
old-project: debugger
ms.assetid: 91674220-3160-40d2-9d68-56d854244711
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugDataSpaces, IDebugDataSpaces interface [Windows Debugging], ReadVirtualUncached method, IDebugDataSpaces2 interface [Windows Debugging], ReadVirtualUncached method, IDebugDataSpaces2::ReadVirtualUncached, IDebugDataSpaces3 interface [Windows Debugging], ReadVirtualUncached method, IDebugDataSpaces3::ReadVirtualUncached, IDebugDataSpaces4 interface [Windows Debugging], ReadVirtualUncached method, IDebugDataSpaces4::ReadVirtualUncached, IDebugDataSpaces::ReadVirtualUncached, IDebugDataSpaces_265817a7-d690-4b8c-957f-06ec5d4f2f08.xml, ReadVirtualUncached method [Windows Debugging], ReadVirtualUncached method [Windows Debugging], IDebugDataSpaces interface, ReadVirtualUncached method [Windows Debugging], IDebugDataSpaces2 interface, ReadVirtualUncached method [Windows Debugging], IDebugDataSpaces3 interface, ReadVirtualUncached method [Windows Debugging], IDebugDataSpaces4 interface, ReadVirtualUncached,IDebugDataSpaces.ReadVirtualUncached, dbgeng/IDebugDataSpaces2::ReadVirtualUncached, dbgeng/IDebugDataSpaces3::ReadVirtualUncached, dbgeng/IDebugDataSpaces4::ReadVirtualUncached, dbgeng/IDebugDataSpaces::ReadVirtualUncached, debugger.readvirtualuncached
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
-	IDebugDataSpaces.ReadVirtualUncached
-	IDebugDataSpaces2.ReadVirtualUncached
-	IDebugDataSpaces3.ReadVirtualUncached
-	IDebugDataSpaces4.ReadVirtualUncached
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces::ReadVirtualUncached method


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
The method was successful.  It is possible that <i>BytesRead</i> is less than <i>BufferSize</i>, but at least one byte of data is being returned.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



This method fills the buffer with the contents of the memory in the target's virtual address space.

This method behaves identically to <a href="https://msdn.microsoft.com/library/windows/hardware/ff554359">ReadVirtual</a>, except that it avoids using the virtual memory cache.  It is therefore useful for reading inherently volatile virtual memory, such as memory-mapped device areas, without contaminating or invalidating the cache.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554359">ReadVirtual</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561473">WriteVirtualUncached</a>



 

 


