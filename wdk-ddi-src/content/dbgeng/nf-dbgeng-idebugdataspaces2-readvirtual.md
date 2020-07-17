---
UID: NF:dbgeng.IDebugDataSpaces2.ReadVirtual
title: IDebugDataSpaces2::ReadVirtual (dbgeng.h)
description: The ReadVirtual method reads memory from the target's virtual address space.
old-location: debugger\readvirtual.htm
tech.root: debugger
ms.assetid: 083b0ab5-e2b9-4dcb-b17d-ab2ebde48665
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces2::ReadVirtual"]
ms.keywords: IDebugDataSpaces interface [Windows Debugging],ReadVirtual method, IDebugDataSpaces2 interface [Windows Debugging],ReadVirtual method, IDebugDataSpaces2.ReadVirtual, IDebugDataSpaces2::ReadVirtual, IDebugDataSpaces3 interface [Windows Debugging],ReadVirtual method, IDebugDataSpaces3::ReadVirtual, IDebugDataSpaces4 interface [Windows Debugging],ReadVirtual method, IDebugDataSpaces4::ReadVirtual, IDebugDataSpaces::ReadVirtual, IDebugDataSpaces_8f9b4f7a-04c6-4775-9d15-a4e1c56ca48c.xml, ReadVirtual, ReadVirtual method [Windows Debugging], ReadVirtual method [Windows Debugging],IDebugDataSpaces interface, ReadVirtual method [Windows Debugging],IDebugDataSpaces2 interface, ReadVirtual method [Windows Debugging],IDebugDataSpaces3 interface, ReadVirtual method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::ReadVirtual, dbgeng/IDebugDataSpaces3::ReadVirtual, dbgeng/IDebugDataSpaces4::ReadVirtual, dbgeng/IDebugDataSpaces::ReadVirtual, debugger.readvirtual
f1_keywords:
 - "dbgeng/IDebugDataSpaces.ReadVirtual"
 - "IDebugDataSpaces.ReadVirtual"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugDataSpaces.ReadVirtual
- IDebugDataSpaces2.ReadVirtual
- IDebugDataSpaces3.ReadVirtual
- IDebugDataSpaces4.ReadVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces2::ReadVirtual


## -description


The <b>ReadVirtual</b> method reads memory from the target's virtual address space.


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
 

This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



This method fills the buffer with the contents of the memory in the target's virtual address space.

This method may reference a cache of memory data when retrieving data.  If the data is volatile, such as memory-mapped hardware state, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtualuncached">ReadVirtualUncached</a> instead.

When reading memory that contains pointers, these pointers are for the target's virtual address space and not the engine's.  For example, if a data structure contained a string, a second call to this method may be needed to read the contents of the string.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces">IDebugDataSpaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtualuncached">ReadVirtualUncached</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-writevirtual">WriteVirtual</a>
 

 

