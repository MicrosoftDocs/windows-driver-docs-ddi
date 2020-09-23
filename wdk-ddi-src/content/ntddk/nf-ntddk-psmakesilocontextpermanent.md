---
UID: NF:ntddk.PsMakeSiloContextPermanent
title: PsMakeSiloContextPermanent function (ntddk.h)
description: This routine makes the slot in a silo instance read-only, allowing the object in the slot to be retrieved without affecting the reference count on that object.
old-location: kernel\psmakesilocontextpermanent.htm
tech.root: kernel
ms.assetid: 74BE4FF9-0342-4942-A58F-9C6D5F76E5F0
ms.date: 04/30/2018
keywords: ["PsMakeSiloContextPermanent function"]
ms.keywords: PsMakeSiloContextPermanent, PsMakeSiloContextPermanent routine [Kernel-Mode Driver Architecture], kernel.psmakesilocontextpermanent, ntddk/PsMakeSiloContextPermanent
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PsMakeSiloContextPermanent
 - ntddk/PsMakeSiloContextPermanent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsMakeSiloContextPermanent
---

# PsMakeSiloContextPermanent function


## -description

This routine makes the slot in a silo instance read-only, allowing the object in the slot to be retrieved without affecting the reference count on that object.

## -parameters

### -param Silo 

[in]
The silo in which the slot resides. This parameter is required and it cannot be <b>NULL</b>.

### -param ContextSlot 

[in]
The slot to make read-only. The slot must be previously allocated by the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psallocsilocontextslot">PsAllocSiloContextSlot</a> routine.

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The slot does not contain a valid object. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The slot has not been allocated. This is an error code.

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

Before calling this routine, the slot must contain a valid object. After it completes, the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psreplacesilocontext">PsReplaceSiloContext</a> and <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremovesilocontext">PsRemoveSiloContext</a> routines will fail with <b>STATUS_NOT_SUPPORTED</b>.