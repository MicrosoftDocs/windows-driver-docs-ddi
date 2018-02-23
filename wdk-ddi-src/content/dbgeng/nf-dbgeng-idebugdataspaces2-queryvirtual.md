---
UID: NF:dbgeng.IDebugDataSpaces2.QueryVirtual
title: IDebugDataSpaces2::QueryVirtual method
author: windows-driver-content
description: The QueryVirtual method provides information about the specified pages in the target's virtual address space.
old-location: debugger\queryvirtual.htm
old-project: debugger
ms.assetid: 2d607433-0d2d-4662-acd6-9adbce290b97
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: QueryVirtual, dbgeng/IDebugDataSpaces2::QueryVirtual, debugger.queryvirtual, IDebugDataSpaces2 interface [Windows Debugging], QueryVirtual method, IDebugDataSpaces_45524d69-d9be-4eb0-971c-3ae6bb6089b2.xml, QueryVirtual method [Windows Debugging], IDebugDataSpaces2::QueryVirtual, QueryVirtual method [Windows Debugging], IDebugDataSpaces2 interface, IDebugDataSpaces2
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugDataSpaces2.QueryVirtual
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
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



This method may not work in all sessions.

This method returns attributes for a range of pages.  This range is determined by Windows; it begins at the specified page, and includes all subsequent pages with the same attributes.  The size of the range is given by the <b>RegionSize</b> field of the structure returned in <i>Info</i>.

MEMORY_BASIC_INFORMATION64 appears in the Microsoft Windows SDK header file winnt.h.  It is the 64-bit equivalent of MEMORY_BASIC_INFORMATION, which is described in the Windows SDK documentation.

This method behaves in a similar way to the Windows SDK function <b>VirtualQuery</b>.  See Windows SDK documentation for details.



