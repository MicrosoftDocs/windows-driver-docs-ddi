---
UID: NF:dbgeng.IDebugDataSpaces2.GetVirtualTranslationPhysicalOffsets
title: IDebugDataSpaces2::GetVirtualTranslationPhysicalOffsets (dbgeng.h)
description: The GetVirtualTranslationPhysicalOffsets method returns the physical addresses of the system paging structures at different levels of the paging hierarchy.
old-location: debugger\getvirtualtranslationphysicaloffsets.htm
tech.root: debugger
ms.assetid: 40438ee7-2e58-4048-8739-75f21179c22c
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces2::GetVirtualTranslationPhysicalOffsets"]
ms.keywords: GetVirtualTranslationPhysicalOffsets, GetVirtualTranslationPhysicalOffsets method [Windows Debugging], GetVirtualTranslationPhysicalOffsets method [Windows Debugging],IDebugDataSpaces2 interface, GetVirtualTranslationPhysicalOffsets method [Windows Debugging],IDebugDataSpaces3 interface, GetVirtualTranslationPhysicalOffsets method [Windows Debugging],IDebugDataSpaces4 interface, IDebugDataSpaces2 interface [Windows Debugging],GetVirtualTranslationPhysicalOffsets method, IDebugDataSpaces2.GetVirtualTranslationPhysicalOffsets, IDebugDataSpaces2::GetVirtualTranslationPhysicalOffsets, IDebugDataSpaces3 interface [Windows Debugging],GetVirtualTranslationPhysicalOffsets method, IDebugDataSpaces3::GetVirtualTranslationPhysicalOffsets, IDebugDataSpaces4 interface [Windows Debugging],GetVirtualTranslationPhysicalOffsets method, IDebugDataSpaces4::GetVirtualTranslationPhysicalOffsets, IDebugDataSpaces_661959c5-a514-4651-8eaa-fd4c4fb94bd7.xml, dbgeng/IDebugDataSpaces2::GetVirtualTranslationPhysicalOffsets, dbgeng/IDebugDataSpaces3::GetVirtualTranslationPhysicalOffsets, dbgeng/IDebugDataSpaces4::GetVirtualTranslationPhysicalOffsets, debugger.getvirtualtranslationphysicaloffsets
f1_keywords:
 - "dbgeng/IDebugDataSpaces2.GetVirtualTranslationPhysicalOffsets"
 - "IDebugDataSpaces2.GetVirtualTranslationPhysicalOffsets"
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
- IDebugDataSpaces2.GetVirtualTranslationPhysicalOffsets
- IDebugDataSpaces3.GetVirtualTranslationPhysicalOffsets
- IDebugDataSpaces4.GetVirtualTranslationPhysicalOffsets
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces2::GetVirtualTranslationPhysicalOffsets


## -description


The <b>GetVirtualTranslationPhysicalOffsets</b> method returns the physical addresses of the system paging structures at different levels of the paging hierarchy.


## -parameters




### -param Virtual [in]

Specifies the location in the target's virtual address space to translate.


### -param Offsets [out, optional]

Receives the physical addresses for the system paging structures.  If it is set to <b>NULL</b>, this information is not returned.


### -param OffsetsSize [in]

Specifies the number of elements the array <i>Offsets</i> holds.  This is the maximum number of addresses that will be returned.


### -param Levels [out, optional]

Receives the number of levels in the paging hierarchy for the specified address.  If this is <b>NULL</b>, this information is not returned.


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
 




## -remarks



This method is only available in kernel-mode debugging.

Translating a virtual address to a physical address requires Windows  to walk down the paging hierarchy.  At each level it reads paging information from physical memory.  This method returns the offsets for these physical pages.  The number of levels in the paging hierarchy may be different for different addresses.

The address at the last level of the hierarchy is the physical address corresponding to the specified virtual address.  This is what <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-virtualtophysical">VirtualToPhysical</a> would return.

For details on how virtual addresses are translated into physical addresses, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.



