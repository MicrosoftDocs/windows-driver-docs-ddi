---
UID: NF:dbgeng.IDebugDataSpaces3.ReadVirtualUncached
title: IDebugDataSpaces3::ReadVirtualUncached (dbgeng.h)
description: The ReadVirtualUncached method reads memory from the target's virtual address space.
old-location: debugger\readvirtualuncached.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces3::ReadVirtualUncached"]
ms.keywords: IDebugDataSpaces interface [Windows Debugging],ReadVirtualUncached method, IDebugDataSpaces2 interface [Windows Debugging],ReadVirtualUncached method, IDebugDataSpaces2::ReadVirtualUncached, IDebugDataSpaces3 interface [Windows Debugging],ReadVirtualUncached method, IDebugDataSpaces3.ReadVirtualUncached, IDebugDataSpaces3::ReadVirtualUncached, IDebugDataSpaces4 interface [Windows Debugging],ReadVirtualUncached method, IDebugDataSpaces4::ReadVirtualUncached, IDebugDataSpaces::ReadVirtualUncached, IDebugDataSpaces_265817a7-d690-4b8c-957f-06ec5d4f2f08.xml, ReadVirtualUncached, ReadVirtualUncached method [Windows Debugging], ReadVirtualUncached method [Windows Debugging],IDebugDataSpaces interface, ReadVirtualUncached method [Windows Debugging],IDebugDataSpaces2 interface, ReadVirtualUncached method [Windows Debugging],IDebugDataSpaces3 interface, ReadVirtualUncached method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::ReadVirtualUncached, dbgeng/IDebugDataSpaces3::ReadVirtualUncached, dbgeng/IDebugDataSpaces4::ReadVirtualUncached, dbgeng/IDebugDataSpaces::ReadVirtualUncached, debugger.readvirtualuncached
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugDataSpaces3::ReadVirtualUncached
 - dbgeng/IDebugDataSpaces3::ReadVirtualUncached
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces3::ReadVirtualUncached
---

# IDebugDataSpaces3::ReadVirtualUncached


## -description

The <b>ReadVirtualUncached</b> method reads memory from the target's virtual address space.

## -parameters

### -param Offset 

[in]
Specifies the location in the target's virtual address space to be read.

### -param Buffer 

[out]
Specifies the buffer to read the memory into.

### -param BufferSize 

[in]
Specifies the size in bytes of the buffer.  This is also the number of bytes being requested.

### -param BytesRead 

[out, optional]
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
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method fills the buffer with the contents of the memory in the target's virtual address space.

This method behaves identically to <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtual">ReadVirtual</a>, except that it avoids using the virtual memory cache.  It is therefore useful for reading inherently volatile virtual memory, such as memory-mapped device areas, without contaminating or invalidating the cache.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces">IDebugDataSpaces</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtual">ReadVirtual</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-writevirtualuncached">WriteVirtualUncached</a>

