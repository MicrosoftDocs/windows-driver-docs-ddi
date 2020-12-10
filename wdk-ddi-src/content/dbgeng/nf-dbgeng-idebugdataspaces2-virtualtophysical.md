---
UID: NF:dbgeng.IDebugDataSpaces2.VirtualToPhysical
title: IDebugDataSpaces2::VirtualToPhysical (dbgeng.h)
description: The VirtualToPhysical method translates a location in the target's virtual address space into a physical memory address.
old-location: debugger\virtualtophysical.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces2::VirtualToPhysical"]
ms.keywords: IDebugDataSpaces2 interface [Windows Debugging],VirtualToPhysical method, IDebugDataSpaces2.VirtualToPhysical, IDebugDataSpaces2::VirtualToPhysical, IDebugDataSpaces3 interface [Windows Debugging],VirtualToPhysical method, IDebugDataSpaces3::VirtualToPhysical, IDebugDataSpaces4 interface [Windows Debugging],VirtualToPhysical method, IDebugDataSpaces4::VirtualToPhysical, IDebugDataSpaces_56267474-49c4-446c-83eb-3e4eb2e92734.xml, VirtualToPhysical, VirtualToPhysical method [Windows Debugging], VirtualToPhysical method [Windows Debugging],IDebugDataSpaces2 interface, VirtualToPhysical method [Windows Debugging],IDebugDataSpaces3 interface, VirtualToPhysical method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::VirtualToPhysical, dbgeng/IDebugDataSpaces3::VirtualToPhysical, dbgeng/IDebugDataSpaces4::VirtualToPhysical, debugger.virtualtophysical
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
 - IDebugDataSpaces2::VirtualToPhysical
 - dbgeng/IDebugDataSpaces2::VirtualToPhysical
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugDataSpaces2.VirtualToPhysical
 - IDebugDataSpaces3.VirtualToPhysical
 - IDebugDataSpaces4.VirtualToPhysical
---

# IDebugDataSpaces2::VirtualToPhysical


## -description

The <b>VirtualToPhysical</b> method translates a location in the target's virtual address space into a physical memory address.

## -parameters

### -param Virtual 

[in]
Specifies the location in the target's virtual address space to translate.

### -param Physical 

[out]
Receives the physical memory address.

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
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_NO_PAGEFILE)</b></dt>
</dl>
</td>
<td width="60%">
No physical page containing the specified address could be found.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method is only available in kernel-mode debugging.
