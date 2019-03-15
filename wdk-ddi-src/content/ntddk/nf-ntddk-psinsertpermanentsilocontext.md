---
UID: NF:ntddk.PsInsertPermanentSiloContext
title: PsInsertPermanentSiloContext function (ntddk.h)
description: This routine inserts an object in an empty slot in a Silo.
old-location: kernel\psinsertpermanentsilocontext.htm
tech.root: kernel
ms.assetid: ADBAB25B-7646-4E0E-AFD8-18B87A293674
ms.date: 04/30/2018
ms.keywords: PsInsertPermanentSiloContext, PsInsertPermanentSiloContext routine [Kernel-Mode Driver Architecture], kernel.psinsertpermanentsilocontext, ntddk/PsInsertPermanentSiloContext
ms.topic: function
req.header: ntddk.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- PsInsertPermanentSiloContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsInsertPermanentSiloContext function


## -description


This routine inserts an object in an empty slot in a <i>Silo</i>.


## -parameters




### -param Silo [in]

The silo in which the object is to be inserted. This parameter is required and it cannot be <b>NULL</b>. 


### -param ContextSlot [in]

The slot in which the object is to be inserted. A slot allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt735056">PsAllocSiloContextSlot</a> routine.


### -param SiloContext [in]

The object to be inserted, created by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt735058">PsCreateSiloContext</a> routine. The object must be created using the same silo as specified in the <i>Silo</i> parameter. This parameter is required and it cannot be <b>NULL</b>. 


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
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are no resources in the system to perform the insert. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The slot is not empty. This is an error code.

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



A successful call to <b>PsInsertPermanentSiloContext</b> increments the reference count on <i>SiloContext</i>. If <b>PsInsertPermanentSiloContext</b> fails, the reference count remains unchanged. In either case, after the routine completes, the caller must call <a href="https://msdn.microsoft.com/library/windows/hardware/mt735059">PsDereferenceSiloContext</a> to decrement the <i>SiloContext</i> object.



