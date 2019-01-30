---
UID: NF:fltkernel.FltCopyOpenReparseList
title: FltCopyOpenReparseList function (fltkernel.h)
description: This routine copies any open reparse information from a previous create into a new ECP list that can be used to issue a second create.
old-location: ifsk\fltcopyopenreparselist.htm
tech.root: ifsk
ms.assetid: 07C39363-559A-4B55-850E-052BA78E869D
ms.date: 04/16/2018
ms.keywords: FltAddOpenReparseEntry, FltAddOpenReparseEntry routine [Installable File System Drivers], FltCopyOpenReparseList, fltkernel/FltAddOpenReparseEntry, ifsk.fltcopyopenreparselist
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

# FltCopyOpenReparseList function


## -description


This routine copies any open reparse information from a previous create into
    a new ECP list that can be used to issue a second create.


## -parameters




### -param Filter [in]

The filter to reference.


### -param Data [in]

The create operation from which open reparse
                       information should be copied.


### -param EcpList [in, out]

A new ECP list to copy open reparse information
                       to.


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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt734259">FltFreeOpenReparseList</a>
 

 

