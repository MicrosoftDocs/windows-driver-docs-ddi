---
UID: NF:fltkernel.FltAddOpenReparseEntry
title: FltAddOpenReparseEntry function (fltkernel.h)
description: This routine adds a caller allocated open reparse structure, OPEN_REPARSE_LIST_ENTRY, into a create operation.
old-location: ifsk\fltaddopenreparseentry.htm
tech.root: ifsk
ms.assetid: D58AB46A-0D87-45B5-8C58-E99ED0F906D2
ms.date: 04/16/2018
ms.keywords: FltAddOpenReparseEntry, FltAddOpenReparseEntry routine [Installable File System Drivers], fltkernel/FltAddOpenReparseEntry, ifsk.fltaddopenreparseentry
ms.topic: function
req.header: fltkernel.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
req.irql: "_IRQL_requires_max_(APC_LEVEL)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltKernel.h
api_name:
-	FltAddOpenReparseEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltAddOpenReparseEntry function


## -description


This routine adds a caller allocated open reparse structure, <a href="https://msdn.microsoft.com/A6D28F60-FA38-45EA-9E3C-D2E6F899333E">OPEN_REPARSE_LIST_ENTRY</a>,  into a create operation.


## -parameters




### -param Filter [in]

The filter to reference.


### -param Data [in]

The create operation to attach open reparse information to.


### -param OpenReparseEntry [in]

The open reparse information to add, of type <a href="https://msdn.microsoft.com/A6D28F60-FA38-45EA-9E3C-D2E6F899333E">OPEN_REPARSE_LIST_ENTRY</a>.


## -returns



The following NT status codes are returned.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
Status code if <i>Data</i> is not a create operation. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
</table>
 




## -remarks



This routine adds an ECP list and/or ECP as needed.  <i>Filter</i> is referenced
    for the lifetime of the open reparse entry structure, not the ECP itself,
    which is conceptually independent of any specific filter.

Use <a href="https://msdn.microsoft.com/library/windows/hardware/mt734261">FltRemoveOpenReparseEntry</a> to remove the open reparse structure from the create operation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt734261">FltRemoveOpenReparseEntry</a>
 

 

