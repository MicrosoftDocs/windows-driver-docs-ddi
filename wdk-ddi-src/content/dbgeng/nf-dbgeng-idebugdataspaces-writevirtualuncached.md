---
UID: NF:dbgeng.IDebugDataSpaces.WriteVirtualUncached
title: IDebugDataSpaces::WriteVirtualUncached
author: windows-driver-content
description: The WriteVirtualUncached method writes data to the target's virtual address space.
old-location: debugger\writevirtualuncached.htm
tech.root: debugger
ms.assetid: 01b729cb-d7d0-4c8d-a438-51319ef8e1c8
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging],WriteVirtualUncached method, IDebugDataSpaces.WriteVirtualUncached, IDebugDataSpaces2 interface [Windows Debugging],WriteVirtualUncached method, IDebugDataSpaces2::WriteVirtualUncached, IDebugDataSpaces3 interface [Windows Debugging],WriteVirtualUncached method, IDebugDataSpaces3::WriteVirtualUncached, IDebugDataSpaces4 interface [Windows Debugging],WriteVirtualUncached method, IDebugDataSpaces4::WriteVirtualUncached, IDebugDataSpaces::WriteVirtualUncached, IDebugDataSpaces_6b986179-8f9c-4b4f-b42c-0c91088868ec.xml, WriteVirtualUncached, WriteVirtualUncached method [Windows Debugging], WriteVirtualUncached method [Windows Debugging],IDebugDataSpaces interface, WriteVirtualUncached method [Windows Debugging],IDebugDataSpaces2 interface, WriteVirtualUncached method [Windows Debugging],IDebugDataSpaces3 interface, WriteVirtualUncached method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::WriteVirtualUncached, dbgeng/IDebugDataSpaces3::WriteVirtualUncached, dbgeng/IDebugDataSpaces4::WriteVirtualUncached, dbgeng/IDebugDataSpaces::WriteVirtualUncached, debugger.writevirtualuncached
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
-	IDebugDataSpaces.WriteVirtualUncached
-	IDebugDataSpaces2.WriteVirtualUncached
-	IDebugDataSpaces3.WriteVirtualUncached
-	IDebugDataSpaces4.WriteVirtualUncached
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces::WriteVirtualUncached


## -description


The <b>WriteVirtualUncached</b> method writes data to the target's virtual address space.


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
The method was at least partially successful.  <i>BytesWritten</i> indicates the number of bytes successfully written, which may be less than <i>BufferSize</i>.

</td>
</tr>
</table>
 




## -remarks



This method writes the buffer to the memory in the target's virtual address space.

This method behaves identically to <a href="https://msdn.microsoft.com/library/windows/hardware/ff561468">WriteVirtual</a>, except that it avoids using the virtual memory cache.  It is therefore useful for reading inherently volatile virtual memory, such as memory-mapped device areas, without contaminating or invalidating the cache.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550528">IDebugDataSpaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550531">IDebugDataSpaces2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550537">IDebugDataSpaces3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550546">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554361">ReadVirtualUncached</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561468">WriteVirtual</a>
 

 

