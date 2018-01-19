---
UID: NF:dbgeng.IDebugDataSpaces2.QueryVirtual
title: IDebugDataSpaces2::QueryVirtual method
author: windows-driver-content
description: The QueryVirtual method provides information about the specified pages in the target's virtual address space.
old-location: debugger\queryvirtual.htm
old-project: debugger
ms.assetid: 2d607433-0d2d-4662-acd6-9adbce290b97
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces2, IDebugDataSpaces2::QueryVirtual, QueryVirtual
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
req.alt-api: IDebugDataSpaces2.QueryVirtual
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

# IDebugDataSpaces2::QueryVirtual method



## -description
The <b>QueryVirtual</b> method provides information about the specified pages in the target's virtual address space.



## -syntax

````
HRESULT QueryVirtual(
  [in]  ULONG64                     Offset,
  [out] PMEMORY_BASIC_INFORMATION64 Info
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's virtual address space of the pages whose information is requested.


### -param Info [out]

Receives the information about the memory page.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
This method may not work in all sessions.

This method returns attributes for a range of pages.  This range is determined by Windows; it begins at the specified page, and includes all subsequent pages with the same attributes.  The size of the range is given by the <b>RegionSize</b> field of the structure returned in <i>Info</i>.

MEMORY_BASIC_INFORMATION64 appears in the Microsoft Windows SDK header file winnt.h.  It is the 64-bit equivalent of MEMORY_BASIC_INFORMATION, which is described in the Windows SDK documentation.

This method behaves in a similar way to the Windows SDK function <b>VirtualQuery</b>.  See Windows SDK documentation for details.</p>