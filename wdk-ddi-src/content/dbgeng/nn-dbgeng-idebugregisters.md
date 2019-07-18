---
UID: NN:dbgeng.IDebugRegisters
title: IDebugRegisters (dbgeng.h)
description: IDebugRegisters interface
old-location: debugger\idebugregisters.htm
tech.root: debugger
ms.assetid: a2587ea7-20cd-43be-ba71-750e699ee0ce
ms.date: 05/03/2018
ms.keywords: IDebugRegisters, IDebugRegisters interface [Windows Debugging], IDebugRegisters interface [Windows Debugging],described, IDebugRegisters_ca710692-a977-4276-b779-2b66311938dc.xml, dbgeng/IDebugRegisters, debugger.idebugregisters
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugRegisters"
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
- IDebugRegisters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugRegisters</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugRegisters</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugRegisters</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getdescription">GetDescription</a>
</td>
<td align="left" width="63%">
Returns the description of a register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getframeoffset">GetFrameOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the stack frame for the current function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getindexbyname">GetIndexByName</a>
</td>
<td align="left" width="63%">
Returns the index of the named register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getinstructionoffset">GetInstructionOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the current thread's current instruction.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getnumberregisters">GetNumberRegisters</a>
</td>
<td align="left" width="63%">
Returns the number of registers on the target computer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getstackoffset">GetStackOffset</a>
</td>
<td align="left" width="63%">
Returns the current thread's current stack location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getvalue">GetValue</a>
</td>
<td align="left" width="63%">
Gets the value of one of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getvalues">GetValues</a>
</td>
<td align="left" width="63%">
Gets the value of several of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-outputregisters">OutputRegisters</a>
</td>
<td align="left" width="63%">
Formats and sends the target's registers to the clients as output.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setvalue">SetValue</a>
</td>
<td align="left" width="63%">
Sets the value of one of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-setvalues">SetValues</a>
</td>
<td align="left" width="63%">
Sets the value of several of the target's registers.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>
 

 

