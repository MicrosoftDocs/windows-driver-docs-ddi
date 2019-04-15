---
UID: NF:fltkernel.FltFreeOpenReparseList
title: FltFreeOpenReparseList function (fltkernel.h)
description: This routine deallocates any information copied into a create operation by a previous call to FltCopyOpenReparseList.
old-location: ifsk\fltfreeopenreparselist.htm
tech.root: ifsk
ms.assetid: 78FA1585-F834-48E4-BB15-78BA5563F9D0
ms.date: 04/16/2018
ms.keywords: FltAddOpenReparseEntry, FltAddOpenReparseEntry routine [Installable File System Drivers], FltFreeOpenReparseList, fltkernel/FltAddOpenReparseEntry, ifsk.fltfreeopenreparselist
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fltKernel.h
api_name:
- FltAddOpenReparseEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltFreeOpenReparseList function


## -description


This routine deallocates any information copied into a create operation by
    a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt734258">FltCopyOpenReparseList</a>.  


## -parameters




### -param Filter [in]

The filter to dereference.


### -param EcpList [in]

The ECP list whose open reparse information should
                       be deallocated.


## -returns



This routine does not return a value.



