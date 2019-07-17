---
UID: NN:dbgeng.IDebugDataSpaces
title: IDebugDataSpaces (dbgeng.h)
description: IDebugDataSpaces interface
old-location: debugger\idebugdataspaces.htm
tech.root: debugger
ms.assetid: 9477821c-4f4f-4ea2-9968-d43f87c496b2
ms.date: 05/03/2018
ms.keywords: IDebugDataSpaces, IDebugDataSpaces interface [Windows Debugging], IDebugDataSpaces interface [Windows Debugging],described, IDebugDataSpaces_83f3a88c-f7e6-4b5c-a2b2-4e8bccef4281.xml, dbgeng/IDebugDataSpaces, debugger.idebugdataspaces
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugDataSpaces"
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
- IDebugDataSpaces
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugDataSpaces</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugDataSpaces</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugDataSpaces</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-checklowmemory">CheckLowMemory</a>
</td>
<td align="left" width="63%">
Checks for memory corruption in the low 4 GB of memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readbusdata">ReadBusData</a>
</td>
<td align="left" width="63%">
Reads data from a system bus.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readcontrol">ReadControl</a>
</td>
<td align="left" width="63%">
Reads implementation-specific system data.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readdebuggerdata">ReadDebuggerData</a>
</td>
<td align="left" width="63%">
Returns information about the target that the debugger engine has queried or determined during the current session.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readio">ReadIo</a>
</td>
<td align="left" width="63%">
Reads from the system and bus I/O memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readmsr">ReadMsr</a>
</td>
<td align="left" width="63%">
Reads a specified Model-Specific Register (MSR).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readphysical">ReadPhysical</a>
</td>
<td align="left" width="63%">
Reads the target's memory from the specified physical address.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readpointersvirtual">ReadPointersVirtual</a>
</td>
<td align="left" width="63%">
 Reads pointers from the target's virtual address space.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readprocessorsystemdata">ReadProcessorSystemData</a>
</td>
<td align="left" width="63%">
Returns data about the specified processor.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtual">ReadVirtual</a>
</td>
<td align="left" width="63%">
Reads memory from the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readvirtualuncached">ReadVirtualUncached</a>
</td>
<td align="left" width="63%">
Reads memory from the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-searchvirtual">SearchVirtual</a>
</td>
<td align="left" width="63%">
Searches the target's virtual memory for a specified pattern of bytes.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-writebusdata">WriteBusData</a>
</td>
<td align="left" width="63%">
Writes data to a system bus.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-writecontrol">WriteControl</a>
</td>
<td align="left" width="63%">
Writes implementation-specific system data.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-writeio">WriteIo</a>
</td>
<td align="left" width="63%">
Writes to the system and bus I/O memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdbgexts/nf-wdbgexts-writemsr">WriteMsr</a>
</td>
<td align="left" width="63%">
Writes a value to the specified Model-Specific Register (MSR).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdbgexts/nf-wdbgexts-writephysical">WritePhysical</a>
</td>
<td align="left" width="63%">
Writes data to the specified physical address in the target's memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-writepointersvirtual">WritePointersVirtual</a>
</td>
<td align="left" width="63%">
Writes pointers to the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-writevirtual">WriteVirtual</a>
</td>
<td align="left" width="63%">
Writes data to the target's virtual address space.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-writevirtualuncached">WriteVirtualUncached</a>
</td>
<td align="left" width="63%">
Writes data to the target's virtual address space.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>
 

 

