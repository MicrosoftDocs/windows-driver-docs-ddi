---
UID: NF:dbgeng.IDebugDataSpaces3.WriteVirtualUncached
title: IDebugDataSpaces3::WriteVirtualUncached (dbgeng.h)
description: The WriteVirtualUncached method writes data to the target's virtual address space.
old-location: debugger\writevirtualuncached.htm
tech.root: debugger
ms.assetid: 01b729cb-d7d0-4c8d-a438-51319ef8e1c8
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces3::WriteVirtualUncached"]
ms.keywords: IDebugDataSpaces interface [Windows Debugging],WriteVirtualUncached method, IDebugDataSpaces2 interface [Windows Debugging],WriteVirtualUncached method, IDebugDataSpaces2::WriteVirtualUncached, IDebugDataSpaces3 interface [Windows Debugging],WriteVirtualUncached method, IDebugDataSpaces3.WriteVirtualUncached, IDebugDataSpaces3::WriteVirtualUncached, IDebugDataSpaces4 interface [Windows Debugging],WriteVirtualUncached method, IDebugDataSpaces4::WriteVirtualUncached, IDebugDataSpaces::WriteVirtualUncached, IDebugDataSpaces_6b986179-8f9c-4b4f-b42c-0c91088868ec.xml, WriteVirtualUncached, WriteVirtualUncached method [Windows Debugging], WriteVirtualUncached method [Windows Debugging],IDebugDataSpaces interface, WriteVirtualUncached method [Windows Debugging],IDebugDataSpaces2 interface, WriteVirtualUncached method [Windows Debugging],IDebugDataSpaces3 interface, WriteVirtualUncached method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::WriteVirtualUncached, dbgeng/IDebugDataSpaces3::WriteVirtualUncached, dbgeng/IDebugDataSpaces4::WriteVirtualUncached, dbgeng/IDebugDataSpaces::WriteVirtualUncached, debugger.writevirtualuncached
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
 - IDebugDataSpaces3::WriteVirtualUncached
 - dbgeng/IDebugDataSpaces3::WriteVirtualUncached
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces.WriteVirtualUncached
 - IDebugDataSpaces2.WriteVirtualUncached
 - IDebugDataSpaces3.WriteVirtualUncached
 - IDebugDataSpaces4.WriteVirtualUncached
---

# IDebugDataSpaces3::WriteVirtualUncached


## -description

The <b>WriteVirtualUncached</b> method writes data to the target's virtual address space.

## -parameters

### -param Offset 

[in]
Specifies the location in the target's virtual address space to be written.

### -param Buffer 

[in]
Specifies the buffer to write the memory from.

### -param BufferSize 

[in]
Specifies the size in bytes of the buffer.  This is also the number of bytes requested to be written.

### -param BytesWritten 

[out, optional]
Receives the number of bytes that were actually written.  If it is set to <b>NULL</b>, this information is not returned.

## -returns

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

This method behaves identically to <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-writevirtual">WriteVirtual</a>, except that it avoids using the virtual memory cache.  It is therefore useful for reading inherently volatile virtual memory, such as memory-mapped device areas, without contaminating or invalidating the cache.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces">IDebugDataSpaces</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtualuncached">ReadVirtualUncached</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-writevirtual">WriteVirtual</a>