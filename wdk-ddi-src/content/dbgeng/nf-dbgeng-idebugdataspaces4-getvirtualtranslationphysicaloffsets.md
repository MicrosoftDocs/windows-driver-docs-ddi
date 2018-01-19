---
UID: NF:dbgeng.IDebugDataSpaces4.GetVirtualTranslationPhysicalOffsets
title: IDebugDataSpaces4::GetVirtualTranslationPhysicalOffsets method
author: windows-driver-content
description: The GetVirtualTranslationPhysicalOffsets method returns the physical addresses of the system paging structures at different levels of the paging hierarchy.
old-location: debugger\getvirtualtranslationphysicaloffsets.htm
old-project: debugger
ms.assetid: 40438ee7-2e58-4048-8739-75f21179c22c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::GetVirtualTranslationPhysicalOffsets, GetVirtualTranslationPhysicalOffsets
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugDataSpaces2.GetVirtualTranslationPhysicalOffsets,IDebugDataSpaces3.GetVirtualTranslationPhysicalOffsets,IDebugDataSpaces4.GetVirtualTranslationPhysicalOffsets
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugDataSpaces4::GetVirtualTranslationPhysicalOffsets method



## -description
The <b>GetVirtualTranslationPhysicalOffsets</b> method returns the physical addresses of the system paging structures at different levels of the paging hierarchy.



## -syntax

````
HRESULT GetVirtualTranslationPhysicalOffsets(
  [in]            ULONG64  Virtual,
  [out, optional] PULONG64 Offsets,
  [in]            ULONG    OffsetsSize,
  [out, optional] PULONG   Levels
);
````


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
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_NO_PAGEFILE)</b></dt>
</dl>No physical page containing the specified address could be found.

 


## -remarks
This method is only available in kernel-mode debugging.

Translating a virtual address to a physical address requires Windows  to walk down the paging hierarchy.  At each level it reads paging information from physical memory.  This method returns the offsets for these physical pages.  The number of levels in the paging hierarchy may be different for different addresses.

The address at the last level of the hierarchy is the physical address corresponding to the specified virtual address.  This is what <a href="https://msdn.microsoft.com/library/windows/hardware/ff560335">VirtualToPhysical</a> would return.

For details on how virtual addresses are translated into physical addresses, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.</p>