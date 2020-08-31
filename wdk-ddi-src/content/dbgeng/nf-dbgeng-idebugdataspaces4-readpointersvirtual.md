---
UID: NF:dbgeng.IDebugDataSpaces4.ReadPointersVirtual
title: IDebugDataSpaces4::ReadPointersVirtual (dbgeng.h)
description: The ReadPointersVirtual method is a convenience method for reading pointers from the target's virtual address space.
old-location: debugger\readpointersvirtual.htm
tech.root: debugger
ms.assetid: 003fd20c-12d6-40b0-8e43-a7d730199846
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces4::ReadPointersVirtual"]
ms.keywords: IDebugDataSpaces interface [Windows Debugging],ReadPointersVirtual method, IDebugDataSpaces2 interface [Windows Debugging],ReadPointersVirtual method, IDebugDataSpaces2::ReadPointersVirtual, IDebugDataSpaces3 interface [Windows Debugging],ReadPointersVirtual method, IDebugDataSpaces3::ReadPointersVirtual, IDebugDataSpaces4 interface [Windows Debugging],ReadPointersVirtual method, IDebugDataSpaces4.ReadPointersVirtual, IDebugDataSpaces4::ReadPointersVirtual, IDebugDataSpaces::ReadPointersVirtual, IDebugDataSpaces_d3857a69-3e22-4d7a-97ef-d6cb7bf8613a.xml, ReadPointersVirtual, ReadPointersVirtual method [Windows Debugging], ReadPointersVirtual method [Windows Debugging],IDebugDataSpaces interface, ReadPointersVirtual method [Windows Debugging],IDebugDataSpaces2 interface, ReadPointersVirtual method [Windows Debugging],IDebugDataSpaces3 interface, ReadPointersVirtual method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::ReadPointersVirtual, dbgeng/IDebugDataSpaces3::ReadPointersVirtual, dbgeng/IDebugDataSpaces4::ReadPointersVirtual, dbgeng/IDebugDataSpaces::ReadPointersVirtual, debugger.readpointersvirtual
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
 - IDebugDataSpaces4::ReadPointersVirtual
 - dbgeng/IDebugDataSpaces4::ReadPointersVirtual
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces.ReadPointersVirtual
 - IDebugDataSpaces2.ReadPointersVirtual
 - IDebugDataSpaces3.ReadPointersVirtual
 - IDebugDataSpaces4.ReadPointersVirtual
---

# IDebugDataSpaces4::ReadPointersVirtual


## -description

The <b>ReadPointersVirtual</b> method is a convenience method for reading pointers from the target's virtual address space.

## -parameters

### -param Count 

[in]
Specifies the number of pointers to read.

### -param Offset 

[in]
Specifies the location in the target's virtual address space to start reading the pointers.

### -param Ptrs 

[out]
Specifies the array to store the pointers.  The number of elements this array holds is <i>Count</i>.

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
All the pointers were read from the target's memory and stored in <i>Ptrs</i>.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method reads from the memory from the target's virtual address space.  The memory is then treated as a list of pointers.  Any 32-bit pointers are then sign-extended to  64-bit values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces">IDebugDataSpaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtual">ReadVirtual</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-writepointersvirtual">WritePointersVirtual</a>

