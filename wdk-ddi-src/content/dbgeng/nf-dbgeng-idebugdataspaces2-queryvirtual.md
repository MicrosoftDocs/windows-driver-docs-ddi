---
UID: NF:dbgeng.IDebugDataSpaces2.QueryVirtual
title: IDebugDataSpaces2::QueryVirtual (dbgeng.h)
description: The QueryVirtual method provides information about the specified pages in the target's virtual address space.
old-location: debugger\queryvirtual.htm
tech.root: debugger
ms.assetid: 2d607433-0d2d-4662-acd6-9adbce290b97
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces2::QueryVirtual"]
ms.keywords: IDebugDataSpaces2 interface [Windows Debugging],QueryVirtual method, IDebugDataSpaces2.QueryVirtual, IDebugDataSpaces2::QueryVirtual, IDebugDataSpaces_45524d69-d9be-4eb0-971c-3ae6bb6089b2.xml, QueryVirtual, QueryVirtual method [Windows Debugging], QueryVirtual method [Windows Debugging],IDebugDataSpaces2 interface, dbgeng/IDebugDataSpaces2::QueryVirtual, debugger.queryvirtual
f1_keywords:
 - "dbgeng/IDebugDataSpaces2.QueryVirtual"
 - "IDebugDataSpaces2.QueryVirtual"
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
- IDebugDataSpaces2.QueryVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces2::QueryVirtual


## -description


The <b>QueryVirtual</b> method provides information about the specified pages in the target's virtual address space.


## -parameters




### -param Offset [in]

Specifies the location in the target's virtual address space of the pages whose information is requested.


### -param Info [out]

Receives the information about the memory page.


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
</table>
 




## -remarks



This method may not work in all sessions.

This method returns attributes for a range of pages.  This range is determined by Windows; it begins at the specified page, and includes all subsequent pages with the same attributes.  The size of the range is given by the <b>RegionSize</b> field of the structure returned in <i>Info</i>.

MEMORY_BASIC_INFORMATION64 appears in the Microsoft Windows SDK header file winnt.h.  It is the 64-bit equivalent of MEMORY_BASIC_INFORMATION, which is described in the Windows SDK documentation.

This method behaves in a similar way to the Windows SDK function <b>VirtualQuery</b>.  See Windows SDK documentation for details.



