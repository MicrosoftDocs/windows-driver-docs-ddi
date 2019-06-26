---
UID: NF:ntddk.PsGetPermanentSiloContext
title: PsGetPermanentSiloContext function (ntddk.h)
description: This routine retrieves an object that was inserted in the Silo without incrementing the reference count.
old-location: kernel\psgetpermanentsilocontext.htm
tech.root: kernel
ms.assetid: C1AEFC8F-6488-4582-9835-DAD07D4ACB17
ms.date: 04/30/2018
ms.keywords: PsGetPermanentSiloContext, PsGetPermanentSiloContext routine [Kernel-Mode Driver Architecture], kernel.psgetpermanentsilocontext, ntddk/PsGetPermanentSiloContext
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
- PsGetPermanentSiloContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsGetPermanentSiloContext function


## -description


This routine retrieves an object that was inserted in the <i>Silo</i> without incrementing the reference count.


## -parameters




### -param Silo [in]

The silo in which the object was inserted. This parameter is required and it cannot be <b>NULL</b>.


### -param ContextSlot [in]

The read-only slot that was previously allocated by<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-psallocsilocontextslot">PsAllocSiloContextSlot</a> and made read-only by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-psmakesilocontextpermanent">PsMakeSiloContextPermanent</a>.


### -param ReturnedSiloContext

A pointer to a caller-allocated variable that receives the address of the existing object. This parameter is required and it cannot be <b>NULL</b>.


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
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The slot is empty. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED </b></dt>
</dl>
</td>
<td width="60%">
The slot is not read-only and it cannot safely retrieve the object. This is an error code.

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



A successful call to <b>PsGetPermanentSiloContext</b> does not increment the reference count on the object that the <i>ReturnedSiloContext</i> parameter points to. The returned object pointer is valid as long as there is a valid reference on the silo object.



