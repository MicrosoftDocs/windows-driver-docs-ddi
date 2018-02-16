---
UID: NF:dbgeng.IDebugDataSpaces3.ReadVirtual
title: IDebugDataSpaces3::ReadVirtual method
author: windows-driver-content
description: The ReadVirtual method reads memory from the target's virtual address space.
old-location: debugger\readvirtual.htm
old-project: debugger
ms.assetid: 083b0ab5-e2b9-4dcb-b17d-ab2ebde48665
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugDataSpaces::ReadVirtual, IDebugDataSpaces interface [Windows Debugging], ReadVirtual method, IDebugDataSpaces4 interface [Windows Debugging], ReadVirtual method, ReadVirtual method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces4::ReadVirtual, IDebugDataSpaces3::ReadVirtual, IDebugDataSpaces2, dbgeng/IDebugDataSpaces4::ReadVirtual, ReadVirtual, ReadVirtual method [Windows Debugging], dbgeng/IDebugDataSpaces2::ReadVirtual, dbgeng/IDebugDataSpaces3::ReadVirtual, IDebugDataSpaces3, ReadVirtual method [Windows Debugging], IDebugDataSpaces2 interface, ReadVirtual method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces2 interface [Windows Debugging], ReadVirtual method, ReadVirtual method [Windows Debugging], IDebugDataSpaces interface, IDebugDataSpaces2::ReadVirtual, debugger.readvirtual, IDebugDataSpaces, IDebugDataSpaces::ReadVirtual, IDebugDataSpaces_8f9b4f7a-04c6-4775-9d15-a4e1c56ca48c.xml, IDebugDataSpaces3 interface [Windows Debugging], ReadVirtual method
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
-	IDebugDataSpaces.ReadVirtual
-	IDebugDataSpaces2.ReadVirtual
-	IDebugDataSpaces3.ReadVirtual
-	IDebugDataSpaces4.ReadVirtual
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugDataSpaces3::ReadVirtual method


## -description


The <b>ReadVirtual</b> method reads memory from the target's virtual address space.


## -syntax


````
HRESULT ReadVirtual(
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
The method was successful.  It is possible that <i>BytesRead</i> is less than <i>BufferSize</i>, but at least one byte of data was returned.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



This method fills the buffer with the contents of the memory in the target's virtual address space.

This method may reference a cache of memory data when retrieving data.  If the data is volatile, such as memory-mapped hardware state, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554361">ReadVirtualUncached</a> instead.

When reading memory that contains pointers, these pointers are for the target's virtual address space and not the engine's.  For example, if a data structure contained a string, a second call to this method may be needed to read the contents of the string.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554361">ReadVirtualUncached</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561468">WriteVirtual</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces::ReadVirtual method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

