---
UID: NF:dbgeng.IDebugDataSpaces2.WritePointersVirtual
title: IDebugDataSpaces2::WritePointersVirtual (dbgeng.h)
description: The WritePointersVirtual method is a convenience method for writing pointers to the target's virtual address space.
old-location: debugger\writepointersvirtual.htm
tech.root: debugger
ms.assetid: b6bde54b-262a-4431-8f85-63f9c66463c4
ms.date: 05/03/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging],WritePointersVirtual method, IDebugDataSpaces2 interface [Windows Debugging],WritePointersVirtual method, IDebugDataSpaces2.WritePointersVirtual, IDebugDataSpaces2::WritePointersVirtual, IDebugDataSpaces3 interface [Windows Debugging],WritePointersVirtual method, IDebugDataSpaces3::WritePointersVirtual, IDebugDataSpaces4 interface [Windows Debugging],WritePointersVirtual method, IDebugDataSpaces4::WritePointersVirtual, IDebugDataSpaces::WritePointersVirtual, IDebugDataSpaces_da1045b5-8b82-4412-8e83-58c285dccce0.xml, WritePointersVirtual, WritePointersVirtual method [Windows Debugging], WritePointersVirtual method [Windows Debugging],IDebugDataSpaces interface, WritePointersVirtual method [Windows Debugging],IDebugDataSpaces2 interface, WritePointersVirtual method [Windows Debugging],IDebugDataSpaces3 interface, WritePointersVirtual method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::WritePointersVirtual, dbgeng/IDebugDataSpaces3::WritePointersVirtual, dbgeng/IDebugDataSpaces4::WritePointersVirtual, dbgeng/IDebugDataSpaces::WritePointersVirtual, debugger.writepointersvirtual
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugDataSpaces.WritePointersVirtual"
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
- IDebugDataSpaces.WritePointersVirtual
- IDebugDataSpaces2.WritePointersVirtual
- IDebugDataSpaces3.WritePointersVirtual
- IDebugDataSpaces4.WritePointersVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces2::WritePointersVirtual


## -description


The <b>WritePointersVirtual</b> method is a convenience method for writing pointers to the target's virtual address space.


## -parameters




### -param Count [in]

Specifies the number of pointers to write.


### -param Offset [in]

Specifies the location in the target's virtual address space at which to start writing the pointers.


### -param Ptrs [in]

Specifies the array of pointers to write.  The number of elements in this array is <i>Count</i>.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
All the pointers in <i>Ptrs</i>  were written to the target's memory.

</td>
</tr>
</table>
 




## -remarks



If the target uses 32-bit pointers, this method casts the specified  64-bit values into 32-bit pointers.  Then it writes these pointers to the target's memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces">IDebugDataSpaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readpointersvirtual">ReadPointersVirtual</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-writevirtual">WriteVirtual</a>
 

 

