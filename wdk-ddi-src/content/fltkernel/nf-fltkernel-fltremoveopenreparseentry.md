---
UID: NF:fltkernel.FltRemoveOpenReparseEntry
title: FltRemoveOpenReparseEntry function
author: windows-driver-content
description: This routine removes an OPEN_REPARSE_LIST_ENTRY structure (added by FltAddOpenReparseEntry) from a create operation.
old-location: ifsk\fltremoveopenreparseentry.htm
old-project: ifsk
ms.assetid: FD8C3A32-E578-47E9-9B2A-E1809D62F7B8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltRemoveOpenReparseEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltAddOpenReparseEntry
req.alt-loc: fltKernel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _IRQL_requires_max_(APC_LEVEL)
req.typenames: EXpsFontRestriction
---

# FltRemoveOpenReparseEntry function



## -description
This routine removes an <a href="..\ntifs\ns-ntifs-_open_reparse_list_entry.md">OPEN_REPARSE_LIST_ENTRY</a> structure (added by <a href="..\fltkernel\nf-fltkernel-fltaddopenreparseentry.md">FltAddOpenReparseEntry</a>) from a create operation.


<div class="alert"><b>Important</b>  <i>OpenReparseEntry</i> must be an entry added by <a href="..\fltkernel\nf-fltkernel-fltaddopenreparseentry.md">FltAddOpenReparseEntry</a>. All other entries are not valid.</div>
<div> </div>




## -syntax

````
void FltAddOpenReparseEntry(
  _In_ PFLT_FILTER              Filter,
  _In_ PFLT_CALLBACK_DATA       Data,
  _In_ POPEN_REPARSE_LIST_ENTRY OpenReparseEntry
);
````


## -parameters

### -param Filter [in]

The filter to dereference.


### -param Data [in]

The create operation to remove open reparse information
                       from.


### -param OpenReparseEntry [in]

The open reparse information to remove, of type <a href="..\ntifs\ns-ntifs-_open_reparse_list_entry.md">OPEN_REPARSE_LIST_ENTRY</a>.


## -returns
This routine does not return a value.


## -remarks
