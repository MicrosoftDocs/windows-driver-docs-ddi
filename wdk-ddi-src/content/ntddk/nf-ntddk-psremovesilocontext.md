---
UID: NF:ntddk.PsRemoveSiloContext
title: PsRemoveSiloContext function (ntddk.h)
description: This routine removes an object that was inserted in the Silo.
old-location: kernel\psremovesilocontext.htm
tech.root: kernel
ms.assetid: 3323EF1B-9EB3-4D56-A9A5-0A8397F8A235
ms.date: 04/30/2018
ms.keywords: PsRemoveSiloContext, PsRemoveSiloContext routine [Kernel-Mode Driver Architecture], kernel.psremovesilocontext, ntddk/PsRemoveSiloContext
ms.topic: function
f1_keywords:
 - "ntddk/PsRemoveSiloContext"
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
- PsRemoveSiloContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsRemoveSiloContext function


## -description


This routine removes an object that was inserted in the <i>Silo</i>.


## -parameters




### -param Silo [in]

The silo from which the object is to be removed. This parameter is required and it cannot be <b>NULL</b>.


### -param ContextSlot [in]

A slot allocated by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-psallocsilocontextslot">PsAllocSiloContextSlot</a> routine.


### -param RemovedSiloContext

<p>A pointer to a caller-allocated variable that receives the address of the removed object. This parameter is optional and can be <b>NULL</b>.</p>




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
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The slot is read-only and it cannot be modified. This is an error code. 

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



In a successful call to <b>PsRemoveSiloContext</b> where the <i>RemovedSiloContext</i> parameter is not <b>NULL</b> and does not point to <b>NULL</b>, the caller must decrement the object that the <i>RemovedSiloContext</i> parameter points to, by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-psdereferencesilocontext">PsDereferenceSiloContext</a> when it is no longer needed. 



