---
UID: NN:dbgeng.IDebugDataSpaces2
title: IDebugDataSpaces2 (dbgeng.h)
description: IDebugDataSpaces2 interface
old-location: debugger\idebugdataspaces2.htm
tech.root: debugger
ms.assetid: a8548f9c-5cb6-4a13-b37c-da28d316b8e1
ms.date: 05/03/2018
ms.keywords: IDebugDataSpaces2, IDebugDataSpaces2 interface [Windows Debugging], IDebugDataSpaces2 interface [Windows Debugging],described, dbgeng/IDebugDataSpaces2, debugger.idebugdataspaces2
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugDataSpaces2"
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
- IDebugDataSpaces2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugDataSpaces2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces">IDebugDataSpaces</a>. <b>IDebugDataSpaces2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugDataSpaces2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-fillphysical">FillPhysical</a>
</td>
<td align="left" width="63%">
Writes a pattern of bytes to the target's physical memory. The pattern is written repeatedly until the specified memory range is filled.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-fillvirtual">FillVirtual</a>
</td>
<td align="left" width="63%">
Writes a pattern of bytes to the target's virtual memory. The pattern is written repeatedly until the specified memory range is filled.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-getvirtualtranslationphysicaloffsets">GetVirtualTranslationPhysicalOffsets</a>
</td>
<td align="left" width="63%">
 Returns the physical addresses of the system paging structures at different levels of the paging hierarchy.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces2-queryvirtual">QueryVirtual</a>
</td>
<td align="left" width="63%">
Provides information about the specified pages in the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-readhandledata">ReadHandleData</a>
</td>
<td align="left" width="63%">
Retrieves information about a system object specified by a system handle.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-virtualtophysical">VirtualToPhysical</a>
</td>
<td align="left" width="63%">
Translates a location in the target's virtual address space into a physical memory address.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces">IDebugDataSpaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>
 

 

