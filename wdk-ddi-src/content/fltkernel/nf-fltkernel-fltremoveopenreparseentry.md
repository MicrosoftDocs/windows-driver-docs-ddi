---
UID: NF:fltkernel.FltRemoveOpenReparseEntry
title: FltRemoveOpenReparseEntry function (fltkernel.h)
description: This routine removes an OPEN_REPARSE_LIST_ENTRY structure (added by FltAddOpenReparseEntry) from a create operation.
old-location: ifsk\fltremoveopenreparseentry.htm
tech.root: ifsk
ms.assetid: FD8C3A32-E578-47E9-9B2A-E1809D62F7B8
ms.date: 04/16/2018
ms.keywords: FltAddOpenReparseEntry, FltAddOpenReparseEntry routine [Installable File System Drivers], FltRemoveOpenReparseEntry, fltkernel/FltAddOpenReparseEntry, ifsk.fltremoveopenreparseentry
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

# FltRemoveOpenReparseEntry function


## -description


This routine removes an <a href="https://msdn.microsoft.com/A6D28F60-FA38-45EA-9E3C-D2E6F899333E">OPEN_REPARSE_LIST_ENTRY</a> structure (added by <a href="https://msdn.microsoft.com/library/windows/hardware/mt734255">FltAddOpenReparseEntry</a>) from a create operation.


<div class="alert"><b>Important</b>  <i>OpenReparseEntry</i> must be an entry added by <a href="https://msdn.microsoft.com/library/windows/hardware/mt734255">FltAddOpenReparseEntry</a>. All other entries are not valid.</div>
<div> </div>



## -parameters




### -param Filter [in]

The filter to dereference.


### -param Data [in]

The create operation to remove open reparse information
                       from.


### -param OpenReparseEntry [in]

The open reparse information to remove, of type <a href="https://msdn.microsoft.com/A6D28F60-FA38-45EA-9E3C-D2E6F899333E">OPEN_REPARSE_LIST_ENTRY</a>.


## -returns



This routine does not return a value.



