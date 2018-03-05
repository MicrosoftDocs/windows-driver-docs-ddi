---
UID: NF:dbgeng.IDebugDataSpaces.WriteVirtualUncached
title: IDebugDataSpaces::WriteVirtualUncached method
author: windows-driver-content
description: The WriteVirtualUncached method writes data to the target's virtual address space.
old-location: debugger\writevirtualuncached.htm
old-project: debugger
ms.assetid: 01b729cb-d7d0-4c8d-a438-51319ef8e1c8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDebugDataSpaces, IDebugDataSpaces interface [Windows Debugging], WriteVirtualUncached method, IDebugDataSpaces2 interface [Windows Debugging], WriteVirtualUncached method, IDebugDataSpaces2::WriteVirtualUncached, IDebugDataSpaces3 interface [Windows Debugging], WriteVirtualUncached method, IDebugDataSpaces3::WriteVirtualUncached, IDebugDataSpaces4 interface [Windows Debugging], WriteVirtualUncached method, IDebugDataSpaces4::WriteVirtualUncached, IDebugDataSpaces::WriteVirtualUncached, IDebugDataSpaces_6b986179-8f9c-4b4f-b42c-0c91088868ec.xml, WriteVirtualUncached method [Windows Debugging], WriteVirtualUncached method [Windows Debugging], IDebugDataSpaces interface, WriteVirtualUncached method [Windows Debugging], IDebugDataSpaces2 interface, WriteVirtualUncached method [Windows Debugging], IDebugDataSpaces3 interface, WriteVirtualUncached method [Windows Debugging], IDebugDataSpaces4 interface, WriteVirtualUncached,IDebugDataSpaces.WriteVirtualUncached, dbgeng/IDebugDataSpaces2::WriteVirtualUncached, dbgeng/IDebugDataSpaces3::WriteVirtualUncached, dbgeng/IDebugDataSpaces4::WriteVirtualUncached, dbgeng/IDebugDataSpaces::WriteVirtualUncached, debugger.writevirtualuncached
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
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces::WriteVirtualUncached method


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

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554361">ReadVirtualUncached</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561468">WriteVirtual</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces::WriteVirtualUncached method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

