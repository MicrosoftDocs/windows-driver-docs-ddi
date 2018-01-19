---
UID: NF:dbgeng.IDebugDataSpaces4.VirtualToPhysical
title: IDebugDataSpaces4::VirtualToPhysical method
author: windows-driver-content
description: The VirtualToPhysical method translates a location in the target's virtual address space into a physical memory address.
old-location: debugger\virtualtophysical.htm
old-project: debugger
ms.assetid: e0b7bd4c-cb3f-4bc3-8359-241c9a245204
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::VirtualToPhysical, VirtualToPhysical
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
req.alt-api: IDebugDataSpaces2.VirtualToPhysical,IDebugDataSpaces3.VirtualToPhysical,IDebugDataSpaces4.VirtualToPhysical
req.alt-loc: Dbgeng.h
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

# IDebugDataSpaces4::VirtualToPhysical method



## -description
The <b>VirtualToPhysical</b> method translates a location in the target's virtual address space into a physical memory address.



## -syntax

````
HRESULT VirtualToPhysical(
  [in]  ULONG64  Virtual,
  [out] PULONG64 Physical
);
````


## -parameters

### -param Virtual [in]

Specifies the location in the target's virtual address space to translate.


### -param Physical [out]

Receives the physical memory address.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_NO_PAGEFILE)</b></dt>
</dl>No physical page containing the specified address could be found.

 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
This method is only available in kernel-mode debugging.</p>