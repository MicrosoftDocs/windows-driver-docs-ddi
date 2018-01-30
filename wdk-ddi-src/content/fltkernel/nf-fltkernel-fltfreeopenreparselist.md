---
UID: NF:fltkernel.FltFreeOpenReparseList
title: FltFreeOpenReparseList function
author: windows-driver-content
description: This routine deallocates any information copied into a create operation by a previous call to FltCopyOpenReparseList.
old-location: ifsk\fltfreeopenreparselist.htm
old-project: ifsk
ms.assetid: 78FA1585-F834-48E4-BB15-78BA5563F9D0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltFreeOpenReparseList, ifsk.fltfreeopenreparselist, FltAddOpenReparseEntry, fltkernel/FltAddOpenReparseEntry, FltAddOpenReparseEntry routine [Installable File System Drivers]
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "_IRQL_requires_max_(APC_LEVEL)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltKernel.h
apiname:
-	FltAddOpenReparseEntry
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFreeOpenReparseList function


## -description


This routine deallocates any information copied into a create operation by
    a previous call to <a href="..\fltkernel\nf-fltkernel-fltcopyopenreparselist.md">FltCopyOpenReparseList</a>.  


## -syntax


````
void FltAddOpenReparseEntry(
  _In_ PFLT_FILTER Filter,
  _In_ PECP_LIST   EcpList
);
````


## -parameters




### -param Filter [in]

The filter to dereference.


### -param EcpList [in]

The ECP list whose open reparse information should
                       be deallocated.


## -returns


This routine does not return a value.


