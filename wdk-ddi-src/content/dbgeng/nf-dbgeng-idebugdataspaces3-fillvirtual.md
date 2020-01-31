---
UID: NF:dbgeng.IDebugDataSpaces3.FillVirtual
title: IDebugDataSpaces3::FillVirtual (dbgeng.h)
description: The FillVirtual method writes a pattern of bytes to the target's virtual memory. The pattern is written repeatedly until the specified memory range is filled.
old-location: debugger\fillvirtual.htm
tech.root: debugger
ms.assetid: d55ccd38-00c7-491b-aadf-8b42b5e89600
ms.date: 05/03/2018
ms.keywords: FillVirtual, FillVirtual method [Windows Debugging], FillVirtual method [Windows Debugging],IDebugDataSpaces2 interface, FillVirtual method [Windows Debugging],IDebugDataSpaces3 interface, FillVirtual method [Windows Debugging],IDebugDataSpaces4 interface, IDebugDataSpaces2 interface [Windows Debugging],FillVirtual method, IDebugDataSpaces2::FillVirtual, IDebugDataSpaces3 interface [Windows Debugging],FillVirtual method, IDebugDataSpaces3.FillVirtual, IDebugDataSpaces3::FillVirtual, IDebugDataSpaces4 interface [Windows Debugging],FillVirtual method, IDebugDataSpaces4::FillVirtual, IDebugDataSpaces_26ed83e1-6084-4826-bf6c-30be250d3e3f.xml, dbgeng/IDebugDataSpaces2::FillVirtual, dbgeng/IDebugDataSpaces3::FillVirtual, dbgeng/IDebugDataSpaces4::FillVirtual, debugger.fillvirtual
f1_keywords:
 - "dbgeng/IDebugDataSpaces2.FillVirtual"
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
- IDebugDataSpaces2.FillVirtual
- IDebugDataSpaces3.FillVirtual
- IDebugDataSpaces4.FillVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces3::FillVirtual


## -description


The <b>FillVirtual</b> method writes a pattern of bytes to the target's virtual memory.  The pattern is written repeatedly until the specified memory range is filled.


## -parameters




### -param Start [in]

Specifies the location in the target's virtual address space at which to start writing the pattern.


### -param Size [in]

Specifies how many bytes to write to the target's memory.


### -param Pattern [in]

Specifies the memory location of the pattern.


### -param PatternSize [in]

Specifies the size in bytes of the pattern.


### -param Filled [out, optional]

Receives the number of bytes written.  If it is set to <b>NULL</b>, this information isn't returned.


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
The method was successful.

</td>
</tr>
</table>
 




## -remarks



This method writes the pattern to the target's memory as many times as will fit in <i>Size</i> bytes.

If the final copy of the pattern will not completely fit into the memory range, it will only be partially written.  This includes the case where the size of the pattern is larger than the value of <i>Size</i>, and the extra bytes in the pattern are ignored.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-writevirtual">WriteVirtual</a>
 

 

