---
UID: NN:dbgeng.IDebugRegisters2
title: IDebugRegisters2 (dbgeng.h)
description: IDebugRegisters2 interface
old-location: debugger\idebugregisters2.htm
tech.root: debugger
ms.assetid: f92a75a9-6578-4bbf-8d80-680493b4d284
ms.date: 05/03/2018
ms.keywords: IDebugRegisters2, IDebugRegisters2 interface [Windows Debugging], IDebugRegisters2 interface [Windows Debugging],described, dbgeng/IDebugRegisters2, debugger.idebugregisters2
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugRegisters2"
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
- IDebugRegisters2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugRegisters2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a>. <b>IDebugRegisters2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugRegisters2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getdescriptionwide">GetDescriptionWide</a>
</td>
<td align="left" width="63%">
Returns the description of a register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getframeoffset2">GetFrameOffset2</a>
</td>
<td align="left" width="63%">
Returns the location of the stack frame for the current function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getindexbynamewide">GetIndexByNameWide</a>
</td>
<td align="left" width="63%">
Returns the index of the named register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getinstructionoffset2">GetInstructionOffset2</a>
</td>
<td align="left" width="63%">
Returns the location of the current thread's current instruction.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getnumberpseudoregisters">GetNumberPseudoRegisters</a>
</td>
<td align="left" width="63%">
Returns the number of pseudo-registers that are maintained by the debugger engine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getpseudodescription">GetPseudoDescription</a>
</td>
<td align="left" width="63%">
Returns a description of a pseudo-register, including its name and type. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getpseudodescriptionwide">GetPseudoDescriptionWide</a>
</td>
<td align="left" width="63%">
Returns a description of a pseudo-register, including its name and type. (Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getpseudoindexbyname">GetPseudoIndexByName</a>
</td>
<td align="left" width="63%">
Returns the index of a pseudo-register. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getpseudoindexbynamewide">GetPseudoIndexByNameWide</a>
</td>
<td align="left" width="63%">
Returns the index of a pseudo-register. (Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getpseudovalues">GetPseudoValues</a>
</td>
<td align="left" width="63%">
Returns the values of a number of pseudo-registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getstackoffset2">GetStackOffset2</a>
</td>
<td align="left" width="63%">
Returns the current thread's current stack location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-getvalues2">GetValues2</a>
</td>
<td align="left" width="63%">
Fetches the value of several of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-outputregisters2">OutputRegisters2</a>
</td>
<td align="left" width="63%">
Formats and outputs the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-setpseudovalues">SetPseudoValues</a>
</td>
<td align="left" width="63%">
Sets the value of several pseudo-registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugregisters2-setvalues2">SetValues2</a>
</td>
<td align="left" width="63%">
Sets the value of several of the target's registers.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a>
 

 

